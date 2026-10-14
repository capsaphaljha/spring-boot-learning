# OOPs

## OOP stands for Object-Oriented Programming.
- object-oriented programming is about creating objects that contain both data and methods.

- OOP is ideal for building scalable, reusable, and maintainable code.

- Object-oriented programming has several advantages over procedural programming:

    - OOP provides a clear structure for the programs
    - OOP helps to keep the Java code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
    - OOP makes it possible to create full reusable applications with less code and shorter development time

### "Don't Repeat Yourself" (DRY)

## Classes and Objects
- A class is a template for objects, and an object is an instance of a class. 
- When the individual objects are created, they inherit all the variables and methods from the class.

A Class is like an object constructor, or a "blueprint" for creating objects.

Example of a class:

```java
// example 2
public class Main {
  int x = 5;
}

// example 2
public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}
```
example 2 main ham class ka object bana kar uski ki ek method call kar rhe hai.

### Class Attributes
- In Java, variables declared inside a class are called "attributes". You can also say that attributes are variables that belong to a class:

example:

```java 

public class Main {
  int x = 5;
  int y = 3;
}

```

#### Accessing Attributes
- You can access attributes by creating an object of the class, and by using the dot syntax (.):

```java 

public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}

```
#### Modify Attributes Or override existing values:

    myObj.x = 40;

-----
# Constructors

- A constructor in Java is a special method that is used to initialize objects.
- The constructor is called when an object of a class is created.
- It can be used to set initial values for object attributes:

example 


```java 
public class Main {
  int x;  // Create a class attribute

  // Create a class constructor for the Main class
  public Main() {
    x = 5;  // Set the initial value for the class attribute x
  }

  public static void main(String[] args) {
    Main myObj = new Main(); // Create an object of class Main (This will call the constructor)
    System.out.println(myObj.x); // Print the value of x
  }
}
```

### Note: Note that the constructor name must match the class name, and it cannot have a return type (like void).
### Note: Also note that the constructor is called when the object is created.
### All classes have constructors by default: if you do not create a class constructor yourself, Java creates one for you. However, then you are not able to set initial values for object attributes.

# Constructor Parameters
- 



