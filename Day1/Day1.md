# Java
## _Java is one of the most popular and widely used programming language._

- Java has been one of the most popular programming language for many years.
- Java is Object Oriented. However it is not considered as pure object oriented as it         provides support for primitive data types (like int, char, etc)
- The Java codes are first compiled into byte code (machine independent code). Then the byte     code runs on Java Virtual Machine (JVM) regardless of the underlying architecture.
- Java syntax is similar to C/C++. But Java does not provide low level programming functionalities like pointers. Also, Java codes are always written in the form of classes and objects.
- Java is used in all kind of applications like Mobile Applications (Android is Java based), desktop applications, web applications, client server applications, enterprise applications and many more.
- When compared with C++, Java codes are generally more maintainable because Java does not allow many things which may lead bad/inefficient programming if used incorrectly. For example, non-primitives are always references in Java. So we cannot pass large objects (like we can do in C++) to functions, we always pass references in Java. One more example, since there are no pointers, bad memory access is also not possible.
- When compared with Python, Java kind of fits between C++ and Python. The programs written in Java typically run faster than corresponding Python programs and slower than C++. Like C++, Java does static type checking, but Python does not.


## Beginning Java programming with Hello World Example
The process of Java programming can be simplified in three steps:
- Create the program by typing it into a text editor and saving it to a file – HelloWorld.java.
- Compile it by typing “javac HelloWorld.java” in the terminal window.
- Execute (or run) it by typing “java HelloWorld” in the terminal window.
```/* This is a simple Java program.
FileName : "HelloWorld.java". */
class HelloWorld
{
	// Your program begins with a call to main().
	// Prints "Hello, World" to the terminal window.
	public static void main(String args[])
	{
		System.out.println("Hello, World");
	}
}
```
1) Class definition:This line uses the keyword class to declare that a new class is being defined.
```class HelloWorld ```
HelloWorld is an identifier that is the name of the class. The entire class definition, including all of its members, will be between the opening curly brace  {  and the closing curly brace  } .

2. main method: In Java programming language, every application must contain a main method whose signature is:
```public static void main(String[] args)
public: So that JVM can execute the method from anywhere.
static: Main method is to be called without object. 
The modifiers public and static can be written in either order.
void: The main method doesn't return anything.
main(): Name configured in the JVM.
String[]: The main method accepts a single argument: 
          an array of elements of type String.
```
Like in C/C++, main method is the entry point for your application and will subsequently invoke all the other methods required by your program.






3.The next line of code is shown here. Notice that it occurs inside main( ).
```System.out.println("Hello, World");```
4.This line outputs the string “Hello, World” followed by a new line on the screen. Output is actually accomplished by the built-in println( ) method. System is a predefined class that provides access to the system, and out is the variable of type output stream that is connected to the console.

```Comments: They can either be multi-line or single line comments.
/* This is a simple Java program. 
Call this file "HelloWorld.java". */
This is a multiline comment. This type of comment must begin with /* and end with */. For single line you may directly use // as in C/C++.
```
# Important Points :

- The name of the class defined by the program is HelloWorld, which is same as name of file(HelloWorld.java). This is not a coincidence. In Java, all codes must reside inside a class and there is at most one public class which contain main() method.
- By convention, the name of the main class(class which contain main method) should match the name of the file that holds the program.
Compiling the program :

- After successfully setting up the environment, we can open terminal in both Windows/Unix and can go to directory where the file – HelloWorld.java is present.
- Now, to compile the HelloWorld program, execute the compiler – javac , specifying the name of the source file on the command line, as shown:
javac HelloWorld.java 
- The compiler creates a file called HelloWorld.class (in present working directory) that contains the bytecode version of the program. Now, to execute our program, JVM(Java Virtual Machine) needs to be called using java, specifying the name of the class file on the command line, as shown:
```java HelloWorld```
- This will print “Hello World” to the terminal screen.








 



