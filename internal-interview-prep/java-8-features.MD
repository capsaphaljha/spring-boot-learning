# Java 8 Features
  - Java 8 is one of the most important releases in the history of Java.
  - Released on March 18, 2014, it introduced several major language and library enhancements that made Java programming more concise, expressive, and suitable for functional-style programming.
  - The most significant Java 8 features include Lambda Expressions, Functional Interfaces, Method References, Stream API, the Optional class, the new Date and Time API, and enhancements to interfaces and collections.

### Introduction of the Stream API for efficient data processing.
### A new Date and Time API for better handling of time and date operations.
### Default and static methods in interfaces for greater flexibility.


The following feature enhanced in Java ersion 8:

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
##- Networking Enhancements
## API for XML processing (JAXP) 1.6 Enhancement
## Java Virtual Machine Enhancements
## Java Mission Control 5.3
## Internationalization Enhancements
## Adoption of Unicode CLDR
## New Calendar and Locale APIs
## Version Enhancements
