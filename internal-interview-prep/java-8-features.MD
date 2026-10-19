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

## Default Methods in Interface

- A default method is a method inside an interface that has a method body and is defined using the default keyword. Introduced in Java 8, its primary purpose is to allow developers to add new methods to existing interfaces without breaking the classes that already implement those interfaces. This ensures backward compatibility while enabling structural evolution.
•  Can be overridden | Called using the object of the implementing class (obj.defaultMethod()).

## Static Methods in Interface
- A static method in an interface is a method that has a concrete implementation and is defined using the static keyword. Similar to static methods in a class, these methods belong to the interface itself and cannot be overridden by implementing classes. They are invoked directly using the interface name and are used to provide utility or helper functionality relevant to the interface.
• Static Methods: Cannot be overridden | Called directly using the Interface name (InterfaceName.staticMethod()).

## Predefined Functional Interfaces
  - Predicates
  - Functions
  - Consumer
  - Supplier

- Java 8 provides these ready-made interfaces so that you don't have to create custom interfaces every time you write a Lambda expression.

### Predicates -  A Predicate represents a boolean-valued function of one argument. It is strictly used for conditional checking or filtering.
• Abstract Method: boolean test(T t)
• Input: Takes one argument of type T.
• Output: Always returns a boolean (true or false).
• Interview Definition: "A Predicate is a functional interface that takes an input object, evaluates a condition on it, and returns a boolean value. It is widely used in filtering data streams."

Example: 

```java
import java.util.function.Predicate;

public class PredicateDemo {
    public static void main(String[] args) {
        // Lambda to check if a string length is greater than 5
        Predicate<String> isLongString = str -> str.length() > 5;

        // Calling the abstract method 'test()'
        System.out.println(isLongString.test("Java"));       // Output: false
        System.out.println(isLongString.test("Functional")); // Output: true
    }
}

```

### Functions - A Function represents an operation that accepts one argument and produces a result. It is used for transforming or mapping data from one type to another.
• Abstract Method: R apply(T t)
• Input: Takes one argument of type T.
• Output: Returns a result of type R (can be the same type or a totally different type).
• Interview Definition: "A Function interface is used for data transformation. It accepts an argument of type T, processes it, and maps it to a return value of type R."

```java
import java.util.function.Function;

public class FunctionDemo {
    public static void main(String[] args) {
        // Lambda to convert a String into an Integer (calculates length)
        // Takes String (T), Returns Integer (R)
        Function<String, Integer> stringLength = str -> str.length();

        // Calling the abstract method 'apply()'
        System.out.println(stringLength.apply("Interview")); // Output: 9
    }
}
```

### Consumer - A Consumer represents an operation that accepts a single input argument and returns no result. It is used when you want to consume, modify, or print data without returning anything.
• Abstract Method: void accept(T t)
• Input: Takes one argument of type T.
• Output: Returns void (Nothing).
• Interview Definition: "A Consumer is a functional interface that accepts a single input to perform an operation, such as printing or saving to a database, without returning any result."

```java
import java.util.function.Consumer;

public class ConsumerDemo {
    public static void main(String[] args) {
        // Lambda to print a message in uppercase
        Consumer<String> upperPrinter = str -> System.out.println(str.toUpperCase());

        // Calling the abstract method 'accept()'
        upperPrinter.accept("hello java"); // Output: HELLO JAVA
    }
}
```


# Supplier - A Supplier represents a supplier of results. It does not accept any arguments but produces a value. It is primarily used for lazy generation or creation of objects.
• Abstract Method: T get()
• Input: Takes no arguments.
• Output: Returns a value of type T.
• Interview Definition: "A Supplier takes no input arguments but supplies a value of a specified type. It is commonly used for generating random values, current timestamps, or factory patterns."
example:

```java
import java.util.function.Supplier;

public class SupplierDemo {
    public static void main(String[] args) {
        // Lambda to generate a random decimal value
        Supplier<Double> randomValue = () -> Math.random();

        // Calling the abstract method 'get()'
        System.out.println(randomValue.get()); // Output: A random number (e.g., 0.6542...)
    }
}
```
*** Lazy Initialization


## Double colon operator (::)
- The Double Colon Operator (::) in Java is known as a Method Reference. It is a syntactical shortcut for a lambda expression that solely invokes an existing method. It makes the code more readable and compact by referencing methods directly by their names without executing them or passing explicit arguments.

```java

import java.util.Arrays;
import java.util.List;

public class MethodReferenceDemo {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Amit", "Rahul", "Priya");

        // Tarika 1: Normal Lambda Expression
        System.out.println("--- Using Lambda ---");
        names.forEach(name -> System.out.println(name));

        // Tarika 2: Using Double Colon Operator (Method Reference)
        System.out.println("--- Using Method Reference ---");
        names.forEach(System.out::println);
    }
}


```


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
