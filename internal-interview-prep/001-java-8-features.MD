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

- A default method is a method inside an interface that has a method body and is defined using the default keyword. Introduced in Java 8, its primary purpose is to allow developers to add new methods to existing interfaces without breaking the classes that already implement those interfaces. This ensures backward compatibility while enabling structural evolution.
•  Can be overridden | Called using the object of the implementing class (obj.defaultMethod()).


<a id="static-methods-in-interface"></a>
## Static Methods in Interface
- A static method in an interface is a method that has a concrete implementation and is defined using the static keyword. Similar to static methods in a class, these methods belong to the interface itself and cannot be overridden by implementing classes. They are invoked directly using the interface name and are used to provide utility or helper functionality relevant to the interface.
• Static Methods: Cannot be overridden | Called directly using the Interface name (InterfaceName.staticMethod()).


<a id="predefined-functional-interfaces"></a>
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


<a id="double-colon-operator"></a>
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


<a id="stream-api"></a>
## Stream API
- Stream API is a sequence of elements supporting functional and declarative operations. 
- It allows us to process collections of data in a pipeline format without changing the original data source.
- It uses internal iteration, meaning the framework handles the looping, allowing us to focus purely on what operations to perform using intermediate methods like filter() and map(), and a terminal method like collect() or forEach()."

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamInterviewExample {
    public static void main(String[] args) {
        
        // 1. Data Source: Original list of integers
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6);

        // 2. Stream Pipeline Creation
        List<Integer> squaredEvenNumbers = numbers.stream()
            
            // Intermediate Operation 1: filter()
            // Lambda expression ka use karke sirf even numbers ko aage bhej rahe hain
            .filter(n -> n % 2 == 0) // Bachenge: [2, 4, 6]
            
            // Intermediate Operation 2: map()
            // Har even number ko uske square se replace kar rahe hain
            .map(n -> n * n) // Ho jayenge: [4, 16, 36]
            
            // Terminal Operation: collect()
            // Stream ko wapas ek List mein convert kar rahe hain (Yeh pipeline trigger karta hai)
            .collect(Collectors.toList());

        // Result print karna
        System.out.println("Squared Even Numbers: " + squaredEvenNumbers); 
        // Output: [4, 16, 36]
    }
}

```
Parallel Processing (Sabse Bada Advantage)
- Agar aapke paas millions of records hain, toh Stream API aapko bina koi complex multithreading code likhe, data ko parallel process karne ki taqat deta hai.
- Aapko bas .stream() ki jagah .parallelStream() likhna hota hai.
- Java ka JVM khud-b-khud aapke computer ke multiple CPU cores par kaam baant deta hai.
- Loop mein agar aapko yeh karna pade, toh aapko khud threads aur synchronization likhni padegi jo ki bahut mushkil hota hai.

<a id="stream-filter"></a>
## Stream Filter

The filter() method is an intermediate stream operation that accepts a Predicate<T> functional interface and returns a new stream containing only the elements that match the given condition. Advanced usage involves combining multiple conditions using Predicate.and() or Predicate.or() for reusability, ensuring the filter logic remains strictly stateless (especially for parallel streams), and leveraging lazy evaluation for short-circuiting performance.

```java
import java.util.Arrays;
import java.util.List;
import java.util.Objects;
import java.util.function.Predicate;
import java.util.stream.Collectors;

class Employee {
    String name;
    String department;
    double salary;

    public Employee(String name, String department, double salary) {
        this.name = name;
        this.department = department;
        this.salary = salary;
    }

    public String getDepartment() { return department; }
    public double getSalary() { return salary; }
    public String getName() { return name; }
}

public class AdvancedFilterExample {
    public static void main(String[] args) {
        
        // 1. Data Source (Kuch null values ke sath)
        List<Employee> employees = Arrays.asList(
            new Employee("Aman", "IT", 75000),
            null, // Null object jo NullPointerException de sakta hai
            new Employee("Rahul", "HR", 45000),
            new Employee("Ankit", "IT", 90000),
            new Employee("Neha", "IT", 60000)
        );

        // 2. Advanced Predicates banana (Reusability ke liye)
        // Condition 1: Employee null nahi hona chahiye
        Predicate<Employee> isNotNull = Objects::nonNull;

        // Condition 2: Department "IT" hona chahiye
        Predicate<Employee> isITDept = e -> e.getDepartment().equals("IT");

        // Condition 3: Salary 70,000 se zyada honi chahiye
        Predicate<Employee> isHighEarner = e -> e.getSalary() > 70000;

        // 3. Predicates ko combine karna (.and() ka use karke) aur Filter lagana
        List<String> eliteITEmployees = employees.stream()
            .filter(isNotNull) // Pehle null hata diya taaki NPE na aaye
            .filter(isITDept.and(isHighEarner)) // Advanced: Multiple predicates ko combine kiya
            .map(Employee::getName) // Sirf names nikal liye
            .collect(Collectors.toList()); // Terminal operation

        // Result print karna
        System.out.println("Elite IT Employees: " + eliteITEmployees); 
        // Output: [Aman, Ankit]
    }
}

```


<a id="date-time-api-joda-api"></a>
## Date/Time API (JODA API)

The Java 8 Date and Time API (java.time), heavily inspired by Joda-Time, provides a modern, immutable, and thread-safe way to handle date and time operations.
Unlike the legacy java.util.Date which was mutable and had confusing indexing, the new API introduces clear domain-specific classes like LocalDate, LocalTime, and LocalDateTime along with powerful tools for parsing, formatting, and calculating intervals using Period and Duration.

LocalDate: Sirf date ke liye (e.g., 2026-10-20). Isme time nahi hota.

LocalTime: Sirf time ke liye (e.g., 14:30:00). Isme date nahi hoti.

LocalDateTime: Date aur Time dono ke liye, bina kisi timezone ke (e.g., 2026-10-20T14:30:00).

ZonedDateTime: Date, Time, aur Timezone ke sath (e.g., IST, UTC).

Period & Duration: Do dates ya times ke beech ka difference nikalne ke liye.

```java
import java.time.LocalDate;
import java.time.LocalTime;
import java.time.LocalDateTime;
import java.time.Period;
import java.time.format.DateTimeFormatter;

public class DateTimeInterviewExample {
    public static void main(String[] args) {
        
        // 1. Current Date aur Time lena
        LocalDate currentDate = LocalDate.now();
        LocalTime currentTime = LocalTime.now();
        LocalDateTime currentDateTime = LocalDateTime.now();
        
        System.out.println("Current Date: " + currentDate);
        System.out.println("Current Time: " + currentTime);

        // 2. Date manipulation (Jaise 5 din aage ki date nikalna)
        LocalDate futureDate = currentDate.plusDays(5);
        System.out.println("Date after 5 days: " + futureDate);

        // 3. Do Dates ke beech ka difference (Period ka use karke)
        LocalDate birthDate = LocalDate.parse("2000-05-15");
        LocalDate today = LocalDate.now();
        
        Period age = Period.between(birthDate, today);
        System.out.println("Age: " + age.getYears() + " years");

        // 4. Date Formatting (Apne marzi ke format mein convert karna)
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");
        String formattedDateTime = currentDateTime.format(formatter);
        
        System.out.println("Formatted Date-Time: " + formattedDateTime);
    }
}
```

<a id="method-references"></a>
## Method References

A Method Reference in Java 8 is a feature that provides a highly readable and compact way to refer to an existing method without executing it. It acts as a shorthand syntax for a Lambda Expression that only calls a single, predefined method. Identified by the double colon (::) operator, it enhances code readability and promotes the reuse of existing logic by mapping directly to a functional interface

like below
• Lambda: (a, b) -> Integer.compare(a, b)
• Method Reference: Integer::compare


```java
import java.util.Arrays;
import java.util.List;

public class MethodRefDemo {
    public static void main(String[] args) {
        List<String> frameworkList = Arrays.asList("Spring", "Hibernate", "Struts");

        // 1. Standard Lambda Expression approach
        frameworkList.forEach(name -> System.out.println(name));

        // 2. Optimized Method Reference approach (Cleaner & Professional)
        frameworkList.forEach(System.out::println);
    }
}
```

<a id="optional-class"></a>
## Optional Class

The Optional<T> class in Java 8 is a container object introduced in the java.util package to represent the presence or absence of a non-null value.
It was primarily designed to reduce the risk of NullPointerException (NPE) and to encourage developers to design cleaner APIs without explicitly returning or checking for null.
It forces the calling code to consciously handle the case where a value might be missing, leading to more robust and readable code.

Without optinal class you get an error
```java 
public String getUserEmail(String userId) {
    User user = database.find(userId); 
    return user.getEmail(); // If user is null, this throws NullPointerException!
}
```

with optional class there will not be any error:

```java 
import java.util.Optional;

public Optional<String> getUserEmail(String userId) {
    User user = database.find(userId);
    
    // Returns an empty Optional box if user/email is null, otherwise wraps the email
    return Optional.ofNullable(user != null ? user.getEmail() : null);
}
```

<a id="foreach-method"></a>
## ForEach() Method

The forEach() method, introduced in Java 8, is a terminal operation defined in the Iterable interface and the Stream interface. It provides a functional approach to iterate over a collection or a stream by accepting a Consumer functional interface as an argument. Unlike traditional for or foreach loops, it abstracts the internal iteration mechanism, allowing Java to optimize data traversal and making the code highly concise and readable.

```java
import java.util.Arrays;
import java.util.List;

public class ForEachListDemo {
    public static void main(String[] args) {
        List<String> javaFeatures = Arrays.asList("Lambda", "Streams", "Optional", "forEach");

        // 1. Using Lambda Expression
        javaFeatures.forEach(feature -> System.out.println("Feature: " + feature));

        // 2. Combining with Method Reference (Cleaner approach)
        javaFeatures.forEach(System.out::println);
    }
}
```


<a id="io-enhancements"></a>
## IO Enhancements
- Java 8 introduced significant IO Enhancements by bridging the gap between the standard java.io / java.nio packages and the newly introduced Stream API. Key updates include additions to the java.nio.file.Files class, such as Files.lines(), Files.walk(), and Files.find(). These methods return lazily-populated streams of lines or file paths, allowing developers to read, filter, and process large files and directory trees efficiently with minimal memory overhead.

NOTE: Before, when java loading large file there was an error OutOfMemoryError but now it read line by line

```java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.stream.Stream;

public class IOReadDemo {
    public static void main(String[] args) {
        String filePath = "app.log";

        // Try-with-resources automatically closes the stream and file handle
        try (Stream<String> lines = Files.lines(Paths.get(filePath))) {
            
            // Filter error logs and print them efficiently
            lines.filter(line -> line.contains("ERROR"))
                 .forEach(System.out::println);

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

```

- difference between Files.list() and Files.walk()?
Files.list() sirf immediate directory items ko lazy stream me fetch karta hai (Non-recursive).
Jabki Files.walk() deep down poore folder structure ko traverse karta hai (Recursive traversal).


<a id="type-and-repeating-annotations"></a>
## Type and Repeating Annotations

- Type Annotations (JSR 308) allow annotations to be applied anywhere a type is used—such as during object creation, type casting, or generic type arguments—enabling stronger compile-time type checking.
- Repeating Annotations allow the same annotation type to be applied multiple times to a single code element, eliminating the need to manually wrap them inside a container annotation, which results in cleaner and more readable code.


Example 1: Type Annotations (Usage places)

```java

import java.util.List;
import java.lang.annotation.Target;
import java.lang.annotation.ElementType;

// Defining a custom type annotation
@Target(ElementType.TYPE_USE) // Crucial: TYPE_USE allows it everywhere
@interface NonEmpty {}

public class TypeAnnotationDemo {
    public static void main(String[] args) {
        // 1. With Object Creation
        Object myObject = new @NonEmpty String("Java 8");

        // 2. With Type Casting
        String str = (@NonEmpty String) myObject;

        // 3. With Generic Type Arguments
        List<@NonEmpty String> names;
    }
}
```

```java
Example 2: Repeating Annotations (The Modern Way)

import java.lang.annotation.Repeatable;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;

// Step 1: Create the Container Annotation
@Retention(RetentionPolicy.RUNTIME)
@interface Roles {
    Role[] value(); // This holds the array of repeating annotations
}

// Step 2: Create the actual annotation and link it to the container
@Repeatable(Roles.class)
@Retention(RetentionPolicy.RUNTIME)
@interface Role {
    String value();
}

// Step 3: Apply it multiple times cleanly!
@Role("ADMIN")
@Role("MANAGER")
public class EmployeeDashboard {
    // Code logic here
}

```


<a id="base64-encode-decode"></a>
## Base64 Encode Decode
Prior to Java 8, developers had to rely on unsupported internal classes like sun.misc.BASE64Encoder or external libraries like Apache Commons Codec to handle Base64 operations.
Java 8 introduced a standardized, highly optimized utility class called java.util.Base64.
This class provides static factory methods to obtain three distinct types of encoders and decoders: Basic, URL-safe, and MIME.
It allows binary data to be safely converted into a printable ASCII string format and back, ensuring safe data transmission across text-based protocols.

```java 
import java.util.Base64;
import java.nio.charset.StandardCharsets;

public class Base64Demo {
    public static void main(String[] args) {
        String originalText = "Java 8 Features & Enhancements!";
        
        // ==========================================
        // 1. BASIC ENCODER & DECODER
        // ==========================================
        // Encoding
        String basicEncoded = Base64.getEncoder().encodeToString(originalText.getBytes(StandardCharsets.UTF_8));
        System.out.println("Basic Encoded: " + basicEncoded);
        
        // Decoding
        byte[] decodedBytes = Base64.getDecoder().decode(basicEncoded);
        String basicDecoded = new String(decodedBytes, StandardCharsets.UTF_8);
        System.out.println("Basic Decoded: " + basicDecoded);


        // ==========================================
        // 2. URL SAFE ENCODER & DECODER
        // ==========================================
        String urlWithSpecialChars = "https://mywebsite.com";
        
        // Encoding (Replaces '/' and '+' cleanly)
        String urlEncoded = Base64.getUrlEncoder().encodeToString(urlWithSpecialChars.getBytes(StandardCharsets.UTF_8));
        System.out.println("URL Safe Encoded: " + urlEncoded);
        
        // Decoding
        byte[] urlDecodedBytes = Base64.getUrlDecoder().decode(urlEncoded);
        String urlDecoded = new String(urlDecodedBytes, StandardCharsets.UTF_8);
        System.out.println("URL Safe Decoded: " + urlDecoded);
    }
}
```


<a id="collectors-class"></a>
## Collectors Class
- 
The Collectors class in Java 8 is a final utility class located in the java.util.stream package.
It consists exclusively of static factory methods that return a Collector implementation.
These collectors are primarily used as arguments in a Stream's terminal .collect() operation to perform mutable reduction operations—such as accumulating elements into collections (like Lists, Sets, or Maps), concatenating strings, partitioning data, or grouping elements based on complex classification functions.



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
