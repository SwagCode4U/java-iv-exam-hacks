# 📚 Day 1: OOP Concepts & Java Basics

![Java](https://img.shields.io/badge/Java-OOP%20Fundamentals-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%201-success?style=for-the-badge)
![Duration](https://img.shields.io/badge/Duration-6%20Hours-yellow?style=for-the-badge)

> *Master the fundamentals, build the future!*

---

## 🌟 Welcome to Day 1!

Today, we'll cover the foundation stones of Java OOP. These concepts are the building blocks for everything else you'll learn. Take your time, practice code, and don't rush!

**Estimated Time:** 6 Hours  
**Goal:** Understand OOP concepts and Java fundamentals

---

## 📖 Table of Contents

1. [What is OOP?](#what-is-oop)
2. [6 Basic OOP Concepts](#6-basic-oop-concepts)
3. [History & Features of Java](#history--features-of-java)
4. [Java Program Structure](#java-program-structure)
5. [Tokens & Identifiers](#tokens--identifiers)
6. [Data Types & Variables](#data-types--variables)
7. [Operators](#operators)
8. [Control Statements](#control-statements)
9. [Practice Questions](#-practice-questions)
10. [Quick Reference](#-quick-reference)

---

## 🎯 What is OOP?

### Definition:
Object-Oriented Programming (OOP) is a software design method that models the characteristics of abstract or real objects using classes and objects.

### In Simple Terms:
```
Real World          →    OOP World
   Car             →      Class (Blueprint)
   My Ferrari      →      Object (Instance)
   Color, Speed    →      Attributes/Properties
   Drive, Brake    →      Methods/Behaviors
```

### Why OOP?
- 📦 **Organized Code** - Everything in its place
- 🔄 **Reusable** - Write once, use many times
- 🛡️ **Secure** - Data hiding protects information
- 🎯 **Real-world Modeling** - Natural way of thinking

---

## 🔥 6 Basic OOP Concepts

### 1️⃣ Object and Class

**Class:** Blueprint/Template for creating objects
```java
// Class declaration - Blueprint
class Student {
    // Properties/Attributes
    String name;
    int rollNo;
    
    // Methods/Behaviors
    void study() {
        System.out.println(name + " is studying");
    }
}
```

**Object:** Instance of a class
```java
// Object creation - Real instance
Student s1 = new Student();
s1.name = "Rahul";
s1.rollNo = 101;
s1.study();

// Student s2 = new Student();
// s2.name = "Priya";
```

**Real-Life Analogy:**
```
Class = Architect's Blueprint
Object = Actual House built from blueprint
```

### 2️⃣ Data Abstraction

**Definition:** Hiding unnecessary details, showing only essential features.

**Real-Life Example:**
```
┌─────────────────────────────┐
│         ATM MACHINE          │
│  ┌─────────────────────────┐ │
│  │  Card Slot             │ │
│  │  Screen               │ │
│  │  Keypad               │ │
│  │  Cash Dispenser        │ │
│  └─────────────────────────┘ │
│                              │
│  What You See:              │
│  ✅ Insert Card            │
│  ✅ Enter PIN              │
│  ✅ Get Cash               │
│                              │
│  What's Hidden:             │
│  ❌ Database Connection     │
│  ❌ Network Processing     │
│  ❌ Transaction Logic      │
└─────────────────────────────┘
```

### 3️⃣ Data Encapsulation

**Definition:** Wrapping data and functions into a single unit (class).

**Example:**
```java
class BankAccount {
    // Private data - hidden from outside
    private double balance;
    
    // Public methods - only way to access
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }
    
    public void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
        }
    }
    
    public double getBalance() {
        return balance;
    }
}
```

### 4️⃣ Inheritance

**Definition:** Child class acquiring properties of parent class.

```java
// Parent class
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

// Child class
class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

// Usage
Dog d = new Dog();
d.eat();   // From Animal - inherited!
d.bark();  // Dog's own method
```

### 5️⃣ Polymorphism

**Definition:** "Poly" = Many, "Morph" = Forms. One name, multiple forms.

```java
// Overloading - Compile time polymorphism
class Calculator {
    int add(int a, int b) {
        return a + b;
    }
    
    double add(double a, double b) {
        return a + b;
    }
}

// Overriding - Runtime polymorphism
class Parent {
    void show() { System.out.println("Parent"); }
}

class Child extends Parent {
    void show() { System.out.println("Child"); }
}
```

### 6️⃣ Dynamic Binding

**Definition:** Decision about which code to run is made at runtime.

```java
Parent p = new Child();  // Which show()?
p.show();  // Runtime pe decide hoga - Child ka show() chalega
```

---

## ☕ History & Features of Java

### Quick History:
```
1991 - Java invented by James Gosling at Sun Microsystems
     - Originally called "Oak"
     - For consumer electronic devices

1995 - Java officially released
     - Name changed to Java (inspired by coffee! ☕)

Today - One of the most popular programming languages
```

### All Java Features:

| Feature | Description |
|---------|-------------|
| ☕ **Compiled & Interpreted** | Two-stage process |
| 🌍 **Platform Independent** | Write Once, Run Anywhere |
| 🎯 **Object-Oriented** | Pure OOP language |
| 🛡️ **Robust & Secure** | No pointers, exception handling |
| 🌐 **Distributed** | RMI for network applications |
| 📦 **Simple & Small** | No pointers, no header files |
| 🔄 **Multithreaded** | Multiple tasks simultaneously |
| ⚡ **High Performance** | JIT compilation |
| 🔌 **Dynamic & Extensible** | Runtime class loading |

### Platform Independence Explained:
```
┌─────────────────────┐
│   Source Code        │
│   (.java file)       │
└─────────┬───────────┘
          ↓ javac
┌─────────────────────┐
│   Bytecode           │
│   (.class file)      │  ← Machine Independent!
└─────────┬───────────┘
          ↓
┌─────────────────────┐
│   JVM (Java Virtual  │
│   Machine)          │  ← Different for each OS
└─────────────────────┘
     ↓      ↓      ↓
┌──────┐ ┌──────┐ ┌──────┐
│ Win  │ │ Linux│ │ Mac  │
│ JVM  │ │ JVM  │ │ JVM  │
└──────┘ └──────┘ └──────┘
```

---

## 🏗️ Java Program Structure

### Complete Structure:
```java
// 1. Documentation Section (Optional)
// Author: Your Name
// Date: 2024

// 2. Package Statement (Optional)
package com.college.student;

// 3. Import Statements (Optional)
import java.util.Scanner;

// 4. Interface Declaration (Optional)
interface Printable { }

// 5. Class Definitions
class Student {
    // Fields
    String name;
    int rollNo;
    
    // Constructor
    Student(String n, int r) {
        name = n;
        rollNo = r;
    }
    
    // Methods
    void display() {
        System.out.println("Name: " + name);
        System.out.println("Roll: " + rollNo);
    }
}

// 6. Main Class
public class MainClass {
    public static void main(String[] args) {
        Student s = new Student("Rahul", 101);
        s.display();
    }
}
```

### Understanding main() method:
```java
public static void main(String[] args)
│      │     │       │
│      │     │       └─ Array of command line arguments
│      │     └───────── No return value (void)
│      └─────────────── Class method, can call without object
└────────────────────── Accessible from anywhere
```

---

## 🏷️ Tokens & Identifiers

### What are Tokens?
Tokens are the smallest building blocks of a Java program.

### 5 Types of Tokens:

**1. Literals (Fixed Values):**
```java
// Integer literals
100, -50, 0, 0xFF  // decimal, negative, zero, hexadecimal

// Floating-point literals
3.14, -2.5, 10e5   // decimal, negative, scientific

// Character literals
'A', 'z', '\n'      // single quotes only

// String literals
"Hello", "Java"     // double quotes

// Boolean literals
true, false
```

**2. Identifiers (Names):**
```java
// ✅ Valid Identifiers
int age;                    // Good
String studentName;          // CamelCase
double $price;               // Dollar sign allowed
final int MAX_VALUE;        // Constants in CAPS
static int _counter;        // Underscore allowed

// ❌ Invalid Identifiers
int 2name;                  // Can't start with digit
double my-score;            // No hyphens
class;                      // Can't use keywords
```

**3. Keywords (Reserved Words):**
```java
// Java has 50 reserved keywords
// You CANNOT use these as identifiers!
abstract, boolean, break, byte, case, catch, char,
class, const, continue, default, do, double, else,
enum, extends, final, finally, float, for, goto, if,
implements, import, instanceof, int, interface, long,
native, new, package, private, protected, public,
return, short, static, strictfp, super, switch,
synchronized, this, throw, throws, transient, try,
void, volatile, while, assert, enum
```

**4. Operators (Symbols):**
```java
// Arithmetic
+ - * / %

// Relational
> < >= <= == !=

// Logical
&& || !

// Assignment
= += -= *= /= %=

// Increment/Decrement
++ --

// Bitwise
& | ^ << >> ~

// Ternary
?:
```

**5. Separators (Punctuations):**
```java
( )    // Method parameters, conditions
{ }    // Class body, method body, blocks
[ ]    // Arrays
;      // Statement end
,      // Multiple declarations
.      // Package hierarchy, method call
```

---

## 📊 Data Types & Variables

### Primitive Data Types:

| Type | Size | Range | Default | Example |
|------|------|-------|---------|---------|
| **byte** | 1 B | -128 to 127 | 0 | `byte b = 100;` |
| **short** | 2 B | -32K to 32K | 0 | `short s = 5000;` |
| **int** | 4 B | -2B to 2B | 0 | `int i = 100000;` |
| **long** | 8 B | Very large | 0L | `long l = 100000L;` |
| **float** | 4 B | Decimal | 0.0f | `float f = 3.14f;` |
| **double** | 8 B | Large decimal | 0.0 | `double d = 3.14159;` |
| **char** | 2 B | Unicode | '\u0000' | `char c = 'A';` |
| **boolean** | 1 B | true/false | false | `boolean b = true;` |

### Types of Variables:

```java
class Student {
    String collegeName;           // Instance variable
    static String university;      // Static/Class variable
    
    void study(String subject) {  // subject is parameter (local)
        int marks = 100;          // Local variable
        
        for (int i = 0; i < 5; i++) {  // i is local to for loop
            // i exists only here
        }
    }
}
```

### Memory Areas:
```
┌─────────────────────────────────────┐
│            HEAP MEMORY               │
│   Objects & Instance Variables       │
│   (Dynamic, garbage collected)      │
├─────────────────────────────────────┤
│            STACK MEMORY             │
│   Method calls, Local variables      │
│   (LIFO, automatic cleanup)         │
├─────────────────────────────────────┤
│            METHOD AREA              │
│   Class info, Static variables       │
│   (Loaded at class loading)        │
└─────────────────────────────────────┘
```

---

## 🔢 Operators

### Operator Precedence Table:

| Priority | Operators | Associativity |
|----------|-----------|---------------|
| 1 | `()` `[]` `.` | Left to Right |
| 2 | `!` `~` `++` `--` | Right to Left |
| 3 | `*` `/` `%` | Left to Right |
| 4 | `+` `-` | Left to Right |
| 5 | `<<` `>>` `>>>` | Left to Right |
| 6 | `<` `<=` `>` `>=` | Left to Right |
| 7 | `==` `!=` | Left to Right |
| 8 | `&` | Left to Right |
| 9 | `^` | Left to Right |
| 10 | `\|` | Left to Right |
| 11 | `&&` | Left to Right |
| 12 | `\|\|` | Left to Right |
| 13 | `?:` | Right to Left |
| 14 | `=` `+=` `-=` etc. | Right to Left |

### Increment/Decrement Deep Dive:

```java
int a = 5, b, c, d;

// Post-increment: Use THEN Increment
b = a++;    // b = 5, a = 6

// Pre-increment: Increment THEN Use
c = ++a;    // c = 7, a = 7

// Post-decrement: Use THEN Decrement
d = a--;    // d = 7, a = 6

// Pre-decrement: Decrement THEN Use
a = --a;    // a = 5
```

### Bitwise Operators:

```java
// AND (&)
5 & 3  // 0101 & 0011 = 0001 = 1

// OR (|)
5 | 3  // 0101 | 0011 = 0111 = 7

// XOR (^)
5 ^ 3  // 0101 ^ 0011 = 0110 = 6

// NOT (~)
~5     // -(5+1) = -6

// Left Shift (<<)
3 << 2  // 3 * 2^2 = 12

// Right Shift (>>)
12 >> 2 // 12 / 2^2 = 3
```

---

## 🔀 Control Statements

### Selection Statements:

**1. if-else:**
```java
// Simple if
if (age >= 18) {
    System.out.println("Eligible to vote");
}

// if-else
if (marks >= 40) {
    System.out.println("Pass");
} else {
    System.out.println("Fail");
}

// Nested if-else
if (marks >= 90) {
    grade = "A+";
} else if (marks >= 80) {
    grade = "A";
} else if (marks >= 70) {
    grade = "B";
} else {
    grade = "F";
}
```

**2. switch:**
```java
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Invalid day");
}

// No break? Falls through!
switch (option) {
    case 1:
    case 2:
    case 3:
        System.out.println("Valid option");
        break;
    default:
        System.out.println("Invalid");
}
```

### Loop Statements:

**1. for Loop:**
```java
// Basic for loop
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}

// Enhanced for loop (for-each)
int[] numbers = {10, 20, 30, 40, 50};
for (int num : numbers) {
    System.out.println(num);
}

// Infinite loop
for (;;) {
    // Runs forever!
}
```

**2. while Loop:**
```java
// Entry-controlled loop
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}

// Check first, then execute
```

**3. do-while Loop:**
```java
// Exit-controlled loop - ALWAYS runs at least once
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

### Jump Statements:

**break vs continue:**
```java
// break - Exit loop immediately
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break;  // Exit loop at 5
    }
    System.out.println(i);
}
// Output: 1, 2, 3, 4

// continue - Skip current iteration
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;  // Skip 3
    }
    System.out.println(i);
}
// Output: 1, 2, 4, 5
```

---

## 🎯 Practice Questions

### MCQs:

**Q1. Java was originally called:**
- A) Java
- B) Oak ✅
- C) Coffee
- D) Green

**Q2. What is the size of `int` in Java?**
- A) 1 byte
- B) 2 bytes
- C) 4 bytes ✅
- D) 8 bytes

**Q3. Which is NOT a primitive type?**
- A) int
- B) float
- C) String ✅
- D) boolean

**Q4. Which loop executes at least once?**
- A) for
- B) while
- C) do-while ✅
- D) enhanced for

**Q5. What is the output of `10 % 3`?**
- A) 3
- B) 1 ✅
- C) 0
- D) 3.33

---

### Predict the Output:

**Q6.**
```java
class Test {
    public static void main(String args[]) {
        int a = 10;
        int b = 5;
        System.out.println(a++ + ++b);
    }
}
// Answer: 16 (10 + 6)
```

**Q7.**
```java
class Test {
    public static void main(String args[]) {
        for (int i = 1; i <= 3; i++) {
            if (i == 2) {
                continue;
            }
            System.out.print(i + " ");
        }
    }
}
// Answer: 1 3
```

**Q8.**
```java
class Test {
    public static void main(String args[]) {
        int x = 5;
        if (x == 5) {
            System.out.print("A ");
        } else if (x < 5) {
            System.out.print("B ");
        } else {
            System.out.print("C ");
        }
    }
}
// Answer: A
```

---

### Coding Questions:

**Q9. Write a program to check if a number is positive, negative, or zero:**
```java
import java.util.Scanner;

class CheckNumber {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        
        if (num > 0) {
            System.out.println("Positive");
        } else if (num < 0) {
            System.out.println("Negative");
        } else {
            System.out.println("Zero");
        }
    }
}
```

**Q10. Write a program to print Fibonacci series:**
```java
class Fibonacci {
    public static void main(String args[]) {
        int n = 10;
        int first = 0, second = 1;
        
        System.out.print("Fibonacci: " + first + " " + second);
        
        for (int i = 2; i < n; i++) {
            int next = first + second;
            System.out.print(" " + next);
            first = second;
            second = next;
        }
    }
}
```

---

## 📋 Quick Reference

### Data Type Ranges:
```
byte:    -128 to 127
short:   -32,768 to 32,767
int:     -2,147,483,648 to 2,147,483,647
long:    -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
float:   3.4e-38 to 3.4e+38
double:  1.7e-308 to 1.7e+308
char:    '\u0000' to '\uffff' (0 to 65,535)
```

### Type Casting:
```java
// Implicit (Automatic) - Widening
byte → short → int → long → float → double
byte b = 100;
int i = b;  // ✅ Automatic

// Explicit - Narrowing
double → float → long → int → short → byte
double d = 100.5;
int i = (int) d;  // ✅ Manual - data loss possible
```

### Java Keywords Count:
```
Total: 50 keywords
Abstract ones to remember:
abstract, assert, boolean, break, byte, case, catch, char,
class, const, continue, default, do, double, else, enum,
extends, final, finally, float, for, goto, if, implements,
import, instanceof, int, interface, long, native, new, package,
private, protected, public, return, short, static, strictfp,
super, switch, synchronized, this, throw, throws, transient,
try, void, volatile, while
```

---

## 🎓 Day 1 Summary

### What We Learned:
1. ✅ What is OOP and why it's important
2. ✅ 6 Basic OOP Concepts
3. ✅ Java History and 9 Key Features
4. ✅ Java Program Structure
5. ✅ Tokens, Identifiers, Keywords
6. ✅ Data Types and Variables
7. ✅ All Operators
8. ✅ Control Statements (if, switch, loops)
9. ✅ break and continue

### Key Takeaways:
```
🎯 OOP = Object Oriented Programming
🎯 Class = Blueprint, Object = Instance
🎯 Java = Platform Independent (bytecode + JVM)
🎯 8 Primitive Data Types
🎯 4 Access Modifiers (public, protected, default, private)
🎯 Loops: for, while, do-while
🎯 break = exit, continue = skip
```

---

## 📝 Homework

1. Practice all code examples by typing them
2. Make notes of important points
3. Solve at least 10 MCQs from practice questions
4. Write one program for each topic

---

## 💪 Motivational Quote

> *"The only way to do great work is to love what you do. If you haven't found it yet, keep looking. Don't settle."*
> — Steve Jobs

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

➡️ **Next: [Day 2 - Classes, Objects & Inheritance](./Day-2/README.md)**

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day1)
