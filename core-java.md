
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

##


##

##


##

##

