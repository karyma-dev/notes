# Java

Java is an object oriented static typed language.

## Data Types

Primitive Data types, unchangable

-   int : Whole numbers, holds positive, negative numbers and zero
-   double: Holds decimal numbers. The maximum value is 1.797,693,134,862,315,7 E+308, which is approximately 17 followed by 307 zeros. The minimum value is 4.9 E-324, which is 324 decimal places
-   float : floating decimal point
-   boolean : true or false
-   char : a single character must be surrounded by single quotations
-   String: stores multiple characters using double quotations

## Comments

-   // : Single-line Comments
-   /\* \*/ : Multi-line Comments

## Operators

-   < : less than
-   \> : greater than
-   != : not equal to
-   == : equal to
-   && : and
-   || : or

### Conditionals and Control Flows

```Java
if() {
} else if {
  // Do Something
} else {
  // Do Something
}

switch(condition){
  case a:
    // Do Something
    break;
  default:
    // Do Something
    break;
}
```

### Array and ArrayList

```Java
// x speciify max length of array
String[] names = new String[x];

int[] nums = {1,2,3,4,5};

names[2] = "kary";
```

```Java
//To print out arrays
import java.util.Arrays

Arrays.toString(names);
```

ArrayList

```Java
import java.util.ArrayList

// <Integer> are generics, Generics are a Java construct that allows us to define classes and objects as parameters of an ArrayList
ArrayList<Integer> myArr = new ArrayList<Integer>();

myArr.add(); // Adds item to end of array
myArr.size(); // Returns the length of array
myArr.get(x); // Returns item in x index
myArr.set(x, value); // Changes in the value in x index;
myArr.remove(x); // x can be index or value;
myArr.indexOf(value) // return index with value;
```

### Loops

```Java
for(int i = 0; i <= arr.length; i++){
}

// For each loops through all elements in an array, same as above
int counter = 0;
for(int element: arr){
  counter++;
}

while(x != 10) {

}

do {

} while ();
```

### Utilities

Scanner

```Java
  import java.util.Scanner;

  Scanner sc = new Scanner(System.in);
```

```Java
  int[] nums = {5,15,3,6,12,6,1,4};

  //sorts and modifies the original array
  Arrays.sort(nums);

  for(int i:nums) {
    System.out.println(i);
  }

  // This will print out the reference in memory
  System.out.println(nums);
```

### Debugging

Syntax errors: Errors found by the compiler.
Run-time errors: Errors that occur when the program is running.
Logic errors: Errors found by the programmer looking for the causes of erroneous results.

When we are writing Java programs, the compiler is our first line of defense against errors. It can catch syntax errors. Syntax errors represent grammar errors in the use of the programming language. They are the easiest to find and correct. The compiler will tell you where it got into trouble, and its best guess as to what you did wrong.

Errors which happen during program execution (run-time) after successful compilation are called run-time errors. Run-time errors occur when a program with no compile-time errors asks the computer to do something that the computer is unable to reliably do. Exceptions are the conditions that occur at runtime and may cause the termination of the program. When an exception occurs, Java displays a message that includes the name of the exception, the line of the program where the exception occurred, and a stack trace.

```Java
public class Debug {
  public static void main(String[] args) {

    int width = 0;
    int length = 40;

    try {
      int ratio = length / width;
    } catch(ArithmeticException e) {
      System.err.println("ArithmeticException: " + e.getMessage());
    }
  }
}
```
