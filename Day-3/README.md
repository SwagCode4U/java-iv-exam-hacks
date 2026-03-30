# 📚 Day 3: Interface & Abstract Class

![Java](https://img.shields.io/badge/Java-Interface%20%26%20Abstract-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%203-success?style=for-the-badge)
![Duration](https://img.shields.io/badge/Duration-5%20Hours-yellow?style=for-the-badge)

> *Mastering the art of abstraction in Java!*

---

## 🌟 Welcome to Day 3!

Today we learn about two powerful concepts in Java - **Abstract Classes** and **Interfaces**. These help us achieve abstraction and solve the "multiple inheritance" problem!

**Estimated Time:** 5 Hours  
**Prerequisites:** Days 1 & 2  
**Goal:** Understand abstraction, interfaces, and when to use what

---

## 📖 Table of Contents

1. [Abstraction - The Concept](#abstraction---the-concept)
2. [Abstract Classes](#abstract-classes)
3. [Interfaces](#interfaces)
4. [Interface vs Abstract Class](#interface-vs-abstract-class)
5. [Multiple Inheritance with Interfaces](#multiple-inheritance-with-interfaces)
6. [Practice Questions](#-practice-questions)
7. [Quick Reference](#-quick-reference)

---

## 🎭 Abstraction - The Concept

### What is Abstraction?

**Abstraction** = Hiding implementation details and showing only essential features to the user.

### Real-World Examples:

```
┌─────────────────────────────────────────────────────────────┐
│                    EXAMPLE 1: ATM                          │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   What You See (Abstract):                                 │
│   ┌───────────────────────────────┐                       │
│   │  INSERT CARD  ─────►  DONE   │                       │
│   └───────────────────────────────┘                       │
│                                                             │
│   What's Hidden (Implementation):                          │
│   ❌ Database queries                                      │
│   ❌ Transaction processing                               │
│   ❌ Network communication                               │
│   ❌ Security algorithms                                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                  EXAMPLE 2: CAR DRIVING                    │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   What Driver Does (Abstract):                             │
│   ✅ Press Accelerator                                     │
│   ✅ Press Brake                                           │
│   ✅ Turn Steering                                         │
│   ✅ Change Gears                                          │
│                                                             │
│   What Car Does Internally (Hidden):                       │
│   ❌ Fuel injection system                                │
│   ❌ Gear shifting mechanism                              │
│   ❌ ABS braking system                                    │
│   ❌ Power steering pump                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Two Ways to Achieve Abstraction in Java:

```
┌─────────────────────────────────────────────┐
│              ABSTRACTION IN JAVA             │
│                                             │
│   ┌─────────────────┐                     │
│   │ Abstract Class   │  0% to 100%         │
│   │ (0-100%)        │                     │
│   └─────────────────┘                     │
│                                             │
│   ┌─────────────────┐                     │
│   │ Interface       │  100% ONLY          │
│   │ (100%)          │                     │
│   └─────────────────┘                     │
│                                             │
└─────────────────────────────────────────────┘
```

---

## 🟡 Abstract Classes

### What is an Abstract Class?

An abstract class is a class declared with the `abstract` keyword. It **may or may not** contain abstract methods (methods without body).

### Key Points:
```
✅ Can have abstract methods (without body)
✅ Can have non-abstract methods (with body)
✅ Can have constructors
✅ Can have instance variables
❌ Cannot be instantiated directly
❌ Cannot create objects
```

### Abstract Method:
```java
// Method without body - must be implemented by subclasses
abstract void draw();        // No implementation
abstract int calculate();   // No implementation
```

### Non-Abstract (Concrete) Method:
```java
// Method with body - optional to override
void display() {
    System.out.println("Display method");
}
```

### Complete Example:
```java
// ========== ABSTRACT CLASS ==========
abstract class Shape {
    String color;
    
    // Constructor - ALLOWED in abstract class
    Shape(String c) {
        color = c;
        System.out.println("Shape constructor called");
    }
    
    // Abstract method - NO body
    abstract double calculateArea();
    
    // Concrete method - HAS body
    void displayColor() {
        System.out.println("Color: " + color);
    }
}

// ========== CONCRETE CLASS 1 ==========
class Circle extends Shape {
    double radius;
    
    Circle(String c, double r) {
        super(c);  // Call parent constructor
        radius = r;
    }
    
    // MUST implement abstract method
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}

// ========== CONCRETE CLASS 2 ==========
class Rectangle extends Shape {
    double width, height;
    
    Rectangle(String c, double w, double h) {
        super(c);
        width = w;
        height = h;
    }
    
    // MUST implement abstract method
    double calculateArea() {
        return width * height;
    }
}

// ========== MAIN CLASS ==========
public class AbstractDemo {
    public static void main(String args[]) {
        // Cannot instantiate abstract class
        // Shape s = new Shape();  // ❌ ERROR!
        
        // Create concrete class objects
        Shape s1 = new Circle("Red", 5);
        Shape s2 = new Rectangle("Blue", 4, 6);
        
        s1.displayColor();
        s2.displayColor();
        
        System.out.println("Circle Area: " + s1.calculateArea());
        System.out.println("Rectangle Area: " + s2.calculateArea());
    }
}
```

### Abstract Class Rules:
```java
// Rule 1: Cannot instantiate
abstract class Demo {
    Demo() { }  // Constructor allowed
}
Demo d = new Demo();  // ❌ ERROR!

// Rule 2: Can have both abstract and concrete methods
abstract class Demo {
    abstract void method1();  // Abstract - no body
    void method2() { }        // Concrete - has body
}

// Rule 3: If class has abstract method, class must be abstract
class Demo {
    abstract void method();  // ❌ ERROR! Class must be abstract
}

// Rule 4: Can have constructors
abstract class Demo {
    Demo() { }  // ✅ OK
}
```

---

## 🔵 Interfaces

### What is an Interface?

An interface is a **100% abstract** blueprint that contains only abstract methods and constants. It's used to achieve **abstraction** and **multiple inheritance**.

### Key Points:
```
✅ 100% abstraction (only abstract methods)
✅ Variables are: public static final (constants)
✅ Methods are: public abstract
❌ Cannot have constructors
❌ Cannot have instance variables
❌ Cannot be instantiated
✅ Can be implemented by multiple classes
✅ One class can implement multiple interfaces
```

### Interface Syntax:
```java
interface InterfaceName {
    // By default: public static final (constants)
    int MAX_SPEED = 120;
    String VERSION = "1.0";
    
    // By default: public abstract (methods)
    void start();
    void stop();
    void accelerate();
}
```

### Simple Interface Example:
```java
// ========== INTERFACE ==========
interface Drawable {
    // Variables: public static final by default
    int MAX_SIZE = 100;  // Same as: public static final int MAX_SIZE = 100;
    
    // Methods: public abstract by default
    void draw();  // Same as: public abstract void draw();
}

// ========== IMPLEMENTATION ==========
class Rectangle implements Drawable {
    public void draw() {  // Must be public!
        System.out.println("Drawing Rectangle");
    }
}

class Circle implements Drawable {
    public void draw() {  // Must be public!
        System.out.println("Drawing Circle");
    }
}

// ========== MAIN ==========
public class InterfaceDemo {
    public static void main(String args[]) {
        Drawable d;  // Interface reference
        
        d = new Rectangle();
        d.draw();  // Drawing Rectangle
        
        d = new Circle();
        d.draw();  // Drawing Circle
    }
}
```

### Interface Declaration and Implementation:
```
┌─────────────────────────────────────────────────────────────┐
│                 INTERFACE DECLARATION                       │
│                                                             │
│   interface Drawable {                                     │
│       void draw();                                         │
│       int getArea();                                       │
│   }                                                        │
│                                                             │
│              │ implements                                   │
│              ↓                                             │
│   ┌─────────────────────┐  ┌─────────────────────┐        │
│   │ class Rectangle     │  │ class Circle        │        │
│   │ implements Drawable │  │ implements Drawable │        │
│   └─────────────────────┘  └─────────────────────┘        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## ⚖️ Interface vs Abstract Class

### Side-by-Side Comparison:

| Feature | Abstract Class | Interface |
|---------|--------------|-----------|
| **Methods** | Abstract + Concrete | Only abstract (Java 7) |
| **Variables** | Any type | public static final only |
| **Constructors** | ✅ Allowed | ❌ Not allowed |
| **Access Modifiers** | All | Only public |
| **Multiple Inheritance** | ❌ Not supported | ✅ Supported |
| **Speed** | Faster | Slightly slower |
| **Inheritance Keyword** | extends | implements |
| **When to use** | "is-a" relationship | "can-do" capability |

### When to Use Abstract Class:
```java
// When you want to share code among related classes
// When you need constructors for initialization
// When you need non-abstract methods

abstract class Animal {
    String name;
    
    Animal(String n) {  // Constructor - OK
        name = n;
    }
    
    void eat() {  // Concrete - shared implementation
        System.out.println(name + " is eating");
    }
    
    abstract void sound();  // Abstract - each animal different
}

class Dog extends Animal {
    Dog(String n) {
        super(n);
    }
    
    void sound() {
        System.out.println("Woof!");
    }
}
```

### When to Use Interface:
```java
// When defining capabilities/contracts
// When you need multiple inheritance
// When unrelated classes share common behavior

interface Printable {
    void print();
}

interface Drawable {
    void draw();
}

interface Exportable {
    void export();
}

// One class can implement multiple interfaces
class Report implements Printable, Drawable, Exportable {
    public void print() {
        System.out.println("Printing Report");
    }
    
    public void draw() {
        System.out.println("Drawing Report");
    }
    
    public void export() {
        System.out.println("Exporting Report");
    }
}
```

### Visual Comparison:
```
┌─────────────────────────────────────────────────────────────┐
│                 ABSTRACT CLASS                               │
│                                                             │
│   abstract class Vehicle {                                  │
│       String brand;           ← Instance variables OK       │
│       Vehicle() { }           ← Constructor OK              │
│       void start() { }        ← Concrete method OK          │
│       abstract void stop();   ← Abstract method OK          │
│   }                                                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                    INTERFACE                                │
│                                                             │
│   interface Vehicle {                                       │
│       int MAX_SPEED = 120;    ← Only constants!            │
│       // No constructors!                                 │
│       void start();           ← Only abstract methods!     │
│       void stop();            ← No concrete methods!       │
│   }                                                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 🌟 Multiple Inheritance with Interfaces

### The Problem:
```java
// ❌ Java doesn't allow multiple inheritance with classes!
class A { }
class B { }
class C extends A, B { }  // ERROR!
```

### The Solution - Interfaces:
```java
// ✅ Multiple interfaces are ALLOWED!
interface A { 
    void methodA(); 
}

interface B { 
    void methodB(); 
}

// One class can implement multiple interfaces
class C implements A, B {
    public void methodA() {
        System.out.println("Method A");
    }
    
    public void methodB() {
        System.out.println("Method B");
    }
}
```

### Interface Extending Interface:
```java
// Parent interfaces
interface Printable {
    void print();
}

interface Showable {
    void show();
}

// Child interface extends multiple parents!
interface Document extends Printable, Showable {
    void edit();
}

// Implementation must implement ALL methods
class Report implements Document {
    public void print() {
        System.out.println("Printing");
    }
    
    public void show() {
        System.out.println("Showing");
    }
    
    public void edit() {
        System.out.println("Editing");
    }
}
```

### Complete Real-World Example:
```java
// ========== INTERFACES ==========
interface Bank {
    void deposit(double amount);
    void withdraw(double amount);
    double getBalance();
}

interface Printable {
    void printStatement();
}

interface Taxable {
    void calculateTax();
}

// ========== IMPLEMENTATION ==========
class SavingsAccount implements Bank, Printable, Taxable {
    private double balance;
    
    SavingsAccount(double initial) {
        balance = initial;
    }
    
    public void deposit(double amount) {
        balance += amount;
        System.out.println("Deposited: " + amount);
    }
    
    public void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: " + amount);
        }
    }
    
    public double getBalance() {
        return balance;
    }
    
    public void printStatement() {
        System.out.println("Statement - Balance: " + balance);
    }
    
    public void calculateTax() {
        double tax = balance * 0.10;
        System.out.println("Tax: " + tax);
    }
}

// ========== MAIN ==========
public class MultiInterfaceDemo {
    public static void main(String args[]) {
        SavingsAccount acc = new SavingsAccount(10000);
        
        acc.deposit(5000);
        acc.withdraw(2000);
        
        acc.printStatement();
        acc.calculateTax();
    }
}
```

---

## 🎯 Practice Questions

### MCQs:

**Q1. Which achieves 100% abstraction?**
- A) Abstract class
- B) **Interface** ✅
- C) Both
- D) None

**Q2. Can an interface have a constructor?**
- A) Yes
- B) **No** ✅
- C) Only in Java 8
- D) Only with default

**Q3. How many interfaces can a class implement?**
- A) One
- B) Two
- C) **Unlimited** ✅
- D) Zero

**Q4. Interface variables are by default:**
- A) private
- B) protected
- C) **public static final** ✅
- D) instance

**Q5. Which is NOT true about abstract class?**
- A) Can have abstract methods
- B) Can have concrete methods
- C) **Can be instantiated** ✅
- D) Can have constructors

---

### Predict the Output:

**Q6.**
```java
interface A {
    void show();
}

class Demo implements A {
    public void show() {
        System.out.println("Show method");
    }
}

public class Test {
    public static void main(String args[]) {
        A a = new Demo();
        a.show();
    }
}
// Answer: Show method
```

**Q7.**
```java
abstract class Parent {
    Parent() {
        System.out.println("Parent Constructor");
    }
    
    abstract void show();
}

class Child extends Parent {
    Child() {
        System.out.println("Child Constructor");
    }
    
    void show() {
        System.out.println("Show method");
    }
}

public class Test {
    public static void main(String args[]) {
        Parent p = new Child();
        p.show();
    }
}
// Answer:
// Parent Constructor
// Child Constructor
// Show method
```

---

### Coding Questions:

**Q8. Write a program demonstrating abstract class:**
```java
abstract class Shape {
    abstract double area();
    void display() {
        System.out.println("Shape");
    }
}

class Triangle extends Shape {
    double base, height;
    
    Triangle(double b, double h) {
        base = b;
        height = h;
    }
    
    double area() {
        return 0.5 * base * height;
    }
}

public class ShapeDemo {
    public static void main(String args[]) {
        Shape s = new Triangle(10, 5);
        s.display();
        System.out.println("Area: " + s.area());
    }
}
```

**Q9. Write a program demonstrating multiple interfaces:**
```java
interface Printable {
    void print();
}

interface Showable {
    void show();
}

class Document implements Printable, Showable {
    public void print() {
        System.out.println("Printing document");
    }
    
    public void show() {
        System.out.println("Showing document");
    }
}

public class MultiInterfaceDemo {
    public static void main(String args[]) {
        Document doc = new Document();
        doc.print();
        doc.show();
    }
}
```

---

## 📋 Quick Reference

### Abstraction Comparison:

| Aspect | Abstract Class | Interface |
|--------|--------------|-----------|
| Methods | Both | Only abstract |
| Variables | Any | Constants only |
| Constructor | ✅ | ❌ |
| Multiple Inheritance | ❌ | ✅ |
| Best For | "is-a" | "can-do" |

### Interface Declaration:
```java
interface MyInterface {
    // Constants: public static final (automatic)
    int CONSTANT = 100;
    
    // Methods: public abstract (automatic)
    void method1();
    int method2(String s);
}
```

### Implementation:
```java
class MyClass implements MyInterface {
    // Must implement ALL interface methods
    public void method1() {
        // Implementation
    }
    
    public int method2(String s) {
        // Implementation
        return 0;
    }
}
```

---

## 🎓 Day 3 Summary

### Key Takeaways:
```
✅ Abstraction = Hide details, show essentials
✅ Abstract class = 0-100% abstraction, can have body
✅ Interface = 100% abstraction, no body
✅ Interface variables = public static final
✅ Interface methods = public abstract
✅ Interface = Multiple inheritance solution
✅ Abstract class = IS-A relationship
✅ Interface = CAN-DO relationship
```

---

## 💪 Motivational Quote

> *"Abstraction is not about vagueness, it's about being at the right level of abstraction."*
> — Unknown

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

⬅️ **[Day 2 - Classes, Objects & Inheritance](../Day-2/README.md)** | **[Day 4 - Exception Handling](../Day-4/README.md)** ➡️

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day3)
