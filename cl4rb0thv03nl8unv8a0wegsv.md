## How to Create Your Own Operating System

In the present day, the typical end-client seldom contemplates the working framework they use. In the cell phone market, as per the GlobalStats site, the Android umbrella rules with a total 73 percent piece of the pie while Apple's environment makes up the rest — in the mean time, in the event that you take a gander at PCs, the image is a lot of something similar with Microsoft frameworks taking the largest part of all frameworks being used.

Actually, I could do without Windows and the nearest feasible option other than the Mac framework I'm composing this on is Linux, which doesn't come close in everyday ease of use. It is generally viewed as difficult to upset the present-day syndications in the PC market — an opinion that I both hate and concur with — and I don't expect to do the unthinkable.

Notwithstanding, I truly do expect to utilize this series of articles to show that making even an exceptionally basic low-level program can be a fabulous opportunity for growth for a software engineer at any level.

Before we start, I might want to say that this article will expect a degree of knowledge of a few essential and a few high level ideas in software engineering and programming, for example,

- Hexadecimal and paired documentation;
- Information structures and their creation and control;
- Calculations;
- Gathering;
- As well as some more theoretical programming ideas.
# Getting everything rolling
We'll begin by setting up a cross-compiler. There are a couple of assets out there that will let you know how to do this for GCC, in spite of the fact that I will compose this series involving LLVM and Clang as a base since we'll later jump into some other programming dialects by the way.

You ought to as of now have Git and CMake introduced as they are both utilized vigorously in this series. Assuming you want to download them, you might do as such in the accompanying areas:

- Git
- CMake
A similar applies to LLVM and Clang, and you might obtain them by running the accompanying in a terminal:

```
mkdir llvm
cd llvm

# Clone the llvm-project repository.
git clone https://github.com/llvm/llvm-project.git

# Create the build directory.
mkdir build
cd build

# Generate build files with CMake.
cmake -DCMAKE_BUILD_TYPE=Release -S ../llvm-project/llvm -DLLVM_ENABLE_PROJECTS='clang lld'

# Build with Make.
make
make install

``` 

In the event that you don't as of now have to Make, you could run CMake for an alternate generator like Ninja utilizing - GNinja, in spite of the fact that Make is the default and accompanies most Unix-based frameworks.

Assuming you're following this series on Windows, you have a few choices — you can introduce MinGW, an insignificant climate that accompanies GNU instruments like make, or you can utilize a WSL establishment. Windows Subsystem for Linux is, as the name could infer, a full Linux framework heated into your Windows introduction.

Whenever we have cleared these fundamentals, we're prepared to continue on toward the seriously thrilling piece of this story: the code!
# Initial Boilerplate
The principal thing we will do is think of some Assembly code. We would rather not invest an excess of energy in Assembly-land so we will make the absolute minimum of the standard to place us into our C climate.

We'll initially pronounce a few constants for our multi-boot header:


```
.set ALIGN, 1<<0
.set MEMINFO, 1<<1
.set FLAGS, ALIGN | MEMINFO
.set MAGIC,    0x1BADB002
.set CHECKSUM, -(MAGIC + FLAGS)
``` 
These constants are some "sorcery" esteems that are totally archived in the multiboot standard.

Then, we'll characterize a few segments. We want to ensure that the program distinguishes as a portion, so we'll begin with our multiboot header and afterward BSS, and lastly, the Text segment where we characterize our entrance into our primary capability.


```

.section .multiboot
.align 4
.long ALIGN
.long FLAGS
.long CHECKSUM

.section .bss
.align 16

stack_bottom:
.skip 16384 # We skip 16KB

stack_top:

.section .text
.global _start
.type _start, @function
_start:  
  /*
  To get our stack setup, we need to set the
  ESP register to the top of the stack.
  */
  mov $stack_top, %esp
  
  # Call into our main function
  call kernelMain
  cli

1:hlt
  jmp 1b

/*
Set the size of the _start symbol to the 
current location '.' minus its start.
*/
.size _start, . - _start
``` 

This code empowers us to start writing in a more elevated level language fitting our personal preference, which is C for this situation. You might gather that first to ensure that it works involving C langs as.

First and foremost, we really want to work out a few utility capabilities. We really want to ensure that we can keep in touch with the screen — something we'll later execute utilizing pixel supports — utilizing a blend of cradles and VGA variety codes.




```
#include <stddef.h>
#include <stdint.h>
#include <stdbool.h>

enum vga {
  VGA_BLACK = 0,
  VGA_BLUE = 1,
  VGA_GREEN = 2,
  VGA_CYAN = 3,
  VGA_RED = 4,
  VGA_MAGENTA = 5,
  VGA_BROWN = 6,
  VGA_LIGHT_GREY = 7,
  VGA_DARK_GREY = 8,
  VGA_LIGHT_BLUE = 9,
  VGA_LIGHT_GREEN = 10,
  VGA_LIGHT_CYAN = 11,
  VGA_LIGHT_RED = 12,
  VGA_LIGHT_MAGENTA = 13,
  VGA_LIGHT_BROWN = 14,
  VGA_WHITE = 15,
}

static inline uint8_t vga_color(enum vga fg, enum vga bg) {
  return fg | bg << 4;
}
 
static inline uint16_t vga_entry(unsigned char uc, uint8_t color) {
  return (uint16_t) uc | (uint16_t) color << 8;
}

``` 

Now we can create a very basic shell:


```
size_t strlen(const char* str) {
  size_t len = 0;
  while (str[len])
    len++;
  
  return len;
}
 
static const size_t VGA_WIDTH = 80;
static const size_t VGA_HEIGHT = 25;
 
size_t shell_row;
size_t shell_col;
uint8_t shell_color;
uint16_t* shell_buf;
 
void shell_init(void) {
  shell_row = 0;
  shell_col = 0;
  shell_color = vga_color(VGA_LIGHT_GREY, VGA_BLACK);
  shell_buf = (uint16_t*) 0xB8000;
  
  for (size_t y = 0; y < VGA_HEIGHT; y++) {
    for (size_t x = 0; x < VGA_WIDTH; x++) {
      const size_t index = y * VGA_WIDTH + x;
      shell_buf[index] = vga_entry(' ', shell_color);
    }
  }
}
 
void shell_setColor(uint8_t color) {
  shell_color = color;
}
 
void shell_putEntryAt(char c, uint8_t color, size_t x, size_t y) {
  const size_t index = y * VGA_WIDTH + x;
  shell_buf[index] = vga_entry(c, color);
}
 
void shell_putChar(char c) {
  shell_putEntryAt(c, shell_color, shell_col, shell_row);
  
  if (++shell_col == VGA_WIDTH) {
    shell_col = 0;
    
    if (++shell_row == VGA_HEIGHT)
      shell_row = 0;
  }
}
 
void shell_write(const char* data, size_t size) {
  for (size_t i = 0; i < size; i++)
    shell_putChar(data[i]);
}
 
void shell_writeString(const char* data) {
  shell_write(data, strlen(data));


``` 

Furthermore, presently we can, at last, compose something!

We can compose the fundamental capability that we alluded to before and we can utilize our writeString capability to print something to our screen!


```

void kernelMain(void) {
  /* Initialize terminal interface */
  shell_init();
 
  /* Newline support is left as an exercise. */
  shell_writeString("Hello, kernel World!\n");
}
``` 
Hello, world!
Now, we’ll need to link everything together:


```
/* The bootloader will look at this image and start execution at the symbol
   designated as the entry point. */
ENTRY(_start)
 
/* Tell where the various sections of the object files will be put in the final
   kernel image. */
SECTIONS
{
  /* Begin putting sections at 1 MiB, a conventional place for kernels to be loaded at by the bootloader. */
  . = 1M;
 
  /* First put the multiboot header, as it is required to be put very early
	   early in the image or the bootloader won't recognize the file format.
	   Next we'll put the .text section. */
  .text BLOCK(4K) : ALIGN(4K)
  {
    *(.multiboot)
    *(.text)
  }
 
  /* Read-only data. */
  .rodata BLOCK(4K) : ALIGN(4K)
  {
    *(.rodata)
  }
 
  /* Read-write data (initialized) */
  .data BLOCK(4K) : ALIGN(4K)
  {
    *(.data)
  }
 
  /* Read-write data (uninitialized) and stack */
  .bss BLOCK(4K) : ALIGN(4K)
  {
    *(COMMON)
    *(.bss)
  }
 
  /* The compiler may produce other sections, by default it will put them in a segment with the same name. Simply add stuff here as needed. */
}

``` 

To fabricate our straightforward working framework, begin by ordering the Assembly code. You might do as such by running a crash bootloader.s - o bootloader.o.

Join the C code into one record and incorporate it with bang kernel.c - o kernel.o. This produces the last piece you really want to interface it.

You may now interface your piece together by running bang - T osLinker.ld - o myos.bin - ffreestanding - O2 - nostdlib bootloader.o kernel.o.

With an extremely essential part currently gathered, you might streak it onto a USB stick and run it that way, or you can run it in a virtual machine like QEMU or VirtualBox.


# Assets
As a disclaimer, a portion of the code was acquired from several distinct sources:
- [OSDev Wiki](https://wiki.osdev.org/Main_Page)



