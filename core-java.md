
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



## 




##

##


##

##


##

##


##

##


##

##

