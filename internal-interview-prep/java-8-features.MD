# Java 8 Features
  - Java 8 is one of the most important releases in the history of Java.
  - Released on March 18, 2014, it introduced several major language and library enhancements that made Java programming more concise, expressive, and suitable for functional-style programming.
  - The most significant Java 8 features include Lambda Expressions, Functional Interfaces, Method References, Stream API, the Optional class, the new Date and Time API, and enhancements to interfaces[...]

### Introduction of the Stream API for efficient data processing.
### A new Date and Time API for better handling of time and date operations.
### Default and static methods in interfaces for greater flexibility.


The following feature enhanced in Java ersion 8:

| Topic | Details |
| --- | --- |
| [Lambda Expressions](#lambda-expressions) | [Open Lambda Expressions section](#lambda-expressions) |
| [Functional Interfaces](#functional-interfaces) | [Open Functional Interfaces section](#functional-interfaces) |
| [Default Methods in Interface](#default-methods) | [Open Default Methods section](#default-methods) |
| [Static Methods in Interface](#static-methods) | [Open Static Methods section](#static-methods) |
| [Predefined Functional Interfaces](#predefined-functional-interfaces) | [Open Predefined Functional Interfaces section](#predefined-functional-interfaces) |
| [Double colon operator (::)](#double-colon-operator) | [Open Double Colon Operator section](#double-colon-operator) |
| [Stream API](#stream-api) | [Open Stream API section](#stream-api) |
| [Stream Filter](#stream-filter) | [Open Stream Filter section](#stream-filter) |
| [Date/Time API (JODA API)](#date-time-api-joda-api) | [Open Date/Time API section](#date-time-api-joda-api) |
| [Method References](#method-references) | [Open Method References section](#method-references) |
| [Optional Class](#optional-class) | [Open Optional Class section](#optional-class) |
| [ForEach() Method](#foreach-method) | [Open ForEach() Method section](#foreach-method) |
| [IO Enhancements](#io-enhancements) | [Open IO Enhancements section](#io-enhancements) |
| [Type and Repeating Annotations](#type-and-repeating-annotations) | [Open Type and Repeating Annotations section](#type-and-repeating-annotations) |
| [Base64 Encode Decode](#base64-encode-decode) | [Open Base64 section](#base64-encode-decode) |
| [Collectors Class](#collectors-class) | [Open Collectors Class section](#collectors-class) |
| [Nashorn JavaScript Engine](#nashorn-javascript-engine) | [Open Nashorn JavaScript Engine section](#nashorn-javascript-engine) |
| [Parallel Array Sorting](#parallel-array-sorting) | [Open Parallel Array Sorting section](#parallel-array-sorting) |
| [Concurrency Enhancements](#concurrency-enhancements) | [Open Concurrency Enhancements section](#concurrency-enhancements) |
| [JDBC Enhancements](#jdbc-enhancements) | [Open JDBC Enhancements section](#jdbc-enhancements) |
| [String Joiner](#string-joiner) | [Open String Joiner section](#string-joiner) |
| [Security Enhancements](#security-enhancements) | [Open Security Enhancements section](#security-enhancements) |
| [Tools Enhancements](#tools-enhancements) | [Open Tools Enhancements section](#tools-enhancements) |
| [Pack200 Enhancements](#pack200-enhancements) | [Open Pack200 Enhancements section](#pack200-enhancements) |
| [Networking Enhancements](#networking-enhancements) | [Open Networking Enhancements section](#networking-enhancements) |
| [API for XML processing (JAXP) 1.6 Enhancement](#api-for-xml-processing-jaxp-16-enhancement) | [Open JAXP section](#api-for-xml-processing-jaxp-16-enhancement) |
| [Java Virtual Machine Enhancements](#java-virtual-machine-enhancements) | [Open JVM Enhancements section](#java-virtual-machine-enhancements) |
| [Java Mission Control 5.3](#java-mission-control-53) | [Open Java Mission Control section](#java-mission-control-53) |
| [Internationalization Enhancements](#internationalization-enhancements) | [Open Internationalization section](#internationalization-enhancements) |
| [Adoption of Unicode CLDR](#adoption-of-unicode-cldr) | [Open Unicode CLDR section](#adoption-of-unicode-cldr) |
| [New Calendar and Locale APIs](#new-calendar-and-locale-apis) | [Open Calendar & Locale APIs section](#new-calendar-and-locale-apis) |
| [Version Enhancements](#version-enhancements) | [Open Version Enhancements section](#version-enhancements) |

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

- NOTE: nonymous Inner Classes are created at compile-time as separate class files, whereas Lambdas are handled at runtime using the invokedynamic bytecode instruction, making Lambdas much faster and [...]

<a id="functional-interfaces"></a>
## Functional Interfaces
- A Functional Interface in Java is an interface that contains exactly one abstract method.
It can have multiple default or static methods, but it must have strictly one abstract method.
Because it has only one unimplemented method, it is also known as a **Single Abstract Method (SAM)** Interface.

@FunctionalInterface - 
- This is an optional but highly recommended annotation. It tells the compiler to check if your interface truly has only one abstract method. If you accidentally add a second abstract method, the comp[...]

Default and Static Methods:
Java 8 allowed interfaces to have implemented methods using default and static keywords. A functional interface can have any number of these methods.

Object Class Methods:
If an interface overrides any public method from the java.lang.Object class (like equals() or toString()), it does not count towards the abstract method limit.

NOTE: a Functional Interface can extend another interface. The golden rule is that after inheritance, the child interface must contain exactly one abstract method. If it inherits one and declares[...]

<a id="default-methods"></a>
### Default Methods 
- A default method is a method inside an interface that has a method body and is defined using the default keyword. Introduced in Java 8, its primary purpose is to allow developers to add new methods [...]
•  Can be overridden | Called using the object of the implementing class (obj.defaultMethod()).

<a id="static-methods"></a>
### Static Methods
- A static method in an interface is a method that has a concrete implementation and is defined using the static keyword. Similar to static methods in a class, these methods belong to the interface it[...]
• Static Methods: Cannot be overridden | Called directly using the Interface name (InterfaceName.staticMethod()).


<a id="default-methods-in-interface"></a>
## Default Methods in Interface


<a id="static-methods-in-interface"></a>
## Static Methods in Interface
<a id="predefined-functional-interfaces"></a>
## Predefined Functional Interfaces
  - Predicates
  - Functions
  - Consumer
  - Supplier
<a id="double-colon-operator"></a>
## Double colon operator (::)
<a id="stream-api"></a>
## Stream API
<a id="stream-filter"></a>
## Stream Filter
<a id="date-time-api-joda-api"></a>
## Date/Time API (JODA API)
<a id="method-references"></a>
## Method References
<a id="optional-class"></a>
## Optional Class
<a id="foreach-method"></a>
## ForEach() Method
<a id="io-enhancements"></a>
## IO Enhancements
<a id="type-and-repeating-annotations"></a>
## Type and Repeating Annotations
<a id="base64-encode-decode"></a>
## Base64 Encode Decode
<a id="collectors-class"></a>
## Collectors Class
<a id="nashorn-javascript-engine"></a>
## Nashorn JavaScript Engine
<a id="parallel-array-sorting"></a>
## Parallel Array Sorting
<a id="concurrency-enhancements"></a>
## Concurrency Enhancements
<a id="jdbc-enhancements"></a>
## JDBC Enhancements
<a id="string-joiner"></a>
## String Joiner
<a id="security-enhancements"></a>
## Security Enhancements
<a id="tools-enhancements"></a>
## Tools Enhancements
<a id="pack200-enhancements"></a>
## Pack200 Enhancements
<a id="networking-enhancements"></a>
## Networking Enhancements
<a id="api-for-xml-processing-jaxp-16-enhancement"></a>
## API for XML processing (JAXP) 1.6 Enhancement
<a id="java-virtual-machine-enhancements"></a>
## Java Virtual Machine Enhancements
<a id="java-mission-control-53"></a>
## Java Mission Control 5.3
<a id="internationalization-enhancements"></a>
## Internationalization Enhancements
<a id="adoption-of-unicode-cldr"></a>
## Adoption of Unicode CLDR
<a id="new-calendar-and-locale-apis"></a>
## New Calendar and Locale APIs
<a id="version-enhancements"></a>
## Version Enhancements
