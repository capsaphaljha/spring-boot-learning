
# Main 
#### The main() method is required in every Java program. It is where the program starts running, or the enrtry point of the program, public static void main(String[] arg)

-   System.out.println("Hello World");
-- System is a built-in Java class.
-- out is a member of System, short for "output".
-- println() is a method, short for "print line".

---

## Java Statements
A computer program is a list of "instructions" to be "executed" by a computer.
In a programming language, these programming instructions are called statements.
ex: System.out.println("Java is fun!");

---

## print() vs println() 
The only difference is that it (print method) does not insert a new line at the end of the output
Double quote required for string type but for numbers without quoute
SOP ("10" + 5)
OP: 105

---

## Comments
Comments can be used to explain Java code, and to make it more readable. It can also be used to prevent execution when testing alternative code.

---

## Java Variables
Variables are containers for storing data values.
String - stores text, such as "Hello". String values are surrounded by double quotes
String myText = "Hello";

### int - stores integers (whole numbers), without decimals, such as 123 or -123
int myNum = 5;

### float - stores floating point numbers, with decimals, such as 19.99 or -19.99

### float myFloatNum = 5.99f;

### char - stores single characters, such as 'a' or 'B'. Char values are surrounded by single quotes
char myLetter = 'D';

### boolean - stores values with two states: true or false
boolean myBool = true;


Code example:
 type variableName = value;
 String name = "John";

You can also declare a variable without assigning the value, and assign the value later:

int myNum;
myNum = 15;

---

## Final Variables
this will declare the variable as "final" or "constant", which means unchangeable and read-only

### One Value to Multiple Variables
int x, y, z;
x = y = z = 50;

### Identifiers
All Java variables must be identified with an unique names. These unique names are called identifiers.
like x and y or more descriptive names (age, sum, totalVolume).

### Constants (final)
A variable declared with final becomes a constant, which means unchangeable and read-only:

### Data Types
Data types are divided into two groups:

- Primitive data types - A primitive data type specifies the type of a variable and the kind of values it can hold.
includes byte, short, int, long, float, double, boolean and char
-------------------------------------------------------------
| Data Type   |	Description|

byte        |	Stores whole numbers from -128 to 127 
short       |	Stores whole numbers from -32,768 to 32,767
int         |	Stores whole numbers from -2,147,483,648 to 2,147,483,647
long        |	Stores whole numbers from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
float       |	Stores fractional numbers. Sufficient for storing 6 to 7 decimal digits ( 32-bit )
double      |	Stores fractional numbers. Sufficient for storing 15 to 16 decimal digits ( 64-bit )
boolean     |	Stores true or false values
char        |	Stores a single character/letter or ASCII values
Alternatively, if you are familiar with ASCII values, you can use those to display certain characters:
char myVar1 = 65;
will return A as it storing the ascii value



Once a variable is declared with a type, it cannot change to another type later in the program:

## Floating Point Types
The float and double data types can store fractional numbers. Note that you should end the value with an "f" for floats and "d" for doubles

float myNum = 5.75f;
double myNum = 19.99d;


## Non-primitive data types 
such as String, Arrays and Classes 
Non-primitive data types are called reference types because they refer to objects.

The main differences between primitive and non-primitive data types are:

Primitive types in Java are predefined and built into the language, while non-primitive types are created by the programmer (except for String).
Non-primitive types can be used to call methods to perform certain operations, whereas primitive types cannot.
Primitive types start with a lowercase letter (like int), while non-primitive types typically starts with an uppercase letter (like String).
Primitive types always hold a value, whereas non-primitive types can be null.
Examples of non-primitive types are Strings, Arrays, Classes etc. 

## var Keyword 
introduced in Java 10 (released in 2018).
var keyword lets the compiler automatically detect the type of a variable based on the value you assign to it.
This helps you write cleaner code and avoid repeating types, especially for long or complex types.

instead 
int x = 5;  you can write:
var x = 5;  // x is an int
Note:  Once the type is chosen, it stays the same.

When to Use var - For simple variables 
it's usually clearer to write the type directly (int, double, char, etc.).

But for more complex types, such as ArrayList or HashMap,
var can make the code shorter and easier to read:

// Without var
ArrayList<String> cars = new ArrayList<String>();

// With var
var cars = new ArrayList<String>();


## Type Casting
Type casting means converting one data type into another. For example, turning an int into a double.

Two main types of casting:
Widening Casting (automatic) - converting a smaller type to a larger type size (no risk of losing information)
byte -> short -> char -> int -> long -> float -> double

example:
int myInt = 9;
double myDouble = myInt; // Automatic casting: int to double

Narrowing Casting (manual) - converting a larger type to a smaller type size
double -> float -> long -> int -> char -> short -> byte
eg:
double myDouble = 9.78d;
int myInt = (int) myDouble; // Manual casting: double to int

## Operators
Operators are used to perform operations on variables and values.

Java divides the operators into the following groups:

Arithmetic operators

+	Addition	Adds together two values	x + y	
-	Subtraction	Subtracts one value from another	x - y	
*	Multiplication	Multiplies two values	x * y	
/	Division	Divides one value by another	x / y	
%	Modulus	Returns the division remainder	x % y	
++	Increment	Increases the value of a variable by 1	++x	
--	Decrement	Decreases the value of a variable by 1	--x

Assignment operators

=	x = 5	    x = 5	
+=	x += 3	    x = x + 3	
-=	x -= 3	    x = x - 3	
*=	x *= 3	    x = x * 3	
/=	x /= 3	    x = x / 3	
%=	x %= 3	    x = x % 3	
&=	x &= 3	    x = x & 3	
|=	x |= 3	    x = x | 3	
^=	x ^= 3	    x = x ^ 3	
>>=	x >>= 3	    x = x >> 3	
<<=	x <<= 3	    x = x << 3

Comparison operators
==	Equal to	x == y	
!=	Not equal	x != y	
>	Greater than	x > y	
<	Less than	x < y	
>=	Greater than or equal to	x >= y	
<=	Less than or equal to	x <= y


Logical operators

&& 	Logical and	Returns true if both statements are true	x < 5 &&  x < 10	
|| 	Logical or	Returns true if one of the statements is true	x < 5 || x < 4	
!	Logical not	Reverse the result, returns false if the result is true	!(x < 5 && x < 10)


Bitwise operators

# Strings

A String variable contains a collection of characters surrounded by double quotes (""):

- String Length

eg:
String txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
txt.length() - length of a string 
toUpperCase
toLowerCase
txt.indexOf("locate") - index (the position) of the first occurrence 

charAt -  access a character at a specific position
String txt = "Hello";
System.out.println(txt.charAt(0));  // H


txt1.equals(txt2) -  compare two string : true/false

txt.trim() -  removes whitespace

---

### Concatenation
]
System.out.println(firstName + " " + lastName);

System.out.println(firstName.concat(lastName));

| Feature | + Operator | String.concat() Method |
| :--- | :---: | ---: |
| Argument Types | Any data type (int, float, Object, etc.). Non-strings are automatically converted using toString(). | Only String objects are allowed. |
| Number of Arguments | Can chain multiple arguments at once (e.g., a + b + c). | Takes exactly one String argument per call. (you have to call that mehtod multiple times) |
| Null Handling	| Converts a null reference into the literal string "null". | Throws a NullPointerException if the variable or argument is null. |
|Under the Hood |Implemented using StringBuilder (or StringBuffer) append methods |	Creates a new internal character array (char[]) directly |
| Empty String Handling	| Always creates a new String object in memory |	Returns the original object reference if the appended string length is 0|

---
### Numbers and Strings
- If you add two numbers, the result will be a number:
- If you add two strings, the result will be a string concatenation:
- If you add a number and a string, the result will be a string concatenation:

### Special Characters
| Escape character |	Result |	Description |
| :---  | :--- | :---  |
| \'	| '	| Single quote |
| \"	| "	| Double quote| 
| \\	| \	| Backslash |

### Common escape sequences that are valid in Java are:
| Code  | Result |
| :---  | :--- | :---  |
|   \n  |	New Line    | 	
|   \t  |	Tab     |
|   \b  |	Backspace   |	
|   \r  |	Carriage Return     |	
|   \f  |	Form Feed   |

----
# Math
Math class has many methods that allows you to perform mathematical tasks on numbers.

Math.max(x,y) - Method can be used to find the highest value of x and y
The Math.min(x,y) - method can be used to find the lowest value of x and y
The Math.sqrt(x) - method returns the square root of x
The Math.abs(x) - method returns the absolute (positive) value of x
The Math.pow(x, y) method returns the value of x raised to the power of y (eg 2^8 ,  O/P = 256)

### Rounding Methods

- Math.round(x) - rounds to the nearest integer
Math.round(4.6);  // 5

- Math.ceil(x) - rounds up (returns the smallest integer greater than or equal to x)
Math.ceil(4.1);   // 5.0

- Math.floor(x) - rounds down (returns the largest integer less than or equal to x)
Math.floor(4.9);  // 4.0


### Random
- Math.random() returns a random number between 0.0 (inclusive), and 1.0 (exclusive):
- int randomNum = (int)(Math.random() * 101);  // 0 to 100, more control over the random number
---

# Booleans
For this, Java has a boolean data type, which can store true or false values.

boolean isJavaFun = true;
boolean isFishTasty = false;

System.out.println(isJavaFun);    // Outputs true
System.out.println(isFishTasty);  // Outputs false

### Boolean Expressions
A boolean expression returns a boolean value: true or false.

Example:
- System.out.println(x > y); // Outputs true, because 10 is greater than 9
- System.out.println(10 > 9); // Outputs true, because 10 is greater than 9
- System.out.println(x == 10); // Outputs true, because the value of x is equal to 10
- System.out.println(10 == 15); // Outputs false, because 10 is not equal to 15


int x = 10;
int y = 9;
boolean isGreater = x > y;
System.out.println(isGreater); // Outputs true

int myAge = 25;
int votingAge = 18;
System.out.println(myAge >= votingAge);

---



# If ... Else 
- Conditions and if statements let you control the flow of your program
- If Without Braces
If an if statement has only one line of code, you can write it without curly braces { }:
if (20 > 18)
  System.out.println("20 is greater than 18");
To avoid mistakes, always use curly braces { }

- The else statement lets you run a block of code when the condition in the if statement is false.

---

# Ternary Operator - Short Hand If...Else 
- There is also a short-hand if else, which is known as the ternary operator because it consists of three operands.

variable = (condition) ? expressionTrue :  expressionFalse;

Example :

int time = 20;
String result = (time < 18) ? "Good day." : "Good evening.";
System.out.println(result);

- Use the ternary operator directly inside System.out.println() without a temporary variable:

int time = 20;
System.out.println((time < 18) ? "Good day." : "Good evening.");

- Nested Ternary

example:

int time = 22;
String message = (time < 12) ? "Good morning."
               : (time < 18) ? "Good afternoon."
               : "Good evening.";
System.out.println(message);

---
# Logical Operators in Conditions
- You can combine or reverse conditions using logical operators.

&& (AND) - all conditions must be true
|| (OR) - at least one condition must be true
! (NOT) - reverses a condition (true = false, false = true)


# Switch Statements
- Instead of writing many if..else statements, you can use the switch statement.

This is how it works:

The switch expression is evaluated once.
The result is compared with each case value.
If there is a match, the matching block of code runs.
The break statement stops the switch after the matching case has run.
The default statement runs if there is no match.

switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}

- A break can save a lot of execution time because it "ignores" the execution of all the rest of the code in the switch block.

- default Keyword
The default keyword specifies some code to run if there is no case match:
Note that if the default statement is used as the last statement in a switch block, it does not need a break.

- 


# swtich case vs if_else 

| Feature | switch-case | if-else | 
| :--- | :--- | :--- |
| Condition Type | Tests only for equality (==) against specific constant values.| Evaluates arbitrary boolean expressions (e.g., <, >, &&, `
| Supported Data Types | Primitives (int, char, byte, short), String, enum, and wrapper classes. | Any data type, as long as the ultimate expression resolves to a boolean.|
| Execution Flow | Jumps directly to the matching case. Requires break to stop (or uses modern arrow -> syntax). | Checks conditions sequentially from top to bottom until one matches.|
| Performance | Faster for many conditions. Uses a compiler optimization called a jump table (lookupswitch / tableswitch).| Slower for large numbers of conditions because it evaluates every expression line-by-line.|
| Readability | Highly clean and structured for multi-way branching on a single variable. | 	Can become cluttered ("ladder effect") when nesting multiple conditions. | 

---

# While Loop

- The while loop repeats a block of code as long as the specified condition is true

int i = 0;
while (i < 5) {
  System.out.println(i);
  i++;
}

-  A while loop may never run if the condition is false from the start.

# Do/While Loop

- The do/while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true. 

do {
  // code block to be executed
}
while (condition);

Real life example, asking for paswordd with 3 times counter


# For Loop
- When you know exactly how many times you want to loop through a block of code, use the for loop instead of a while loop:

for (int i = 0; i < 5; i++) {
  System.out.println(i);
}

# for-each Loop
There is also a "for-each" loop, which is used exclusively to loop through elements in an array (or other data structures)

for (type variableName : arrayName) {
  // code block to be executed
}

Example:

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

for (String car : cars) {
  System.out.println(car);
}

---

# Break and Continue

- break = stop the loop completely.


- continue = skip this round, but keep looping.

# Arrays
- Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.
- To declare an array, define the variable type with square brackets [ ] :

String[] cars;
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

### Lenght 
- To find out how many elements an array has, use the length property:

for (int i = 0; i < numbers.length; i++) {
  sum += numbers[i];
}


### Array with For-Each

int[] numbers = {45, 12, 98, 33, 27};

int max = numbers[0];
int min = numbers[0];

for (int n : numbers) {
  if (n > max) {
    max = n;
  }
  if (n < min) {
    min = n;
  }
}


### Multidimensional 

int[][] myNumbers = { {1, 4, 2}, {3, 6, 8} };



# Methods
 - Methods are the building blocks which run when they called
 - We can also pass param un methods
 - Mehtods can be categories to perform perticular operations
 - Code can we resuse

 EG:
public class Main {
  static void myMethod() {
    System.out.println("I just got executed!");
  }

  public static void main(String[] args) {
    myMethod();
  }
}
- myMethod() is the name of the method
- static means that the method belongs to the Main class and not an object of the Main class. 
- void means that this method does not have a return value.


### Parameters and Arguments

- Information can be passed to methods as a parameter. Parameters act as variables inside the method.

EG- 
public class Main {
  static void myMethod(String fname) {
    System.out.println(fname + " Refsnes");
  }

  public static void main(String[] args) {
    myMethod("Liam");
  }
}

- NOTE: When a parameter is passed to the method, it is called an argument. So, from the example above: fname is a parameter, while Liam, Jenny and Anja are arguments.  

- Return : 
    - "void" keyword in all examples (like static void myMethod(int x)), which indicates that the method should not return a value.

    - If you want the method to return a value, you can use a primitive data type (such as int, char, etc.) instead of void, and use the return keyword inside the method

 public class Main {
      static int myMethod(int x) {
    return 5 + x;
  }

  public static void main(String[] args) {
    System.out.println(myMethod(3));
  }
}

# Method Overloading

- Multiple methods can have the same name with different parameters
EG:

```java
int myMethod(int x)
float myMethod(float x)
double myMethod(double x, double y)

static int plusMethod(int x, int y) {
  return x + y;
}

static double plusMethod(double x, double y) {
  return x + y;
}

public static void main(String[] args) {
  int myNum1 = plusMethod(8, 5);
  double myNum2 = plusMethod(4.3, 6.26);
  System.out.println("int: " + myNum1);
  System.out.println("double: " + myNum2);
}
```

----

# Variable Scope

- In Java, variables are only accessible inside the region where they are created. This is called scope.

### In Method Scope
- Variables declared directly inside a method are available anywhere in the method following the line of code in which they were declared:

### In Block Scope
- Variables declared inside a block of code are only accessible by the code between the curly braces, and only after the line in which the variable was declared

### In Loop Scope
- 









# this keyword

- The this keyword in Java refers to the current object in a method or constructor.

this.x

- Calling a Constructor from Another Constructor, You can also use this() to call another constructor in the same class.
This is useful when you want to provide default values or reuse initialization code instead of repeating it.

```java

public class Main {
  int modelYear;
  String modelName;

  // Constructor with one parameter
  public Main(String modelName) {
    // Call the two-parameter constructor to reuse code and set a default year    
    this(2020, modelName);
  }

  // Constructor with two parameters
  public Main(int modelYear, String modelName) {
    // Use 'this' to assign values to the class variables
    this.modelYear = modelYear;
    this.modelName = modelName;
  }

  // Method to print car information
  public void printInfo() {
    System.out.println(modelYear + " " + modelName);
  }

  public static void main(String[] args) {
    // Create a car with only model name (uses default year)
    Main car1 = new Main("Corvette");

    // Create a car with both model year and name
    Main car2 = new Main(1969, "Mustang");

    car1.printInfo();
    car2.printInfo();
  }
}
```
- When to use this?

When a constructor or method has a parameter with the same name as a class variable, use this to update the class variable correctly.
To call another constructor in the same class and reuse code.

---
# Modifiers
- The public keyword is an access modifier, meaning that it is used to set the access level for classes, attributes, methods and constructors.

Access Modifiers - controls the access level

Non-Access Modifiers - do not control access level, but provides other functionality


## Access Modifiers

- For classes, you can use either public or default:

  - public- The class is accessible by any other class	
  - default	- The class is only accessible by classes in the same package. This is used when you don't specify a modifier.


- For attributes, methods and constructors, you can use the one of the following:

  - public - The code is accessible for all classes	
  - private - The code is only accessible within the declared class	
  - default -	The code is only accessible in the same package. This is used when you don't specify a modifier.
  - protected	- The code is accessible in the same package and subclasses.

## Methods : Non-Access Modifiers 

- Non-access modifiers do not control visibility (like public or private), but instead add other features to classes, methods, and attributes.

- The most commonly used non-access modifiers are final, static, and abstract.

  - Final : f you don't want the ability to override existing attribute values, declare attributes as final
  - Static : A static method belongs to the class, not to any specific object. This means you can call it without creating an object of the class.
  
  Note: A static method belongs to the class itself. You can call it without creating an object, but it cannot use variables or methods that belong to an object.


 - abstract - An abstract method belongs to an abstract class, and it does not have a body. The body is provided by the subclass:

## classes : Non-Access Modifiers 
- final	The class cannot be inherited by other classes
- To access an abstract class, it must be inherited from another class. You will learn more about inheritance and abstraction in the Inheritance and Abstraction chapters)


----
-----
continue in other system

-----


# Packages & API
- A package in Java is used to group related classes
  ## Built-in Packages (packages from the Java API)
  - The Java API is a library of prewritten classes, that are free to use, included in the Java Development Environment.
  example: The library contains components for managing input, database programming, and much much more.


  ## User-defined Packages (create your own packages)
  -To create your own package, you need to understand that Java uses a file system directory to store them. Just like folders on your computer:
  Example
└── root
  └── mypack
    └── MyPackageClass.java

To create a package, use the package keyword:

```java
package mypack;
class MyPackageClass {
  public static void main(String[] args) {
    System.out.println("This is my package!");
  }
}
```
Save the file as MyPackageClass.java, and compile it:

- C:\Users\Your Name>javac MyPackageClass.java

Then compile the package:

- C:\Users\Your Name>javac -d . MyPackageClass.java

"This forces the compiler to create the "mypack" package.

The -d keyword specifies the destination for where to save the class file. You can use any directory name, like c:/user (windows), or, if you want to keep the package within the same directory, you can use the dot sign ".", like in the example above.

Note: The package name should be written in lower case to avoid conflict with class names.
"

The library is divided into packages and classes. Meaning you can either import a single class (along with its methods and attributes), or a whole package that contain all the classes that belong to the specified package.- 

eg:
```java

import package.name.Class;   // Import a single class
import package.name.*;   // Import the whole package

```

Class: the Scanner class, which is used to get user input, write the following code:

import java.util.Scanner;


Java 8 features 
Spring boot basics
Spring data
Spring security
Restfull api
Auth
postgre sql

Java 8 Features, Spring Boot Basics, Spring Data JPA, Spring Security, RESTful APIs &  Authentication 

---------



## Inheritance 

- inherit attributes and methods from one class to another

- Subclass - child class

- Superclass - parent  class

### types of Inheritance

- Single Inheritance - B extends A
- Multilevel Inheritance - C extends B, aur B extends A
- Hierarchical Inheritance - B extends A aur C extends A
- Multiple Inheritance - Not supported by java - possible through Interfaces, why not support, because parent class can have same method ( Diamond Problem) name, 
- Hybrid Inheritance - Not supported by java - possible through Interfaces - same problem with hybrid


## final Keyword

If you don't want other classes to inherit from a class, use the final keyword:

Ex:  final class Vehicle

## Polymorphism - Poly = Many, Morphs = Forms

it occurs when we have many classes that are related to each other by inheritance.

- Compile-Time Polymorphism (Static Binding / Early Binding) : 
- Runtime Polymorphism (Dynamic Binding / Late Binding) : 


## super Keyword
The super keyword is used to refer to the parent class of a subclass.
The most common use of the super keyword is to eliminate the confusion between superclasses and subclasses that have methods with the same name.


```java

class Animal {
  public void animalSound() {
    System.out.println("The animal makes a sound");
  }
}

class Dog extends Animal {
  public void animalSound() {
    super.animalSound(); // Call the parent method using super keyword
    System.out.println("The dog says: bow wow");
  }
}

public class Main {
  public static void main(String[] args) {
    Dog myDog = new Dog();
    myDog.animalSound();
  }
}
```

### Access Parent Attributes

```java

class Animal {
  String type = "Animal";
}

class Dog extends Animal {
  String type = "Dog";

  public void printType() {
    System.out.println(super.type); // Access parent attribute
  }
}

public class Main {
  public static void main(String[] args) {
    Dog myDog = new Dog();
    myDog.printType();
  }
}

```

### Call Parent Constructor

```java

class Animal {
  Animal() {
    System.out.println("Animal is created");
  }
}

class Dog extends Animal {
  Dog() {
    super(); // Call parent constructor
    System.out.println("Dog is created");
  }
}

public class Main {
  public static void main(String[] args) {
    Dog myDog = new Dog();
  }
}

```


## Inner Classes

it is also possible to nest classes (a class within a class).
The purpose of nested classes is to group classes that belong together, which makes your code more readable and maintainable.

eg:

```java

class OuterClass {
  int x = 10;

  class InnerClass {
    int y = 5;
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass myOuter = new OuterClass();
    OuterClass.InnerClass myInner = myOuter.new InnerClass();
    System.out.println(myInner.y + myOuter.x);
  }
}


```

### Private Inner Class

Unlike a "regular" class, an inner class can be private or protected.
If you don't want outside objects to access the inner class, declare the class as private:

```java
class OuterClass {
  int x = 10;

  private class InnerClass {
    int y = 5;
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass myOuter = new OuterClass();
    OuterClass.InnerClass myInner = myOuter.new InnerClass();
    System.out.println(myInner.y + myOuter.x);
  }
}
```

### Static Inner Class

An inner class can also be static, which means that you can access it without creating an object of the outer class:

```java
class OuterClass {
  int x = 10;

  static class InnerClass {
    int y = 5;
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass.InnerClass myInner = new OuterClass.InnerClass();
    System.out.println(myInner.y);
  }
}
```

### Access Outer Class From Inner Class

```java
class OuterClass {
  int x = 10;

  class InnerClass {
    public int myInnerMethod() {
      return x;
    }
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass myOuter = new OuterClass();
    OuterClass.InnerClass myInner = myOuter.new InnerClass();
    System.out.println(myInner.myInnerMethod());
  }
}
```



## Abstraction

- Data abstraction is the process of hiding certain details and showing only essential information to the user.
- Abstraction can be achieved with either abstract classes or interfaces
- The abstract keyword is a non-access modifier, used for classes and methods:

  - Abstract class: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
  - Abstract method: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).

-An abstract class can have both abstract and regular methods:

```java
abstract class Animal {
  public abstract void animalSound();
  public void sleep() {
    System.out.println("Zzz");
  }
}
```

##

```java
// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```



## Interface
- An interface is a completely "abstract class" that is used to group related methods with empty bodies:\
- 
```java
// interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void run(); // interface method (does not have a body)
}
```
- To access the interface methods, the interface must be "implemented"  (kinda like inherited) by another class with the implements keyword (instead of extends). The body of the interface method is provided by the "implement" class:

```java
// Interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

// Pig "implements" the Animal interface
class Pig implements Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig();  // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```

Notes on Interfaces:
Like abstract classes, interfaces cannot be used to create objects (in the example above, it is not possible to create an "Animal" object in the MyMainClass)
Interface methods do not have a body - the body is provided by the "implement" class
On implementation of an interface, you must override all of its methods
Interface methods are by default abstract and public
Interface attributes are by default public, static and final
An interface cannot contain a constructor (as it cannot be used to create objects)
Why And When To Use Interfaces?
1) To achieve security - hide certain details and only show the important details of an object (interface).

2) Java does not support "multiple inheritance" (a class can only inherit from one superclass). However, it can be achieved with interfaces, because the class can implement multiple interfaces. Note: To implement multiple interfaces, separate them with a comma (see example below).


## Anonymous Class

```java
// Normal class
class Animal {
  public void makeSound() {
    System.out.println("Animal sound");
  }
}

public class Main {
  public static void main(String[] args) {
    // Anonymous class that overrides makeSound()
    Animal myAnimal = new Animal() {
      public void makeSound() {
        System.out.println("Woof woof");
      }
    }; // semicolon is required to end the line of code that creates the object

    myAnimal.makeSound();
  }
}
```
### Anonymous Class from an Interface

```java
// Interface
interface Greeting {
  void sayHello();
}

public class Main {
  public static void main(String[] args) {
    // Anonymous class that implements Greeting
    Greeting greet = new Greeting() {
      public void sayHello() {
        System.out.println("Hello, World!");
      }
    };

    greet.sayHello();
  }
}
```


- When to Use Anonymous Classes?
- Use anonymous classes when you need to create a short class for one-time use. For example:
- Overriding a method without creating a new subclass
- Implementing an interface quickly
- Passing small pieces of behavior as objects



## Enums 
- An enum is a special "class" that represents a group of constants (unchangeable variables, like final variables).

```java
public class Main {
  enum Level {
    LOW,
    MEDIUM,
    HIGH
  }

  public static void main(String[] args) {
    Level myVar = Level.MEDIUM; 
    System.out.println(myVar);
  }
}
```
Enum is short for "enumerations", which means "specifically listed".

- Difference between Enums and Classes
- An enum can, just like a class, have attributes and methods. The only difference is that enum constants are public, static and final (unchangeable - cannot be overridden).
- An enum cannot be used to create objects, and it cannot extend other classes (but it can implement interfaces).

Why And When To Use Enums?
Use enums when you have values that you know aren't going to change, like month days, days, colors, deck of cards, etc.


## Enum Constructor
An enum can also have a constructor just like a class.
The constructor is called automatically when the constants are created. You cannot call it yourself.

```java

enum Level {
  // Enum constants (each has its own description)
  LOW("Low level"),
  MEDIUM("Medium level"),
  HIGH("High level");

  // Field (variable) to store the description text
  private String description;

  // Constructor (runs once for each constant above)
  private Level(String description) {
    this.description = description;
  }

  // Getter method to read the description
  public String getDescription() {
    return description;
  }
}

public class Main {
  public static void main(String[] args) {
    Level myVar = Level.MEDIUM; // Pick one enum constant
    System.out.println(myVar.getDescription()); // Prints "Medium level"
  }
}

```

## User Input 

The Scanner class is used to get user input, and it is found in the java.util package.

```java
import java.util.Scanner;  // Import the Scanner class

class Main {
  public static void main(String[] args) {
    Scanner myObj = new Scanner(System.in);  // Create a Scanner object
    System.out.println("Enter username");

    String userName = myObj.nextLine();  // Read user input
    System.out.println("Username is: " + userName);  // Output user input
  }
```



## Date and Time
 - Java does not have a built-in Date class, but we can import the java.time package to work with the date and time API. The package includes many date and time classes. For example:

```java
import java.time.LocalDate; // import the LocalDate class


    LocalDate myObj = LocalDate.now(); // Create a date object


    LocalTime myObj = LocalTime.now(); // current time


    LocalDateTime myObj = LocalDateTime.now(); // date time together


    DateTimeFormatter myFormatObj = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss"); // format data time



```

