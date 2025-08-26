# Java Basics Cheat Sheet 📚

## Hello World & Setup

```java
// File name: HelloWorld.java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

### Compilation & Execution
```bash
# Compile (creates HelloWorld.class)
javac HelloWorld.java

# Run
java HelloWorld
```

## Data Types

| Type | Category | Size | Range | Default | Operators |
|------|----------|------|-------|---------|-----------|
| `byte` | Integer | 8-bit | -128 to 127 | 0 | + - * / % |
| `short` | Integer | 16-bit | -32,768 to 32,767 | 0 | + - * / % |
| `int` | Integer | 32-bit | -2³¹ to 2³¹-1 | 0 | + - * / % |
| `long` | Integer | 64-bit | -2⁶³ to 2⁶³-1 | 0L | + - * / % |
| `float` | Floating | 32-bit | ~6-7 decimal digits | 0.0f | + - * / |
| `double` | Floating | 64-bit | ~15-16 decimal digits | 0.0 | + - * / |
| `boolean` | Boolean | 1-bit | true or false | false | && \|\| ! |
| `char` | Character | 16-bit | Unicode characters | '\u0000' | |
| `String` | Reference | Variable | Sequence of characters | null | + |

## Variable Declaration & Assignment

```java
// Declaration
int a, b;
String name;

// Assignment
a = 10;
name = "Java";

// Initialization (declaration + assignment)
int c = 15;
double pi = 3.14159;
boolean isActive = true;
char grade = 'A';

// Constants
final int MAX_SIZE = 100;
final double PI = 3.14159;

// Compound assignment operators
a += 5;  // a = a + 5
a -= 3;  // a = a - 3
a *= 2;  // a = a * 2
a /= 4;  // a = a / 4
a %= 3;  // a = a % 3

// Increment/Decrement
int x = 5;
x++;     // x = 6 (post-increment)
++x;     // x = 7 (pre-increment)
x--;     // x = 6 (post-decrement)
--x;     // x = 5 (pre-decrement)
```

## Comparison & Logical Operators

| Operator | Meaning | Example |
|----------|---------|---------|
| `==` | Equal to | `a == b` |
| `!=` | Not equal to | `a != b` |
| `<` | Less than | `a < b` |
| `>` | Greater than | `a > b` |
| `<=` | Less than or equal | `a <= b` |
| `>=` | Greater than or equal | `a >= b` |
| `&&` | Logical AND | `(a > 0) && (b > 0)` |
| `\|\|` | Logical OR | `(a > 0) \|\| (b > 0)` |
| `!` | Logical NOT | `!(a > 0)` |

## Input/Output Operations

```java
import java.util.Scanner;

// Input
Scanner scanner = new Scanner(System.in);
System.out.print("Enter your name: ");
String name = scanner.nextLine();
System.out.print("Enter your age: ");
int age = scanner.nextInt();
scanner.close();

// Output
System.out.print("Hello");           // Print without newline
System.out.println("Hello World");   // Print with newline
System.out.println();                // Print blank line

// Formatted output
System.out.printf("Name: %s, Age: %d%n", name, age);
```

## String Operations

```java
String str = "Hello World";

// Common methods
int length = str.length();                    // 11
char ch = str.charAt(0);                     // 'H'
String upper = str.toUpperCase();            // "HELLO WORLD"
String lower = str.toLowerCase();            // "hello world"
String sub = str.substring(0, 5);           // "Hello"
boolean contains = str.contains("World");    // true
boolean starts = str.startsWith("Hello");   // true
boolean ends = str.endsWith("World");       // true
String replaced = str.replace("World", "Java"); // "Hello Java"
String[] parts = str.split(" ");            // ["Hello", "World"]
String trimmed = "  Hello  ".trim();        // "Hello"

// String comparison
str.equals("Hello World");        // true
str.equalsIgnoreCase("HELLO");    // false
str.compareTo("Hello World");     // 0
```

## Type Conversion & Parsing

```java
// Automatic conversions
int i = 10;
double d = i;        // int to double (automatic)

// Explicit casting
double d = 10.5;
int i = (int) d;     // double to int (explicit) - truncates to 10

// String to primitive
int num = Integer.parseInt("123");
double decimal = Double.parseDouble("3.14");
boolean bool = Boolean.parseBoolean("true");
long bigNum = Long.parseLong("12345");

// Primitive to String
String s1 = String.valueOf(123);
String s2 = Integer.toString(123);
```

## Math Library

```java
// Common Math methods
Math.abs(-5);              // 5 (absolute value)
Math.max(10, 20);         // 20 (maximum)
Math.min(10, 20);         // 10 (minimum)
Math.pow(2, 3);           // 8.0 (2^3)
Math.sqrt(16);            // 4.0 (square root)
Math.ceil(3.2);           // 4.0 (round up)
Math.floor(3.8);          // 3.0 (round down)
Math.round(3.7);          // 4 (round to nearest)
Math.random();            // Random double between 0.0 and 1.0

// Trigonometric functions
Math.sin(Math.PI / 2);    // 1.0
Math.cos(0);              // 1.0
Math.tan(Math.PI / 4);    // 1.0
Math.toRadians(180);      // π (convert degrees to radians)
Math.toDegrees(Math.PI);  // 180.0 (convert radians to degrees)

// Constants
Math.PI;                  // 3.141592653589793
Math.E;                   // 2.718281828459045
```

## Conditional Statements

```java
// If statement
if (age >= 18) {
    System.out.println("Adult");
}

// If-else statement
if (score >= 60) {
    System.out.println("Pass");
} else {
    System.out.println("Fail");
}

// If-else if ladder
if (grade >= 90) {
    System.out.println("A");
} else if (grade >= 80) {
    System.out.println("B");
} else if (grade >= 70) {
    System.out.println("C");
} else {
    System.out.println("F");
}

// Ternary operator
String result = (score >= 60) ? "Pass" : "Fail";

// Switch statement
switch (day) {
    case 1:
        dayName = "Monday";
        break;
    case 2:
        dayName = "Tuesday";
        break;
    case 3:
        dayName = "Wednesday";
        break;
    default:
        dayName = "Invalid day";
        break;
}

// Enhanced switch (Java 12+)
String dayType = switch (day) {
    case 1, 2, 3, 4, 5 -> "Weekday";
    case 6, 7 -> "Weekend";
    default -> "Invalid";
};
```

## Loop Statements

```java
// For loop
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}

// Enhanced for loop (for-each)
int[] numbers = {1, 2, 3, 4, 5};
for (int number : numbers) {
    System.out.println(number);
}

// While loop
int i = 0;
while (i < 10) {
    System.out.println(i);
    i++;
}

// Do-while loop
int j = 0;
do {
    System.out.println(j);
    j++;
} while (j < 5);

// Loop control
for (int i = 0; i < 10; i++) {
    if (i == 3) continue;    // Skip iteration
    if (i == 8) break;       // Exit loop
    System.out.println(i);
}
```

## Arrays

```java
// Array declaration and initialization
int[] numbers = new int[5];              // Array of 5 integers
int[] values = {1, 2, 3, 4, 5};         // Initialize with values
String[] names = new String[3];

// Accessing elements
numbers[0] = 10;        // Set first element
int first = numbers[0]; // Get first element
int length = numbers.length; // Get array length

// Multi-dimensional arrays
int[][] matrix = new int[3][4];          // 3x4 matrix
int[][] grid = {{1, 2}, {3, 4}, {5, 6}};

// Array operations
int[] original = {1, 2, 3};
int[] copy = Arrays.copyOf(original, original.length);
Arrays.sort(numbers);                    // Sort array
Arrays.fill(numbers, 0);                 // Fill with value
String str = Arrays.toString(numbers);   // Convert to string
```

## Exception Handling

```java
// Basic try-catch
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}

// Multiple catch blocks
try {
    int[] arr = new int[5];
    arr[10] = 100;
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array index out of bounds");
} catch (Exception e) {
    System.out.println("General exception: " + e.getMessage());
}

// Try-catch-finally
try {
    // Risky code
} catch (Exception e) {
    // Handle exception
} finally {
    // Always executes
    System.out.println("Cleanup code");
}

// Throwing exceptions
public void checkAge(int age) throws IllegalArgumentException {
    if (age < 0) {
        throw new IllegalArgumentException("Age cannot be negative");
    }
}
```

## Object-Oriented Programming

### Classes and Objects

```java
public class Person {
    // Instance variables (fields)
    private String name;
    private int age;
    
    // Static variable (class variable)
    private static int personCount = 0;
    
    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
        personCount++;
    }
    
    // Default constructor
    public Person() {
        this("Unknown", 0);
    }
    
    // Instance methods
    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
    
    public int getAge() {
        return age;
    }
    
    public void setAge(int age) {
        this.age = age;
    }
    
    // Static method
    public static int getPersonCount() {
        return personCount;
    }
    
    // Override toString method
    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + "}";
    }
}

// Creating and using objects
Person person1 = new Person("Alice", 25);
Person person2 = new Person("Bob", 30);

System.out.println(person1.getName()); // Alice
person1.setAge(26);
System.out.println(Person.getPersonCount()); // 2
```

### Inheritance

```java
// Parent class
public class Animal {
    protected String name;
    protected int age;
    
    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public void makeSound() {
        System.out.println("Animal makes a sound");
    }
    
    public void eat() {
        System.out.println(name + " is eating");
    }
}

// Child class
public class Dog extends Animal {
    private String breed;
    
    public Dog(String name, int age, String breed) {
        super(name, age);  // Call parent constructor
        this.breed = breed;
    }
    
    @Override
    public void makeSound() {
        System.out.println(name + " barks: Woof!");
    }
    
    public void wagTail() {
        System.out.println(name + " wags tail");
    }
}

// Usage
Dog myDog = new Dog("Buddy", 3, "Golden Retriever");
myDog.makeSound(); // Buddy barks: Woof! (overridden method)
myDog.eat();       // Buddy is eating (inherited method)
myDog.wagTail();   // Buddy wags tail (own method)
```

### Polymorphism

```java
// Method Overloading (Compile-time polymorphism)
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
    
    public double add(double a, double b) {
        return a + b;
    }
    
    public int add(int a, int b, int c) {
        return a + b + c;
    }
}

// Method Overriding (Runtime polymorphism)
Animal[] animals = {
    new Dog("Buddy", 3, "Labrador"),
    new Cat("Whiskers", 2, "Persian"),
    new Animal("Generic", 1)
};

for (Animal animal : animals) {
    animal.makeSound(); // Calls appropriate overridden method
}
```

### Abstraction

```java
// Abstract class
public abstract class Shape {
    protected String color;
    
    public Shape(String color) {
        this.color = color;
    }
    
    // Abstract method (must be implemented by subclasses)
    public abstract double getArea();
    
    // Concrete method
    public void printColor() {
        System.out.println("Color: " + color);
    }
}

// Concrete class
public class Circle extends Shape {
    private double radius;
    
    public Circle(String color, double radius) {
        super(color);
        this.radius = radius;
    }
    
    @Override
    public double getArea() {
        return Math.PI * radius * radius;
    }
}

// Interface
public interface Drawable {
    void draw();           // Abstract method (public by default)
    
    default void print() { // Default method (Java 8+)
        System.out.println("Printing...");
    }
    
    static void info() {   // Static method (Java 8+)
        System.out.println("Drawable interface");
    }
}

// Implementing interface
public class Rectangle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a rectangle");
    }
}
```

### Encapsulation

```java
public class BankAccount {
    private double balance;      // Private field
    private String accountNumber;
    
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }
    
    // Getter methods
    public double getBalance() {
        return balance;
    }
    
    public String getAccountNumber() {
        return accountNumber;
    }
    
    // Controlled access through methods
    public boolean deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            return true;
        }
        return false;
    }
    
    public boolean withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            return true;
        }
        return false;
    }
}
```

## Access Modifiers

| Modifier | Class | Package | Subclass | World |
|----------|-------|---------|----------|-------|
| `public` | ✓ | ✓ | ✓ | ✓ |
| `protected` | ✓ | ✓ | ✓ | ✗ |
| default (no modifier) | ✓ | ✓ | ✗ | ✗ |
| `private` | ✓ | ✗ | ✗ | ✗ |

## Non-Access Modifiers

- `static`: Belongs to class rather than instance
- `final`: Cannot be modified/overridden
- `abstract`: Must be implemented by subclass
- `synchronized`: Thread-safe access
- `volatile`: Variable may be changed by multiple threads
- `transient`: Skip during serialization

## Collections Framework Basics

```java
import java.util.*;

// ArrayList - Dynamic array
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
list.add(1, "Orange");  // Insert at index
String item = list.get(0); // Get by index
list.remove("Banana");
list.size();

// HashMap - Key-value pairs
Map<String, Integer> map = new HashMap<>();
map.put("Alice", 25);
map.put("Bob", 30);
int age = map.get("Alice");
map.containsKey("Alice");
map.keySet();   // Get all keys
map.values();   // Get all values

// HashSet - Unique elements
Set<String> set = new HashSet<>();
set.add("Red");
set.add("Blue");
set.add("Red");  // Duplicate, won't be added
set.contains("Red");
set.size(); // 2

// Enhanced for loops with collections
for (String item : list) {
    System.out.println(item);
}

for (Map.Entry<String, Integer> entry : map.entrySet()) {
    System.out.println(entry.getKey() + ": " + entry.getValue());
}
```

## Packages and Imports

```java
// Package declaration (first line of file)
package com.company.myapp;

// Import statements
import java.util.Scanner;           // Import specific class
import java.util.*;                 // Import all classes from package
import static java.lang.Math.PI;    // Static import

// Using imported classes
Scanner scanner = new Scanner(System.in);
List<String> list = new ArrayList<>();
double circumference = 2 * PI * radius; // Static import
```

## Common Utility Methods

```java
// Random numbers
Random random = new Random();
int randomInt = random.nextInt(10);      // 0-9
double randomDouble = random.nextDouble(); // 0.0-1.0

// Date and Time (Java 8+)
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

LocalDate today = LocalDate.now();
LocalDateTime now = LocalDateTime.now();
DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
String formatted = now.format(formatter);

// File operations basics
import java.io.*;
import java.nio.file.*;

// Reading file
String content = Files.readString(Paths.get("file.txt"));
List<String> lines = Files.readAllLines(Paths.get("file.txt"));

// Writing file
Files.writeString(Paths.get("output.txt"), "Hello World");
```
