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





# Naming Conventions in Java
- A programmer is always said to write clean codes where naming. has to be appropriate so that for any other programmer it acts as an easy way out to read the code. At a smaller level, this seems meaningless but think of the industrial level where it becomes necessary to write clean codes in order to save time for which there are certain rules been laid of which one of the factors is to name the keyword right which is termed as a naming convention in Java. 

- For example when you are using a variable name depicting displacement then it should be named as “displace” or similar likewise not likely x, d which becomes complex as the code widens up and decreases the readability aperture. Consider the below illustrations to get a better understanding which later on we will be discussing in detail.

- Attention reader! Don’t stop learning now. Get hold of all the important Java Foundation and Collections concepts with the Fundamentals of Java and Java Collections Course at a student-friendly price and become industry ready. To complete your preparation from learning a language to DS Algo and many more,  please refer Complete Interview Preparation Course.

## Illustrations: 

- Class: If you are naming any class then it should be a noun and so should be named as per the goal to be achieved in the program such as Add2Numbers, ReverseString, and so on not likely A1, Programming, etc. It should be specific pointing what exactly is there inside without glancing at the body of the class.
- Interface: If you are naming an interface, it should look like an adjective such as consider the existing ones: Runnable, Serializable, etc. Try to use ‘able’ at the end, yes it is said to try as there are no hard and fast bound rules as if we do consider an inbuilt interface such as ‘Remote’, it is not having ble at the end. Consider if you are supposed to create an interface to make read operation then it is suggested as per naming conventions in java to name a similar likely ‘Readable’ interface.
- Methods: Now if we do look closer a method is supposed to do something that it does contains in its body henceforth it should be a verb.
- Constants: As the name suggests it should look like as we read it looks like it is fixed for examples PI, MAX_INT, MIN_INT, etc as follows.
- Naming Conventions in Java 
- In java, it is good practice to name class, variables, and methods name as what they are actually supposed to do instead of naming them randomly. Below are some naming conventions of the java programming language. They must be followed while developing software in java for good maintenance and readability of code. Java uses CamelCase as a practice for writing names of methods, variables, classes, packages, and constants. 




- Camel’s case in java programming consists of compound words or phrases such that each word or abbreviation begins with a capital letter or first word with a lowercase letter, rest all with capital. Here in simpler terms, it means if there are two 

>Note: Do look out for these exceptioj cases to camel casing in java as follows:

- In package, everything is small even while we are combining two or more words in java
In constants, we do use everthing as uppercase and only ‘_’ character is used even if we are combining two or more words in java.
Type 1: Classes and Interfaces

- Class names should be nouns, in mixed cases with the first letter of each internal word capitalized. Interfaces names should also be capitalized just like class names.
Use whole words and must avoid acronyms and abbreviations.
```Classes: class Student { }
         class S=Integer {}
         class Scanner {}
Interfaces : Runnable
             Remote
             Seriazable 
Type 2: Methods 
```
- Methods should be verbs, in mixed case with the first letter lowercase and with the first letter of each internal word capitalized.
public static void main(String [] args)  {}
As the name suggests the method is supposed to be primarily method which indeed it is as main() method in java is the method from where the program begins its execution.

```Type 3: Variables```

- Variable names should be short yet meaningful. 

- Variables can also start with either underscore('_') or dollar sign '$' characters.
- Should be mnemonic i.e, designed to indicate to the casual observer the intent of its use.
- One-character variable names should be avoided except for temporary variables.
- Common names for temporary variables are i, j, k, m, and n for integers; c, d, and e for characters.
```-int[] marks;```
double double answer,
- As the name suggests one stands for marks while the other for an answer be it of any e do not mind.

```Type 4: Constant variables```

- Should be all uppercase with words separated by underscores (“_”).
- There are various constants used in predefined classes like Float, Long, String etc.
num = PI;
```Type 5: Packages```

- The prefix of a unique package name is always written in all-lowercase ASCII letters and should be one of the top-level domain names, like com, edu, gov, mil, net, org.
- Subsequent components of the package name vary according to an organization’s own internal naming conventions.

    ``` java.util.Scanner ;
    java.io.*; 
- As the name suggests in the first case we are trying to access the Scanner class from the java.util package and in other all classes(* standing for all) input-output classes making it so easy for another programmer to identify.

Note:

- For class and interfaces, the first letter has to be uppercase.
- For method , variable, package_name, and constants, the first letter has to be lowercase.


 



