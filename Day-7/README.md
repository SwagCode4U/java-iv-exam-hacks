# 📚 Day 7: Packages, Strings, Collections & More

![Java](https://img.shields.io/badge/Java-Advanced%20Topics-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%207-success?style=for-the-badge)
![Duration](https://img.shields.io/badge/Duration-6%20Hours-yellow?style=for-the-badge)

> *Mastering Packages, String Handling, Wrapper Classes, Multithreading, Collections, and File I/O!*

---

## 🌟 Welcome to Day 7!

Today we cover additional important topics that are essential for your Java exams. These topics are frequently asked in both theory and practical exams!

**Estimated Time:** 6 Hours  
**Prerequisites:** Days 1-6  
**Goal:** Master Packages, Strings, Collections, Multithreading, and File I/O

---

## 📖 Table of Contents

1. [Packages](#-packages)
2. [String Handling](#-string-handling)
3. [StringBuffer & StringBuilder](#-stringbuffer--stringbuilder)
4. [Wrapper Classes & Autoboxing](#-wrapper-classes--autoboxing)
5. [Multithreading](#-multithreading)
6. [Collections Framework](#-collections-framework)
7. [File I/O](#-file-io)
8. [Generics](#-generics)
9. [Practice Questions](#-practice-questions)
10. [Quick Reference](#-quick-reference)

---

## 📦 Packages

### What is a Package?

A **Package** in Java is a group of related classes and interfaces. It helps in organizing code and avoiding naming conflicts.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    JAVA PACKAGES HIERARCHY                            │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│                        java (root)                                   │
│                       ╱    │    ╲                                   │
│                      ╱     │     ╲                                  │
│                   lang    util   io                                 │
│                   ╱╲       │      │                                 │
│                  ╱  ╲   ArrayList  File                            │
│                Object  String                                             │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Types of Packages:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    TYPES OF PACKAGES                                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   1. Built-in Packages (Pre-defined in JDK)                         │
│      ├── java.lang      → String, System, Math, Object              │
│      ├── java.util      → ArrayList, HashMap, Scanner               │
│      ├── java.io        → File, FileInputStream, FileWriter         │
│      ├── java.net       → Socket, URL, ServerSocket                 │
│      ├── java.awt       → GUI components                           │
│      ├── java.applet    → Applet classes                           │
│      └── java.swing     → Advanced GUI (Swing)                     │
│                                                                     │
│   2. User-defined Packages (Custom)                                 │
│      └── Created by programmers                                     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Creating a Package:

```java
// Step 1: Create package declaration at the top
package college.department;

public class Student {
    String name;
    int rollNo;
    
    void display() {
        System.out.println("Name: " + name);
        System.out.println("Roll: " + rollNo);
    }
}
```

**Hinglish:** Package create karne ke liye pehle line pe `package packageName;` likho. File ka naam class ke naam se same hona chahiye (Student.java).

### Saving & Compiling Package:

```
Folder Structure:
┌─────────────────────────────────────┐
│   college/                          │
│       └── department/               │
│             └── Student.class        │
│                                     │
└─────────────────────────────────────┘

Command to compile:
    javac -d . Student.java

Command to run:
    java college.department.Student
```

**Hinglish:** `-d .` matlab current directory mein package structure create karo.

### Using Packages:

**1. Import single class:**
```java
// Syntax: import packageName.ClassName;
import java.util.ArrayList;

public class Test {
    public static void main(String args[]) {
        ArrayList<String> list = new ArrayList<>();
    }
}
```

**2. Import all classes from package:**
```java
// Syntax: import packageName.*;
import java.util.*;

public class Test {
    public static void main(String args[]) {
        ArrayList<String> list = new ArrayList<>();
        HashMap<Integer, String> map = new HashMap<>();
    }
}
```

**3. Fully Qualified Name:**
```java
public class Test {
    public static void main(String args[]) {
        java.util.ArrayList<String> list = new java.util.ArrayList<>();
    }
}
```

**Hinglish:** Jab import nahi karte toh har baar poora naam likhna padta hai. Yeh kabhi kabhi necessary hota hai jab do packages mein same class naam ho.

### java.lang Package:

```java
// java.lang automatically import hota hai har program mein!
// Isme ye important classes hain:

// Object class - sab classes ke parent
class MyClass extends Object { }

// String class
String s = "Hello";

// System class
System.out.println("Hello");

// Math class
double sqrt = Math.sqrt(25);
int max = Math.max(10, 20);

// Integer, Double, etc. (Wrapper classes)
Integer i = 100;
Double d = 3.14;
```

**Hinglish:** java.lang package automatically import hota hai, isliye ise alag se import karne ki zaroorat nahi.

### Accessing Package Members:

```java
// File: mypack/MyClass.java
package mypack;

public class MyClass {
    public int publicVar = 1;
    protected int protectedVar = 2;
    int defaultVar = 3;        // package-private
    private int privateVar = 4; // sirf is class mein
}

// File: test/TestAccess.java
package test;
import mypack.MyClass;

public class TestAccess {
    public static void main(String args[]) {
        MyClass obj = new MyClass();
        
        System.out.println(obj.publicVar);      // ✅ Works
        // obj.protectedVar - ❌ different package, not subclass
        // obj.defaultVar - ❌ different package
        // obj.privateVar - ❌ private
    }
}
```

---

## 🔤 String Handling

### What is String?

**String** in Java is a sequence of characters. It is a class in Java (not a primitive type).

```
┌─────────────────────────────────────────────────────────────────────┐
│                    STRING IN JAVA                                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   String s = "Hello";                                              │
│                                                                     │
│   Memory View:                                                      │
│   ┌─────┬─────┬─────┬─────┬─────┐                                 │
│   │  H  │  e  │  l  │  l  │  o  │                                 │
│   └─────┴─────┴─────┴─────┴─────┘                                 │
│     0     1     2     3     4    ← Index (0-based!)                │
│                                                                     │
│   Length = 5                                                        │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Creating Strings:

```java
// Method 1: Using String Literal (Preferred)
String s1 = "Hello";
// → Ye String Pool mein store hota hai

// Method 2: Using new keyword
String s2 = new String("Hello");
// → Ye Heap Memory mein store hota hai

// Method 3: From char array
char[] ch = {'H', 'e', 'l', 'l', 'o'};
String s3 = new String(ch);

// Method 4: From byte array
byte[] b = {72, 101, 108, 108, 111};
String s4 = new String(b);
```

**Hinglish:** String literal zyada efficient hai kyunki yeh String Pool mein store hota hai. new keyword se bana String alag object banata hai.

### String Pool Concept:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    STRING POOL                                       │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   String s1 = "Java";                                               │
│   String s2 = "Java";                                               │
│   String s3 = new String("Java");                                   │
│                                                                     │
│   String Pool                          Heap Memory                   │
│   ┌─────────────┐                     ┌─────────────┐                │
│   │   "Java"    │                     │   "Java"    │                │
│   │   (s1, s2)  │                     │   (s3)      │                │
│   └─────────────┘                     └─────────────┘                │
│                                                                     │
│   s1 == s2  → true  (same object in pool)                          │
│   s1 == s3  → false (different objects)                            │
│   s1.equals(s3) → true (same content)                              │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Important String Methods:

```java
class StringMethods {
    public static void main(String args[]) {
        String s = "Hello Java Programming";
        
        // 1. length() - Return total characters
        System.out.println(s.length());  // 21
        
        // 2. charAt(index) - Return character at index
        System.out.println(s.charAt(0));  // H
        System.out.println(s.charAt(6));  // J
        
        // 3. substring(start) - Return from start to end
        System.out.println(s.substring(6));  // Java Programming
        
        // 4. substring(start, end) - Return from start to end-1
        System.out.println(s.substring(6, 10));  // Java
        
        // 5. toUpperCase() - Convert to uppercase
        System.out.println(s.toUpperCase());  // HELLO JAVA PROGRAMMING
        
        // 6. toLowerCase() - Convert to lowercase
        System.out.println(s.toLowerCase());  // hello java programming
        
        // 7. equals() - Compare content (case sensitive)
        System.out.println("hello".equals("hello"));  // true
        System.out.println("hello".equals("Hello"));  // false
        
        // 8. equalsIgnoreCase() - Compare ignoring case
        System.out.println("hello".equalsIgnoreCase("HELLO"));  // true
        
        // 9. indexOf(char/string) - Return first occurrence
        System.out.println(s.indexOf('a'));  // 7
        System.out.println(s.indexOf("Java"));  // 6
        
        // 10. lastIndexOf() - Return last occurrence
        System.out.println(s.lastIndexOf('a'));  // 18
        
        // 11. contains() - Check if contains
        System.out.println(s.contains("Java"));  // true
        
        // 12. startsWith() - Check prefix
        System.out.println(s.startsWith("Hello"));  // true
        
        // 13. endsWith() - Check suffix
        System.out.println(s.endsWith("ming"));  // true
        
        // 14. replace(old, new) - Replace characters/string
        System.out.println(s.replace("Java", "Python"));  // Hello Python Programming
        
        // 15. trim() - Remove leading/trailing spaces
        String s2 = "  Hello  ";
        System.out.println(s2.trim());  // Hello
        
        // 16. split(delimiter) - Split into array
        String fruits = "Apple,Banana,Mango";
        String arr[] = fruits.split(",");
        for(String f : arr) {
            System.out.println(f);
        }
        
        // 17. concat() - Join strings
        String s3 = "Hello".concat(" World");
        System.out.println(s3);  // Hello World
        
        // 18. isEmpty() - Check if empty
        System.out.println("".isEmpty());  // true
        
        // 19. valueOf() - Convert other types to String
        int num = 100;
        String str = String.valueOf(num);
        System.out.println(str);  // "100"
    }
}
```

### String Comparison - == vs equals():

```java
class StringComparison {
    public static void main(String args[]) {
        String s1 = "Java";
        String s2 = "Java";
        String s3 = new String("Java");
        String s4 = new String("java");
        
        // Using == (compares references)
        System.out.println(s1 == s2);  // true  (same object in pool)
        System.out.println(s1 == s3);  // false (different objects)
        System.out.println(s3 == s4);  // false (different content)
        
        // Using equals() (compares content)
        System.out.println(s1.equals(s2));  // true
        System.out.println(s1.equals(s3));  // true
        System.out.println(s1.equals(s4));  // false (case sensitive!)
        
        // Using equalsIgnoreCase()
        System.out.println(s1.equalsIgnoreCase(s4));  // true
    }
}
```

**Hinglish:** **Always use equals() for comparing String content. == compares memory locations, equals() compares actual characters.**

### Immutability of Strings:

```java
class StringImmutability {
    public static void main(String args[]) {
        String s = "Hello";
        s.concat(" World");  // Creates NEW string
        
        System.out.println(s);  // Hello (NOT changed!)
        // Reason: Strings are immutable in Java
        
        // To actually change, assign back:
        s = s.concat(" World");
        System.out.println(s);  // Hello World
    }
}
```

**Hinglish:** String immutable hai matlab change nahi ho sakta ek baar create hone ke baad. concat() naya String return karta hai, original change nahi hota.

### Why Strings are Immutable?

```
┌─────────────────────────────────────────────────────────────────────┐
│                    WHY STRING IS IMMUTABLE?                          │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   1. Security                                              │
│      • Database usernames, passwords stored as Strings              │
│      • If mutable, anyone could change them                       │
│                                                                     │
│   2. Thread Safety                                                 │
│      • Immutable objects can be shared between threads safely       │
│      • No synchronization needed                                    │
│                                                                     │
│   3. String Pool Optimization                                       │
│      • JVM can cache string literals                               │
│      • Saves memory                                                │
│                                                                     │
│   4. HashCode Caching                                              │
│      • String objects used as HashMap keys                         │
│      • HashCode computed once and cached                           │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 🔧 StringBuffer & StringBuilder

### Why do we need them?

Since Strings are immutable, for frequent modifications we use **StringBuffer** and **StringBuilder**.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    MUTABLE STRING CLASSES                            │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   StringBuffer              StringBuilder                           │
│   ───────────              ─────────────                           │
│   ✅ Thread-safe           ❌ Not thread-safe                      │
│   ⚠️ Slower                ⚡ Faster                                │
│   Use in multi-threaded     Use in single-threaded                  │
│                                                                     │
│   Both are MUTABLE - original string changes kar sakte hain!        │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### StringBuffer Methods:

```java
class StringBufferDemo {
    public static void main(String args[]) {
        StringBuffer sb = new StringBuffer("Hello");
        
        // 1. append() - Add at end
        sb.append(" World");
        System.out.println(sb);  // Hello World
        
        // 2. insert() - Insert at position
        sb.insert(5, ",");
        System.out.println(sb);  // Hello, World
        
        // 3. replace() - Replace substring
        sb.replace(6, 11, "Java");
        System.out.println(sb);  // Hello, Java
        
        // 4. delete() - Delete substring
        sb.delete(5, 10);
        System.out.println(sb);  // Hello
        
        // 5. reverse()
        sb.reverse();
        System.out.println(sb);  // olleH
        
        // 6. capacity() - How much memory allocated
        System.out.println(sb.capacity());  // 21 (default: 16 + length)
        
        // 7. length()
        System.out.println(sb.length());  // 5
        
        // 8. charAt()
        System.out.println(sb.charAt(0));  // o
        
        // 9. setCharAt()
        sb.setCharAt(0, 'O');
        System.out.println(sb);  // OlleH
    }
}
```

### StringBuilder vs StringBuffer:

```java
// StringBuilder - When single-threaded environment
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb);

// StringBuffer - When multi-threaded environment
StringBuffer sb2 = new StringBuffer("Hello");
sb2.append(" World");
System.out.println(sb2);
```

**Hinglish:** StringBuilder faster hai lekin thread-safe nahi. StringBuffer thread-safe hai lekin thoda slow. Single-threaded mein StringBuilder use karo.

---

## 📦 Wrapper Classes & Autoboxing

### What are Wrapper Classes?

Wrapper classes convert primitive types to objects.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    PRIMITIVE vs WRAPPER                              │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Primitive          Wrapper Class                                   │
│   ─────────         ─────────────                                   │
│   int               → Integer                                      │
│   byte              → Byte                                         │
│   short             → Short                                        │
│   long              → Long                                         │
│   float             → Float                                        │
│   double            → Double                                       │
│   char              → Character                                    │
│   boolean           → Boolean                                      │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Why Wrapper Classes?

```java
// 1. Collections don't support primitives
// ArrayList<int> - ❌ Not allowed
ArrayList<Integer> list = new ArrayList<>();  // ✅ Works

// 2. Need objects for synchronization
// 3. null value possible in wrappers
Integer i = null;  // Allowed
// int i = null;    // ❌ Not allowed

// 3. Utility methods
int x = Integer.parseInt("100");
double y = Double.parseDouble("3.14");
String s = Integer.toBinaryString(10);  // "1010"
```

### Creating Wrapper Objects:

```java
class WrapperDemo {
    public static void main(String args[]) {
        // Method 1: Using constructor (deprecated but works)
        Integer i1 = new Integer(100);
        Double d1 = new Double(3.14);
        
        // Method 2: Using valueOf() (preferred)
        Integer i2 = Integer.valueOf(100);
        Double d2 = Double.valueOf(3.14);
        
        // Method 3: Autoboxing (automatic conversion)
        Integer i3 = 100;  // Automatic!
        Double d3 = 3.14;  // Automatic!
    }
}
```

### Autoboxing and Unboxing:

```java
class AutoboxingDemo {
    public static void main(String args[]) {
        // Autoboxing: Primitive → Wrapper
        Integer i = 10;  // Compiler converts to Integer.valueOf(10)
        
        // Unboxing: Wrapper → Primitive
        int j = i;  // Compiler converts to i.intValue()
        
        // In expressions
        Integer a = 10;
        Integer b = 20;
        Integer c = a + b;  // a.intValue() + b.intValue() = 30
                            // Then autoboxed to Integer
        
        // Method calls
        printValue(100);  // Autoboxing - int to Integer
        
        // Collections
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10);  // Autoboxing
        int x = list.get(0);  // Unboxing
    }
    
    static void printValue(Integer num) {
        System.out.println(num);
    }
}
```

### Integer Cache:

```java
class IntegerCacheDemo {
    public static void main(String args[]) {
        // Integer cache: -128 to 127
        Integer a = 127;
        Integer b = 127;
        System.out.println(a == b);  // true (same object)
        
        Integer c = 128;
        Integer d = 128;
        System.out.println(c == d);  // false (different objects)
        
        // Always use equals() for value comparison
        System.out.println(c.equals(d));  // true
    }
}
```

**Hinglish:** Integer objects -128 to 127 cache mein store hote hain. Isliye == comparison kabhi kabhi true deta hai. Always equals() use karo!

### Conversion Methods:

```java
class ConversionDemo {
    public static void main(String args[]) {
        String s = "100";
        
        // String to primitive
        int i = Integer.parseInt(s);
        double d = Double.parseDouble("3.14");
        boolean b = Boolean.parseBoolean("true");
        
        // String to Wrapper
        Integer i2 = Integer.valueOf(s);
        
        // Primitive to String
        String s2 = String.valueOf(100);
        String s3 = Integer.toString(100);
        
        // Wrapper to primitive
        int i3 = i2.intValue();
        double d3 = i2.doubleValue();  // Converts to double
        
        // Auto unboxing
        int i4 = i2;  // Same as i2.intValue()
    }
}
```

---

## 🧵 Multithreading

### What is Multithreading?

**Multithreading** is a Java feature that allows concurrent execution of two or more threads.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    SINGLE vs MULTI THREADING                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   SINGLE THREADING               MULTI THREADING                     │
│                                                                     │
│   ┌──────────────────┐          ┌──────────────────┐               │
│   │   Thread 1       │          │   Thread 1       │               │
│   │   ████████████   │          │   ████           │               │
│   │   ████████████   │          │       Thread 2   │               │
│   │   (100%)         │          │   ████████████   │               │
│   └──────────────────┘          └──────────────────┘               │
│                                                                     │
│   • Sequential                • Concurrent/Parallel                  │
│   • Slower                   • Faster                               │
│   • One task at a time       • Multiple tasks together              │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Thread Lifecycle:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    THREAD LIFECYCLE                                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│                         ┌───────────┐                               │
│                         │   NEW     │                               │
│                         │ (Created) │                               │
│                         └─────┬─────┘                               │
│                               │ start()                             │
│                               ▼                                     │
│                         ┌───────────┐                               │
│          ┌─────────────│ RUNNABLE  │─────────────┐                  │
│          │             │  (Ready)  │             │                  │
│          │             └─────┬─────┘             │                  │
│          │                   │                   │                  │
│          │              run() │                   │                  │
│          │                   ▼                   │                  │
│          │             ┌───────────┐             │                  │
│          │             │ RUNNING   │             │                  │
│          │             │(Executing)│             │                  │
│          │             └─────┬─────┘             │                  │
│          │                   │                   │                  │
│          │      ┌───────────┴───────────┐        │                  │
│          │      │                       │        │                  │
│          │      ▼                       ▼        │                  │
│   ┌───────────┐                   ┌───────────┐   │                  │
│   │ BLOCKED/  │                   │ TERMINATED│   │                  │
│   │ WAITING   │───────────────────│ (Finished)│   │                  │
│   └───────────┘    sleep()/wait()└───────────┘   │                  │
│                                                       │                  │
│                                                       │                  │
│                       ┌───────────┐                   │                  │
│                       │ RUNNABLE  │───────────────────┘                  │
│                       │  (Ready)  │    notify()/timeout                  │
│                       └───────────┘                                       │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Creating Threads - Two Ways:

**Method 1: Extending Thread Class**

```java
class MyThread extends Thread {
    // Override run() method
    public void run() {
        System.out.println("Thread is running!");
        for(int i = 1; i <= 5; i++) {
            System.out.println("Count: " + i);
            try {
                Thread.sleep(1000);  // 1 second pause
            } catch(InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}

class ThreadDemo {
    public static void main(String args[]) {
        MyThread t = new MyThread();  // Create thread
        
        t.start();  // Start thread (NOT run()!)
        
        // Main thread also runs
        for(int i = 1; i <= 5; i++) {
            System.out.println("Main: " + i);
        }
    }
}
```

**Hinglish:** Thread start() karne ke liye `t.start()` call karo, NOT `t.run()`. start() naya thread create karta hai, run() sirf normal method ki tarah chalega.

**Method 2: Implementing Runnable Interface**

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread running via Runnable");
        for(int i = 1; i <= 5; i++) {
            System.out.println("Runnable: " + i);
        }
    }
}

class RunnableDemo {
    public static void main(String args[]) {
        MyRunnable r = new MyRunnable();
        Thread t = new Thread(r);  // Pass Runnable to Thread
        
        t.start();
        
        System.out.println("Main thread continues...");
    }
}
```

**Hinglish:** Runnable interface implement karna better hai kyunki Java single inheritance deta hai. Agar class already kisi aur class ko extend kar rahi hai toh Runnable use karo.

### Thread Methods:

```java
class ThreadMethodsDemo implements Runnable {
    public void run() {
        System.out.println("Thread started: " + Thread.currentThread().getName());
        
        try {
            // Sleep - pause thread
            Thread.sleep(1000);
            
            // Join - wait for other thread
            // t.join();  // Wait for t to finish
            
        } catch(InterruptedException e) {
            System.out.println("Thread interrupted");
        }
        
        System.out.println("Thread finished");
    }
    
    public static void main(String args[]) {
        Thread t1 = new Thread(new ThreadMethodsDemo(), "Thread-1");
        Thread t2 = new Thread(new ThreadMethodsDemo(), "Thread-2");
        
        t1.start();  // Start first thread
        
        try {
            t1.join();  // Wait for t1 to finish
        } catch(InterruptedException e) { }
        
        t2.start();  // Start second thread
        
        // Other useful methods:
        // Thread.yield() - Give up CPU
        // t.setPriority() - Set priority
        // t.isAlive() - Check if running
    }
}
```

### Synchronization:

```java
// WITHOUT Synchronization - Data may be corrupted
class Counter {
    int count = 0;
    
    void increment() {
        count++;  // Not thread-safe!
    }
}

// WITH Synchronization - Safe but slower
class CounterSync {
    int count = 0;
    
    synchronized void increment() {
        count++;  // Thread-safe
    }
}

// Test with threads
class SyncDemo implements Runnable {
    CounterSync c = new CounterSync();
    
    public void run() {
        for(int i = 0; i < 1000; i++) {
            c.increment();
        }
    }
    
    public static void main(String args[]) throws Exception {
        SyncDemo demo = new SyncDemo();
        Thread t1 = new Thread(demo);
        Thread t2 = new Thread(demo);
        
        t1.start();
        t2.start();
        
        t1.join();
        t2.join();
        
        System.out.println("Final count: " + demo.c.count);
        // Without sync: May not be 2000 (data corruption)
        // With sync: Always 2000
    }
}
```

**Hinglish:** Synchronization se ek time pe sirf ek thread access kar sakta hai. Yeh data corruption rokta hai lekin performance slow karta hai.

### wait() and notify():

```java
class WaitNotifyDemo {
    public static void main(String args[]) {
        final String resource = "Shared Resource";
        
        Thread t1 = new Thread(() -> {
            synchronized(resource) {
                System.out.println("Thread 1: Waiting for notification");
                try {
                    resource.wait();  // Release lock and wait
                } catch(InterruptedException e) { }
                System.out.println("Thread 1: Resumed!");
            }
        });
        
        Thread t2 = new Thread(() -> {
            synchronized(resource) {
                System.out.println("Thread 2: Doing work");
                resource.notify();  // Notify waiting thread
                System.out.println("Thread 2: Notification sent");
            }
        });
        
        t1.start();
        t2.start();
    }
}
```

---

## 📚 Collections Framework

### What is Collections?

**Collections** is a framework that provides classes and interfaces to store, manipulate, and manage groups of objects.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    COLLECTIONS HIERARCHY                             │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│                       Iterable                                       │
│                          │                                          │
│                       Collection                                     │
│                      ╱   │   ╲                                      │
│                     ╱    │    ╲                                     │
│                List     Set    Queue                                 │
│               ╱╲        │╲      │                                   │
│              ╱  ╲   SortedSet │                                    │
│         ArrayList  HashSet   PriorityQueue                           │
│        LinkedList TreeSet                                           │
│        Vector    LinkedHashSet                                       │
│        Stack                                                           │
│                                                                     │
│   Map (Separate Hierarchy)                                            │
│      ╱│╲                                                            │
│     ╱ │ ╲                                                           │
│ HashMap  TreeMap  LinkedHashMap                                     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### List Interface:

**List** - Ordered collection that allows duplicates.

```java
import java.util.*;

class ListDemo {
    public static void main(String args[]) {
        // ArrayList - Resizable array
        ArrayList<String> al = new ArrayList<>();
        al.add("Apple");
        al.add("Banana");
        al.add("Mango");
        al.add("Apple");  // Duplicates allowed
        
        System.out.println(al);  // [Apple, Banana, Mango, Apple]
        
        // Access elements
        System.out.println(al.get(1));  // Banana
        System.out.println(al.size());  // 4
        System.out.println(al.indexOf("Apple"));  // 0
        System.out.println(al.lastIndexOf("Apple"));  // 3
        
        // Modify
        al.set(1, "Grapes");
        System.out.println(al);  // [Apple, Grapes, Mango, Apple]
        
        // Remove
        al.remove("Apple");  // Removes first occurrence
        System.out.println(al);  // [Grapes, Mango, Apple]
        
        // Iterate
        for(String s : al) {
            System.out.println(s);
        }
        
        // LinkedList - Doubly linked list
        LinkedList<Integer> ll = new LinkedList<>();
        ll.add(10);
        ll.add(20);
        ll.addFirst(5);   // Add at beginning
        ll.addLast(30);   // Add at end
        System.out.println(ll);  // [5, 10, 20, 30]
        
        // Vector - Synchronized (thread-safe)
        Vector<String> v = new Vector<>();
        v.add("Hello");
        
        // Stack - LIFO
        Stack<Integer> s = new Stack<>();
        s.push(10);
        s.push(20);
        System.out.println(s.pop());  // 20 (removed)
        System.out.println(s.peek()); // 10 (view top)
    }
}
```

### Set Interface:

**Set** - Unordered collection that does NOT allow duplicates.

```java
import java.util.*;

class SetDemo {
    public static void main(String args[]) {
        // HashSet - No order, fastest
        HashSet<String> hs = new HashSet<>();
        hs.add("Apple");
        hs.add("Banana");
        hs.add("Mango");
        hs.add("Apple");  // Ignored (duplicate)
        
        System.out.println(hs);  // [Banana, Mango, Apple] (random order)
        
        // LinkedHashSet - Maintains insertion order
        LinkedHashSet<String> lhs = new LinkedHashSet<>();
        lhs.add("Apple");
        lhs.add("Banana");
        lhs.add("Mango");
        System.out.println(lhs);  // [Apple, Banana, Mango]
        
        // TreeSet - Sorted order (ascending)
        TreeSet<String> ts = new TreeSet<>();
        ts.add("Banana");
        ts.add("Apple");
        ts.add("Mango");
        System.out.println(ts);  // [Apple, Banana, Mango]
        
        // Set operations
        HashSet<Integer> set1 = new HashSet<>();
        set1.add(1); set1.add(2); set1.add(3); set1.add(4);
        
        HashSet<Integer> set2 = new HashSet<>();
        set2.add(3); set2.add(4); set2.add(5); set2.add(6);
        
        // Union
        HashSet<Integer> union = new HashSet<>(set1);
        union.addAll(set2);
        System.out.println("Union: " + union);  // [1, 2, 3, 4, 5, 6]
        
        // Intersection
        HashSet<Integer> inter = new HashSet<>(set1);
        inter.retainAll(set2);
        System.out.println("Intersection: " + inter);  // [3, 4]
        
        // Difference
        HashSet<Integer> diff = new HashSet<>(set1);
        diff.removeAll(set2);
        System.out.println("Difference: " + diff);  // [1, 2]
    }
}
```

### Map Interface:

**Map** - Key-Value pairs, keys must be unique.

```java
import java.util.*;

class MapDemo {
    public static void main(String args[]) {
        // HashMap - No order
        HashMap<Integer, String> hm = new HashMap<>();
        hm.put(1, "Java");
        hm.put(2, "Python");
        hm.put(3, "C++");
        hm.put(1, "JavaScript");  // Overwrites key 1
        
        System.out.println(hm);  // {1=JavaScript, 2=Python, 3=C++}
        
        // Access
        System.out.println(hm.get(2));  // Python
        System.out.println(hm.getOrDefault(4, "Not Found"));  // Not Found
        
        // Check
        System.out.println(hm.containsKey(1));  // true
        System.out.println(hm.containsValue("Java"));  // false (replaced)
        
        // Remove
        hm.remove(2);
        
        // Iterate
        for(Map.Entry<Integer, String> e : hm.entrySet()) {
            System.out.println(e.getKey() + ": " + e.getValue());
        }
        
        // Keys only
        for(Integer key : hm.keySet()) {
            System.out.println(key);
        }
        
        // Values only
        for(String val : hm.values()) {
            System.out.println(val);
        }
        
        // LinkedHashMap - Maintains insertion order
        LinkedHashMap<String, Integer> lhm = new LinkedHashMap<>();
        lhm.put("A", 1);
        lhm.put("B", 2);
        
        // TreeMap - Sorted by keys
        TreeMap<String, Integer> tm = new TreeMap<>();
        tm.put("Zebra", 1);
        tm.put("Apple", 2);
        System.out.println(tm);  // {Apple=2, Zebra=1} (sorted)
    }
}
```

### Queue Interface:

```java
import java.util.*;

class QueueDemo {
    public static void main(String args[]) {
        // PriorityQueue - Elements sorted by priority
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        pq.add(30);
        pq.add(10);
        pq.add(50);
        pq.add(20);
        
        System.out.println(pq.peek());  // 10 (minimum by default)
        System.out.println(pq.poll()); // 10 (removes and returns)
        
        // ArrayDeque - Double-ended queue
        ArrayDeque<String> adq = new ArrayDeque<>();
        adq.addFirst("First");
        adq.addLast("Last");
        System.out.println(adq);  // [First, Last]
    }
}
```

### Iterators:

```java
import java.util.*;

class IteratorDemo {
    public static void main(String args[]) {
        ArrayList<String> al = new ArrayList<>();
        al.add("A"); al.add("B"); al.add("C");
        
        // 1. Using Iterator
        Iterator<String> it = al.iterator();
        while(it.hasNext()) {
            String s = it.next();
            System.out.println(s);
            if(s.equals("B")) {
                it.remove();  // Remove while iterating
            }
        }
        
        // 2. Using ListIterator (bidirectional)
        ListIterator<String> lit = al.listIterator();
        while(lit.hasNext()) {
            System.out.println(lit.next());
        }
        while(lit.hasPrevious()) {
            System.out.println(lit.previous());
        }
        
        // 3. Enhanced for loop
        for(String s : al) {
            System.out.println(s);
        }
        
        // 4. forEach (Java 8+)
        al.forEach(s -> System.out.println(s));
    }
}
```

---

## 📁 File I/O

### File Class:

```java
import java.io.*;

class FileDemo {
    public static void main(String args[]) {
        // Create File object
        File f = new File("test.txt");
        
        // Check properties
        System.out.println("Exists: " + f.exists());
        System.out.println("Is File: " + f.isFile());
        System.out.println("Is Directory: " + f.isDirectory());
        System.out.println("Length: " + f.length());
        System.out.println("Can Read: " + f.canRead());
        System.out.println("Can Write: " + f.canWrite());
        System.out.println("Hidden: " + f.isHidden());
        
        // Create/Manage
        File f2 = new File("newfile.txt");
        // f2.createNewFile();
        // f2.delete();
        
        // List directory contents
        File dir = new File("/path/to/directory");
        String files[] = dir.list();
        for(String s : files) {
            System.out.println(s);
        }
    }
}
```

### Byte Streams:

```java
import java.io.*;

class ByteStreamDemo {
    public static void main(String args[]) throws IOException {
        // Writing bytes (FileOutputStream)
        FileOutputStream fos = new FileOutputStream("output.bin");
        byte[] data = {65, 66, 67};  // A, B, C
        fos.write(data);
        fos.close();
        
        // Reading bytes (FileInputStream)
        FileInputStream fis = new FileInputStream("output.bin");
        int byteData;
        while((byteData = fis.read()) != -1) {  // -1 means EOF
            System.out.print((char)byteData + " ");
        }
        fis.close();
    }
}
```

### Character Streams:

```java
import java.io.*;

class CharacterStreamDemo {
    public static void main(String args[]) throws IOException {
        // Writing text (FileWriter)
        FileWriter fw = new FileWriter("output.txt");
        fw.write("Hello Java!");
        fw.write("\nWelcome to File I/O");
        fw.close();
        
        // Reading text (FileReader)
        FileReader fr = new FileReader("output.txt");
        int ch;
        while((ch = fr.read()) != -1) {
            System.out.print((char)ch);
        }
        fr.close();
    }
}
```

### Buffered Streams (Efficient):

```java
import java.io.*;

class BufferedDemo {
    public static void main(String args[]) throws IOException {
        // BufferedWriter - Faster writing
        BufferedWriter bw = new BufferedWriter(new FileWriter("buffered.txt"));
        bw.write("Line 1");
        bw.newLine();  // Add newline
        bw.write("Line 2");
        bw.close();
        
        // BufferedReader - Faster reading, has readLine()
        BufferedReader br = new BufferedReader(new FileReader("buffered.txt"));
        String line;
        while((line = br.readLine()) != null) {
            System.out.println(line);
        }
        br.close();
        
        // PrintWriter - Easy printing
        PrintWriter pw = new PrintWriter(new FileWriter("print.txt"));
        pw.println("Hello");
        pw.printf("Value: %d", 100);  // Formatted output
        pw.close();
    }
}
```

### Scanner Class:

```java
import java.util.Scanner;
import java.io.*;

class ScannerDemo {
    public static void main(String args[]) throws IOException {
        // Reading from console
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter name: ");
        String name = sc.nextLine();
        System.out.print("Enter age: ");
        int age = sc.nextInt();
        
        // Reading from file
        Scanner fileSc = new Scanner(new File("input.txt"));
        while(fileSc.hasNext()) {
            System.out.println(fileSc.nextLine());
        }
        
        // Different data types
        int num = sc.nextInt();
        double d = sc.nextDouble();
        boolean b = sc.nextBoolean();
    }
}
```

### Serialization:

```java
import java.io.*;

class Student implements Serializable {
    String name;
    int rollNo;
    transient int password;  // Will NOT be serialized
    
    Student(String n, int r, int p) {
        name = n;
        rollNo = r;
        password = p;
    }
}

class SerializationDemo {
    public static void main(String args[]) throws Exception {
        Student s1 = new Student("Rahul", 101, 12345);
        
        // Serialization - Object to bytes
        FileOutputStream fos = new FileOutputStream("student.ser");
        ObjectOutputStream oos = new ObjectOutputStream(fos);
        oos.writeObject(s1);
        oos.close();
        
        // Deserialization - Bytes to Object
        FileInputStream fis = new FileInputStream("student.ser");
        ObjectInputStream ois = new ObjectInputStream(fis);
        Student s2 = (Student) ois.readObject();
        ois.close();
        
        System.out.println(s2.name + " " + s2.rollNo);
        // s2.password will be 0 (default) because it was transient
    }
}
```

---

## 🎯 Generics

### What are Generics?

**Generics** enable type safety at compile time. They allow you to write code that works with different types while providing compile-time type checking.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    WHY GENERICS?                                      │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   WITHOUT GENERICS:                                                  │
│   ArrayList list = new ArrayList();                                 │
│   list.add("Hello");                                                │
│   list.add(100);                                                    │
│   String s = (String) list.get(1);  // Runtime Error!               │
│                                                                     │
│   WITH GENERICS:                                                    │
│   ArrayList<String> list = new ArrayList<>();                       │
│   list.add("Hello");                                                │
│   // list.add(100);  // Compile Error!                             │
│   String s = list.get(0);  // No casting needed!                   │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Generic Classes:

```java
// Generic class with one type parameter
class Box<T> {
    private T content;
    
    public void set(T content) {
        this.content = content;
    }
    
    public T get() {
        return content;
    }
}

class GenericClassDemo {
    public static void main(String args[]) {
        // Integer box
        Box<Integer> intBox = new Box<>();
        intBox.set(100);
        int value = intBox.get();  // No casting!
        
        // String box
        Box<String> strBox = new Box<>();
        strBox.set("Hello");
        String str = strBox.get();
        
        // Multiple type parameters
        Box2<String, Integer> pair = new Box2<>();
        pair.setKey("Age");
        pair.setValue(25);
    }
}

class Box2<K, V> {
    private K key;
    private V value;
    
    public void setKey(K key) { this.key = key; }
    public void setValue(V value) { this.value = value; }
    public K getKey() { return key; }
    public V getValue() { return value; }
}
```

### Generic Methods:

```java
class GenericMethodDemo {
    // Generic method
    public static <T> void printArray(T[] arr) {
        for(T element : arr) {
            System.out.print(element + " ");
        }
        System.out.println();
    }
    
    // Generic method with return type
    public static <T> T findFirst(T[] arr) {
        return arr[0];
    }
    
    // Bounded type parameter
    public static <T extends Number> double sum(T a, T b) {
        return a.doubleValue() + b.doubleValue();
    }
    
    public static void main(String args[]) {
        Integer[] intArr = {1, 2, 3};
        String[] strArr = {"A", "B", "C"};
        
        printArray(intArr);  // 1 2 3
        printArray(strArr);  // A B C
        
        System.out.println(sum(10, 20));  // 30.0
        System.out.println(sum(3.14, 2.86));  // 6.0
    }
}
```

### Wildcards:

```java
import java.util.*;

class WildcardDemo {
    // ? extends Number - Read only (Upper bound)
    public static void printNumbers(List<? extends Number> list) {
        for(Number n : list) {
            System.out.println(n.doubleValue());
        }
        // list.add(10);  // Error! Can't add
    }
    
    // ? super Integer - Write only (Lower bound)
    public static void addNumbers(List<? super Integer> list) {
        list.add(10);
        list.add(20);
        // Reading returns Object type
    }
    
    // ? - unbounded (Read/Write but unchecked)
    public static void printAll(List<?> list) {
        for(Object o : list) {
            System.out.println(o);
        }
    }
    
    public static void main(String args[]) {
        List<Integer> intList = Arrays.asList(1, 2, 3);
        List<Double> doubleList = Arrays.asList(1.1, 2.2);
        List<String> strList = Arrays.asList("A", "B");
        
        printNumbers(intList);    // Works
        printNumbers(doubleList); // Works
        // printNumbers(strList); // Error!
        
        addNumbers(intList);  // Works
        // addNumbers(doubleList); // Error!
        
        printAll(intList);   // Works
        printAll(strList);   // Works
    }
}
```

### Annotations:

```java
// Built-in Annotations

// @Override - Method overrides parent method
class Parent {
    void show() { }
}

class Child extends Parent {
    @Override
    void show() {  // Compiler checks if parent has this method
        System.out.println("Child show");
    }
}

// @Deprecated - Mark as deprecated
@Deprecated
class OldClass {
    void oldMethod() { }
}

// @SuppressWarnings - Suppress compiler warnings
class SuppressDemo {
    @SuppressWarnings("unchecked")
    void uncheckedCode() {
        ArrayList list = new ArrayList();  // Raw type warning suppressed
    }
    
    @SuppressWarnings("deprecation")
    void deprecatedCode() {
        // Using deprecated code - warning suppressed
    }
}

// @FunctionalInterface - Lambda expression support
@FunctionalInterface
interface MyFunction {
    int apply(int a, int b);
}
```

---

## 🎯 Practice Questions

### MCQs:

**Q1. Which package is automatically imported?**
- A) java.util
- B) java.lang ✅
- C) java.io
- D) java.net

> **Hinglish:** java.lang automatically import hota hai har Java program mein.

---

**Q2. What is the output?**
```java
String s1 = "Java";
String s2 = "Java";
String s3 = new String("Java");
System.out.println(s1 == s2);
System.out.println(s1 == s3);
```
- A) true true
- B) true false ✅
- C) false true
- D) false false

> **Hinglish:** String pool mein same literal same object hota hai. new keyword se naya object banata hai.

---

**Q3. Which collection does NOT allow duplicates?**
- A) List
- B) ArrayList
- C) Set ✅
- D) Vector

> **Hinglish:** Set interface duplicates allow nahi karta. List allow karta hai.

---

**Q4. How to create a thread?**
- A) extends Thread or implements Runnable ✅
- B) implements Thread
- C) extends Runnable
- D) Only extends Thread

> **Hinglish:** Thread do tarike se bana sakte hain: Thread class extend karo ya Runnable implement karo.

---

**Q5. What is autoboxing?**
- A) Primitive to Wrapper
- B) Wrapper to Primitive
- C) String to Primitive
- D) None

> **Hinglish:** Autoboxing compiler ka feature hai jo primitive ko automatically wrapper mein convert karta hai.

---

## 📋 Quick Reference

### Package Keywords:
```
package packagename;      → Create package
import package.Class;     → Import single class
import package.*;         → Import all classes
```

### String Methods:
```
length()           → Characters count
charAt(index)      → Character at index
substring(start,end)→ Substring
equals(str)        → Content comparison
indexOf(str)       → First occurrence
replace(old,new)   → Replace
split(delimiter)   → Split to array
trim()             → Remove spaces
```

### StringBuffer Methods:
```
append(str)        → Add at end
insert(pos, str)   → Insert at position
replace(s,e,str)   → Replace
delete(s,e)        → Delete
reverse()          → Reverse string
capacity()         → Buffer size
```

### Collections Quick Reference:
```
List:    ArrayList, LinkedList, Vector, Stack (Ordered, Duplicates OK)
Set:     HashSet, LinkedHashSet, TreeSet (No duplicates)
Map:     HashMap, LinkedHashMap, TreeMap (Key-Value)
Queue:   PriorityQueue, ArrayDeque
```

### Thread Methods:
```
start()    → Start thread
run()      → Code to execute
sleep(ms)  → Pause thread
join()     → Wait for thread
yield()    → Give up CPU
synchronized → Thread-safe block
```

---

## 🎓 Day 7 Summary

### What We Learned:
```
✅ Packages - Organizing code
✅ String Handling - Immutable strings, String pool
✅ StringBuffer/StringBuilder - Mutable strings
✅ Wrapper Classes - Primitive to Object
✅ Autoboxing/Unboxing - Automatic conversion
✅ Multithreading - Concurrent execution
✅ Collections - Lists, Sets, Maps
✅ File I/O - Reading/Writing files
✅ Generics - Type safety
✅ Annotations - Metadata
```

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

⬅️ **[Day 6 - Applet & Graphics](../Day-6/README.md)** | **[Bonus Questions](../Bonus/BONUS-Questions.md)** ➡️

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day7)
