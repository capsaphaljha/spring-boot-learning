
## Wrapper Classes
Wrapper classes provide a way to use primitive data types (int, boolean, etc..) as objects.
The table below shows the primitive type and the equivalent wrapper class:

Primitive Data Type	Wrapper Class
byte	Byte
short	Short
int	Integer
long	Long
float	Float
double	Double
boolean	Boolean
char	Character

### Creating Wrapper Objects
To create a wrapper object, use the wrapper class instead of the primitive type. To get the value, you can just print the object:

```java
public class Main {
  public static void main(String[] args) {
    Integer myInt = 5;
    Double myDouble = 5.99;
    Character myChar = 'A';
    System.out.println(myInt);
    System.out.println(myDouble);
    System.out.println(myChar);
  }
}
```


