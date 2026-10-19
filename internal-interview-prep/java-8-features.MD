# Java 8 Features
  - Java 8 is one of the most important releases in the history of Java.
  - Released on March 18, 2014, it introduced several major language and library enhancements that made Java programming more concise, expressive, and suitable for functional-style programming.
  - The most significant Java 8 features include Lambda Expressions, Functional Interfaces, Method References, Stream API, the Optional class, the new Date and Time API, and enhancements to interfaces and collections.

### Introduction of the Stream API for efficient data processing.
### A new Date and Time API for better handling of time and date operations.
### Default and static methods in interfaces for greater flexibility.


The following feature enhanced in Java ersion 8:

## Lambda Expressions
## Functional Interfaces
## Default Methods in Interface
## Static Methods in Interface
## Predefined Functional Interfaces
  - Predicates
  - Functions
  - Consumer
  - Supplier
## Double colon operator (::)
## Stream API
## Stream Filter
## Date/Time API (JODA API)
## Method References
## Optional Class
## ForEach() Method
## IO Enhancements
## Type and Repeating Annotations
## Base64 Encode Decode
## Collectors Class
## Nashorn JavaScript Engine
## Parallel Array Sorting
## Concurrency Enhancements
## JDBC Enhancements
## String Joiner
## Security Enhancements
## Tools Enhancements
## Pack200 Enhancements
## Networking Enhancements
## API for XML processing (JAXP) 1.6 Enhancement
## Java Virtual Machine Enhancements
## Java Mission Control 5.3
## Internationalization Enhancements
## Adoption of Unicode CLDR
## New Calendar and Locale APIs
## Version Enhancements

## Lambda Expressions
  - A Lambda Expression in Java is an anonymous function,  a function without a name, return type, or access modifier, that provides a clear and concise way to implement a Functional Interface.
Introduced in Java 8, it enables functional programming by allowing you to pass behavior as an argument into methods, significantly reducing boilerplate code.

  - They make java compiler more smart, it understand method implementation itself.
  - By using arrow we are passing the behavior of that method as well 

- traditional way: 
```java
// Addition ke liye bada code
MathOperation addition = new MathOperation() {
    @Override
    public int operate(int a, int b) {
        return a + b;
    }
};

System.out.println(addition.operate(5, 3)); // Output: 8

```
- Lambda: 

```java

// Addition ke liye chhota code
MathOperation addition = (a, b) -> a + b;

// Multiplication ke liye chhota code
MathOperation multiplication = (a, b) -> a * b;

System.out.println(addition.operate(5, 3));        // Output: 8
System.out.println(multiplication.operate(5, 3)); // Output: 15
```

- NOTE: nonymous Inner Classes are created at compile-time as separate class files, whereas Lambdas are handled at runtime using the invokedynamic bytecode instruction, making Lambdas much faster and memory-efficient.

## Functional Interfaces
- A Functional Interface in Java is an interface that contains exactly one abstract method.
It can have multiple default or static methods, but it must have strictly one abstract method.
Because it has only one unimplemented method, it is also known as a **Single Abstract Method (SAM)** Interface.

@FunctionalInterface - 
- This is an optional but highly recommended annotation. It tells the compiler to check if your interface truly has only one abstract method. If you accidentally add a second abstract method, the compiler will throw an error immediately.

Default and Static Methods:
Java 8 allowed interfaces to have implemented methods using default and static keywords. A functional interface can have any number of these methods.

Object Class Methods:
If an interface overrides any public method from the java.lang.Object class (like equals() or toString()), it does not count towards the abstract method limit.

NOTE: a Functional Interface can extend another interface. The golden rule is that after inheritance, the child interface must contain exactly one abstract method. If it inherits one and declares another, it violates the Single Abstract Method (SAM) rule and ceases to be a Functional Interface."

### Default Methods 
- A default method is a method inside an interface that has a method body and is defined using the default keyword. Introduced in Java 8, its primary purpose is to allow developers to add new methods to existing interfaces without breaking the classes that already implement those interfaces. This ensures backward compatibility while enabling structural evolution.
•  Can be overridden | Called using the object of the implementing class (obj.defaultMethod()).

### 
Static Methods
- A static method in an interface is a method that has a concrete implementation and is defined using the static keyword. Similar to static methods in a class, these methods belong to the interface itself and cannot be overridden by implementing classes. They are invoked directly using the interface name and are used to provide utility or helper functionality relevant to the interface.
• Static Methods: Cannot be overridden | Called directly using the Interface name (InterfaceName.staticMethod()).


## Default Methods in Interface


## Static Methods in Interface
## Predefined Functional Interfaces
  - Predicates
  - Functions
  - Consumer
  - Supplier
## Double colon operator (::)
## Stream API
## Stream Filter
## Date/Time API (JODA API)
## Method References
## Optional Class
## ForEach() Method
## IO Enhancements
## Type and Repeating Annotations
## Base64 Encode Decode
## Collectors Class
## Nashorn JavaScript Engine
## Parallel Array Sorting
## Concurrency Enhancements
## JDBC Enhancements
## String Joiner
## Security Enhancements
## Tools Enhancements
## Pack200 Enhancements
##- Networking Enhancements
## API for XML processing (JAXP) 1.6 Enhancement
## Java Virtual Machine Enhancements
## Java Mission Control 5.3
## Internationalization Enhancements
## Adoption of Unicode CLDR
## New Calendar and Locale APIs
## Version Enhancements
