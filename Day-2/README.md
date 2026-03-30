# 📚 Day 2: Classes, Objects & Inheritance

![Java](https://img.shields.io/badge/Java-Classes%20%26%20Inheritance-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%202-success?style=for-the-badge)
![Duration](https://img.shields.io/badge/Duration-6%20Hours-yellow?style=for-the-badge)

> *Building blocks of Java - Classes, Objects, and the Power of Inheritance!*

---

## 🌟 Welcome to Day 2!

Today we dive deep into the heart of OOP - Classes and Objects. These are the real building blocks of Java. You'll learn how to create your own data types and how to share code between classes using inheritance.

**Estimated Time:** 6 Hours  
**Prerequisites:** Day 1 Concepts  
**Goal:** Master classes, objects, constructors, and inheritance

---

## 📖 Table of Contents

1. [Classes and Objects](#classes-and-objects)
2. [Constructors](#constructors)
3. [Method Overloading](#method-overloading)
4. [Inheritance](#inheritance)
5. [Method Overriding](#method-overriding)
6. [Access Modifiers](#access-modifiers)
7. [static and final Keywords](#static-and-final-keywords)
8. [Practice Questions](#-practice-questions)
9. [Quick Reference](#-quick-reference)

---

## 🏗️ Classes and Objects

### Understanding Classes:

A class is a blueprint or template for creating objects. It defines:
- **Attributes** (data/variables)
- **Behaviors** (methods/functions)

### Class Syntax:
```java
class ClassName {
    // 1. Fields (Instance Variables)
    data_type variable1;
    data_type variable2;
    
    // 2. Constructors
    ClassName() {
        // initialization code
    }
    
    // 3. Methods
    return_type methodName(parameters) {
        // method body
    }
}
```

### Complete Class Example:
```java
// Student class - Blueprint
class Student {
    // ========== ATTRIBUTES ==========
    String name;        // Instance variable - each object has its own
    int rollNo;         // Instance variable
    static String college;  // Static variable - shared by all objects
    
    // ========== CONSTRUCTOR ==========
    Student(String n, int r) {
        name = n;
        rollNo = r;
    }
    
    // ========== METHODS ==========
    void display() {
        System.out.println("Name: " + name);
        System.out.println("Roll: " + rollNo);
        System.out.println("College: " + college);
    }
    
    void study(String subject) {
        System.out.println(name + " is studying " + subject);
    }
}
```

### Creating Objects:

**Three Steps:**
```java
// Step 1: Declaration - Create reference
Student s1;        // s1 is null at this point

// Step 2: Instantiation - Create actual object
s1 = new Student(); // Allocates memory

// Step 3: Combined (Most Common)
Student s2 = new Student("Rahul", 101);
```

### Memory Allocation:
```
┌─────────────────────────────────────────────────────────┐
│                    HEAP MEMORY                           │
│                                                         │
│   Student Object 1          Student Object 2            │
│   ┌─────────────────┐     ┌─────────────────┐         │
│   │ name: "Rahul"   │     │ name: "Priya"   │         │
│   │ rollNo: 101     │     │ rollNo: 102     │         │
│   └─────────────────┘     └─────────────────┘         │
│         ↑                        ↑                      │
│         │                        │                      │
│   Stack Reference          Stack Reference              │
│   s1 ─────────────────►     s2 ─────────────────►     │
│                                                         │
│   Static Area                                          │
│   ┌─────────────────┐                                 │
│   │ college: "IIT"  │  ← Shared by all objects        │
│   └─────────────────┘                                 │
└─────────────────────────────────────────────────────────┘
```

### Real-World Analogy:
```
┌────────────────────────────────────────┐
│          CLASS = BLUEPRINT             │
│                                        │
│   Class Student:                       │
│   ├── Properties:                      │
│   │   ├── name                        │
│   │   ├── rollNo                      │
│   │   └── college                     │
│   └── Methods:                        │
│       ├── study()                      │
│       └── display()                    │
└────────────────────────────────────────┘
           ↓ creates
┌────────────────────────────────────────┐
│         OBJECTS = INSTANCES            │
│                                        │
│   Student s1 = new Student()           │
│   Student s2 = new Student()           │
│   Student s3 = new Student()           │
│                                        │
│   Each object has its own copy of      │
│   instance variables!                  │
└────────────────────────────────────────┘
```

---

## 🔧 Constructors

### What is a Constructor?

A constructor is a special method that is called when an object is created. It's used to **initialize** the object.

### Key Rules:
1. Constructor name MUST be same as class name
2. Constructor has NO return type (not even void)
3. Called automatically when object is created
4. If you don't create one, compiler creates default constructor

### Types of Constructors:

**1. Default Constructor (No-arg):**
```java
class Bike {
    String brand;
    int speed;
    
    // Default constructor - no parameters
    Bike() {
        brand = "Unknown";
        speed = 0;
        System.out.println("Bike created with defaults!");
    }
}

// Usage
Bike b1 = new Bike();  // Output: Bike created with defaults!
System.out.println(b1.brand);  // Unknown
System.out.println(b1.speed);   // 0
```

**2. Parameterized Constructor:**
```java
class Student {
    String name;
    int rollNo;
    double marks;
    
    // Parameterized constructor
    Student(String n, int r, double m) {
        name = n;
        rollNo = r;
        marks = m;
    }
    
    void display() {
        System.out.println(name + " - " + rollNo + " - " + marks);
    }
}

// Usage
Student s1 = new Student("Rahul", 101, 85.5);
Student s2 = new Student("Priya", 102, 92.0);
s1.display();  // Rahul - 101 - 85.5
s2.display();  // Priya - 102 - 92.0
```

**3. Constructor Overloading:**
```java
class Rectangle {
    double length, width;
    
    // Constructor 1: No args
    Rectangle() {
        length = 0;
        width = 0;
    }
    
    // Constructor 2: One arg (Square)
    Rectangle(double side) {
        length = side;
        width = side;
    }
    
    // Constructor 3: Two args
    Rectangle(double l, double w) {
        length = l;
        width = w;
    }
    
    double area() {
        return length * width;
    }
}

// Usage
Rectangle r1 = new Rectangle();        // 0 x 0
Rectangle r2 = new Rectangle(5);       // 5 x 5 (square)
Rectangle r3 = new Rectangle(4, 6);    // 4 x 6

System.out.println(r1.area());  // 0
System.out.println(r2.area());  // 25
System.out.println(r3.area());  // 24
```

### Constructor vs Method:

| Constructor | Method |
|------------|--------|
| Same name as class | Any name |
| No return type | Has return type |
| Called automatically | Called explicitly |
| Used to initialize | Used for behavior |
| Can't be inherited | Can be inherited |

---

## 🔄 Method Overloading

### Definition:
Having multiple methods with the **same name** but **different parameters** in the same class.

### Ways to Overload:

**1. Different Number of Parameters:**
```java
class Calculator {
    // Method 1: Two parameters
    int add(int a, int b) {
        System.out.println("Adding 2 numbers");
        return a + b;
    }
    
    // Method 2: Three parameters
    int add(int a, int b, int c) {
        System.out.println("Adding 3 numbers");
        return a + b + c;
    }
}

// Usage
Calculator calc = new Calculator();
System.out.println(calc.add(5, 3));         // 8
System.out.println(calc.add(1, 2, 3));       // 6
```

**2. Different Data Types:**
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }
    
    double add(double a, double b) {
        return a + b;
    }
}

// Usage
Calculator calc = new Calculator();
System.out.println(calc.add(5, 3));         // 8 (int)
System.out.println(calc.add(2.5, 3.5));     // 6.0 (double)
```

**3. Different Order of Parameters:**
```java
class Display {
    void show(int a, String b) {
        System.out.println("Int first: " + a + " " + b);
    }
    
    void show(String a, int b) {
        System.out.println("String first: " + a + " " + b);
    }
}

// Usage
Display d = new Display();
d.show(101, "Rahul");      // Int first
d.show("Rahul", 101);      // String first
```

### Method Overloading = Compile Time Polymorphism
```java
// Compiler decides at COMPILE TIME which method to call
// Based on parameter list

calc.add(5, 3);      // Compiler sees: int, int → calls int version
calc.add(2.5, 3.5);  // Compiler sees: double, double → calls double version
```

---

## 🧬 Inheritance

### What is Inheritance?

Inheritance is the process where one class acquires the properties (fields) and behaviors (methods) of another class.

### Why Use Inheritance?

```
┌─────────────────────────────────────────┐
│           CODE REUSABILITY               │
│                                          │
│   Without Inheritance:                    │
│   class Dog {                            │
│       void eat() { }                     │
│       void sleep() { }                   │
│       void bark() { }                    │
│   }                                      │
│   class Cat {                            │
│       void eat() { }    ← DUPLICATE!    │
│       void sleep() { } ← DUPLICATE!     │
│       void meow() { }                   │
│   }                                      │
│                                          │
│   With Inheritance:                       │
│   class Animal {                         │
│       void eat() { }   ← SHARED!        │
│       void sleep() { } ← SHARED!        │
│   }                                      │
│   class Dog extends Animal {             │
│       void bark() { }                   │
│   }                                      │
│   class Cat extends Animal {             │
│       void meow() { }                   │
│   }                                      │
└─────────────────────────────────────────┘
```

### Inheritance Syntax:
```java
class ParentClass {
    // Parent's code
}

class ChildClass extends ParentClass {
    // Child's code + Parent's inherited code
}
```

### Types of Inheritance:

**1. Single Inheritance:**
```
    ┌─────────┐
    │    A    │  (Parent/Superclass)
    └────┬────┘
         │
         │ extends
         ↓
    ┌─────────┐
    │    B    │  (Child/Subclass)
    └─────────┘
```
```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

// Usage
Dog d = new Dog();
d.eat();   // From Animal
d.bark();  // Dog's own
```

**2. Multilevel Inheritance:**
```
    ┌─────────┐
    │    A    │  (Grandparent)
    └────┬────┘
         │
         ↓
    ┌─────────┐
    │    B    │  (Parent)
    └────┬────┘
         │
         ↓
    ┌─────────┐
    │    C    │  (Child)
    └─────────┘
```
```java
class Grandfather {
    void home() {
        System.out.println("Grandfather's home");
    }
}

class Father extends Grandfather {
    void car() {
        System.out.println("Father's car");
    }
}

class Child extends Father {
    void cycle() {
        System.out.println("Child's cycle");
    }
}

// Usage
Child c = new Child();
c.home();   // From Grandfather
c.car();    // From Father
c.cycle();  // Child's own
```

**3. Hierarchical Inheritance:**
```
        ┌─────────┐
        │    A    │  (Parent)
        └────┬────┘
       ╱          ╲
      ╱            ╲
     ↓              ↓
┌─────────┐    ┌─────────┐
│    B    │    │    C    │  (Children)
└─────────┘    └─────────┘
```
```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

class Cat extends Animal {
    void meow() {
        System.out.println("Meowing...");
    }
}

// Usage
Dog d = new Dog();
Cat c = new Cat();
d.eat();  // From Animal
c.eat();  // From Animal
```

**4. Multiple Inheritance (NOT ALLOWED with classes!):**
```
      ┌─────────┐    ┌─────────┐
      │    A    │    │    B    │  (Parents)
      └─────────┘    └─────────┘
              ╲        ╱
               ╲      ╱
                ╲    ╱
                 ↓  ↓
            ┌─────────┐
            │    C    │  ❌ NOT ALLOWED!
            └─────────┘
```
```java
// ❌ THIS IS NOT ALLOWED IN JAVA!
class A { }
class B { }
class C extends A, B { }  // ERROR!

// ✅ SOLUTION: Use Interfaces
interface A { }
interface B { }
class C implements A, B { }  // ALLOWED!
```

---

## 🔁 Method Overriding

### What is Method Overriding?

When a child class provides a **specific implementation** of a method already defined in its parent class.

### Rules for Overriding:

1. Method name must be **SAME** as parent
2. Parameters must be **SAME** as parent
3. There must be **IS-A relationship** (inheritance)
4. Cannot override **private** methods
5. Cannot override **static** methods (this is called hiding)
6. Return type must be **same or covariant**

### Example:
```java
class Vehicle {
    void run() {
        System.out.println("Vehicle is running");
    }
}

class Bike extends Vehicle {
    @Override  // Annotation - helps catch errors
    void run() {
        System.out.println("Bike is running at 60kmph");
    }
}

// Usage
Vehicle v = new Bike();  // Parent reference, Child object
v.run();  // Output: Bike is running at 60kmph
```

### Overloading vs Overriding:

| Aspect | Method Overloading | Method Overriding |
|--------|------------------|-------------------|
| Definition | Same name, different params | Same name, same params |
| Class | Same class | Different classes |
| Purpose | Flexibility | Specific implementation |
| Polymorphism | Compile Time | Runtime |
| Parameters | Must be different | Must be same |
| Return Type | Can be different | Same or covariant |

---

## 🔒 Access Modifiers

### The Four Access Levels:

```
┌─────────────────────────────────────────────────────────────┐
│                    ACCESS MODIFIER HIERARCHY                │
│                                                             │
│   public     ████████████████████████████████████  ALL     │
│                                                             │
│   protected  ██████████████████████████        (Package +   │
│                                              Subclasses)    │
│                                                             │
│   default    ████████████████           (Package Only)       │
│                                                             │
│   private    ████████              (Class Only)            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Access Modifier Table:

| Location | public | protected | default | private |
|----------|--------|-----------|---------|---------|
| Same Class | ✅ | ✅ | ✅ | ✅ |
| Same Package (Subclass) | ✅ | ✅ | ✅ | ❌ |
| Same Package (Non-subclass) | ✅ | ✅ | ✅ | ❌ |
| Different Package (Subclass) | ✅ | ✅ | ❌ | ❌ |
| Different Package (Non-subclass) | ✅ | ❌ | ❌ | ❌ |

### Examples:

**public - Accessible everywhere:**
```java
package college;

public class Student {
    public String name;  // Accessible everywhere
    
    public void display() {
        System.out.println(name);
    }
}

// From anywhere in any package
Student s = new Student();
s.name = "Rahul";  // ✅ Works
```

**protected - Package + Inheritance:**
```java
package college;

public class Student {
    protected String collegeName;  // Same package + subclasses
    
    protected void display() {
        System.out.println(collegeName);
    }
}

// In same package (any class)
Student s = new Student();
s.collegeName = "IIT";  // ✅ Works

// In different package (subclass only)
class SpecialStudent extends Student {
    void test() {
        collegeName = "IIT";  // ✅ Works (through inheritance)
    }
}
```

**default (package-private) - Same package only:**
```java
// In package college
class Student {
    String name;  // default - no modifier
    
    void display() { }  // default
}
// Only accessible within college package
```

**private - Same class only:**
```java
class BankAccount {
    private double balance;  // Only accessible in this class
    
    private void secretMethod() {
        balance = 0;  // ✅ Works here
    }
    
    public void deposit(double amt) {
        balance += amt;  // ✅ Works here
    }
}

class Hacker {
    BankAccount acc = new BankAccount();
    void steal() {
        acc.balance = 0;  // ❌ ERROR - private!
    }
}
```

---

## 📌 static and final Keywords

### static Keyword:

**static Variable:**
```java
class Student {
    String name;              // Instance - each student has own
    static String college;    // Static - shared by all students
    
    Student(String n) {
        name = n;
    }
    
    void display() {
        System.out.println(name + " from " + college);
    }
}

public class StaticDemo {
    public static void main(String[] args) {
        Student.college = "IIT Delhi";  // Class name access
        
        Student s1 = new Student("Rahul");
        Student s2 = new Student("Priya");
        
        s1.display();  // Rahul from IIT Delhi
        s2.display();  // Priya from IIT Delhi
    }
}
```

**static Method:**
```java
class MathUtil {
    static int square(int x) {
        return x * x;
    }
    
    static double cube(double x) {
        return x * x * x;
    }
    
    // Cannot access non-static directly
    // static void show() {
    //     int x = 10;         // ✅ OK
    //     String s = "hi";     // ✅ OK
    //     name = "test";       // ❌ ERROR - instance variable
    // }
}

public class StaticMethodDemo {
    public static void main(String[] args) {
        // No object needed!
        int result = MathUtil.square(5);
        System.out.println(result);  // 25
    }
}
```

**Restrictions on static:**
```java
static void test() {
    int x = 10;          // ✅ Can access
    String s = "hi";      // ✅ Can access
    
    // ❌ Cannot use 'this' or 'super'
    // ❌ Cannot access instance (non-static) variables
    // ❌ Cannot call non-static methods directly
}
```

### final Keyword:

**final Variable - Constant:**
```java
class Constants {
    final double PI = 3.14159;  // Cannot be changed
    
    void test() {
        PI = 3.14;  // ❌ ERROR! Cannot assign value to final variable
    }
}
```

**final Method - Cannot Override:**
```java
class Parent {
    final void show() {
        System.out.println("Parent's show");
    }
}

class Child extends Parent {
    void show() {  // ❌ ERROR! Cannot override final method
        System.out.println("Child's show");
    }
}
```

**final Class - Cannot Extend:**
```java
final class FinalClass {
    void display() {
        System.out.println("FinalClass");
    }
}

class SubClass extends FinalClass {  // ❌ ERROR! Cannot extend final class
    void display() {
        System.out.println("SubClass");
    }
}
```

---

## 🎯 Practice Questions

### MCQs:

**Q1. Which keyword is used for inheritance?**
- A) inherit
- B) **extends** ✅
- C) implements
- D) base

**Q2. How many times is constructor called?**
- A) Once
- B) Twice
- C) **As many times as objects created** ✅
- D) Never

**Q3. Which is NOT a type of inheritance?**
- A) Single
- B) Multiple ✅
- C) Hierarchical
- D) Multilevel

**Q4. Method Overloading is which type of polymorphism?**
- A) Runtime
- B) **Compile Time** ✅
- C) Both
- D) None

**Q5. Which is the most restrictive modifier?**
- A) protected
- B) default
- C) **private** ✅
- D) public

**Q6. What is the output?**

```java
class Parent {
    Parent() { System.out.print("P "); }
}
class Child extends Parent {
    Child() { System.out.print("C "); }
}
public class Test {
    public static void main(String args[]) {
        new Child();
    }
}
```
**Answer: P C** (Parent constructor runs first via super())

---

### Coding Questions:

**Q7. Write a program demonstrating inheritance:**
```java
class Employee {
    float salary = 40000;
    
    void displaySalary() {
        System.out.println("Base Salary: " + salary);
    }
}

class Programmer extends Employee {
    int bonus = 10000;
    
    void totalSalary() {
        System.out.println("Total: " + (salary + bonus));
    }
}

public class InheritanceDemo {
    public static void main(String args[]) {
        Programmer p = new Programmer();
        p.displaySalary();  // 40000
        p.totalSalary();    // 50000
    }
}
```

**Q8. Write a program for method overriding:**
```java
class Bank {
    double getRate() {
        return 0;
    }
}

class SBI extends Bank {
    @Override
    double getRate() {
        return 8.5;
    }
}

class HDFC extends Bank {
    @Override
    double getRate() {
        return 9.0;
    }
}

public class BankDemo {
    public static void main(String args[]) {
        Bank b;
        b = new SBI();
        System.out.println("SBI Rate: " + b.getRate() + "%");  // 8.5
        
        b = new HDFC();
        System.out.println("HDFC Rate: " + b.getRate() + "%"); // 9.0
    }
}
```

---

## 📋 Quick Reference

### Inheritance Types:
```
✅ Single:    A → B
✅ Multilevel: A → B → C
✅ Hierarch:   A → B, A → C
❌ Multiple:   A, B → C (NOT with classes!)
```

### Constructor Rules:
```
1. Name = Class Name
2. No Return Type
3. Called Automatically
4. Can Overload
5. If not created, compiler creates default
```

### Method Overriding Rules:
```
1. Same name
2. Same parameters
3. Inheritance required (IS-A)
4. Cannot override private
5. Cannot override static
6. Return type: same or covariant
```

### Access Modifiers:
```
public    → Everywhere
protected → Package + Subclasses
default   → Package only
private   → Class only
```

---

## 🎓 Day 2 Summary

### Key Takeaways:
```
✅ Class = Blueprint, Object = Instance
✅ Constructor = Object initialization
✅ Overloading = Same class, different params
✅ Overriding = Different class, same params
✅ Inheritance = Code reuse via extends
✅ 4 access modifiers: public > protected > default > private
✅ static = class level, shared
✅ final = constant / no override / no extend
```

---

## 💪 Motivational Quote

> *"The best way to predict the future is to create it."*
> — Peter Drucker

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

⬅️ **[Day 1 - OOP Basics & Java Fundamentals](../Day-1/README.md)** | **[Day 3 - Interface & Abstract Class](../Day-3/README.md)** ➡️

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day2)
