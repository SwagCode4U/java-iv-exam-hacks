# 📚 Day 4: Exception Handling

![Java](https://img.shields.io/badge/Java-Exception%20Handling-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%204-success?style=for-the-badge)
![Duration](https://img.shields.io/badge/Duration-4%20Hours-yellow?style=for-the-badge)

> *Learning to handle errors gracefully like a pro!*

---

## 🌟 Welcome to Day 4!

Today we learn about Exception Handling - one of the most important topics in Java. Exceptions are runtime errors that can crash your program if not handled properly.

**Estimated Time:** 4 Hours  
**Prerequisites:** Days 1-3  
**Goal:** Master exception handling with try-catch-finally

---

## 📖 Table of Contents

1. [What is Exception?](#what-is-exception)
2. [Exception Hierarchy](#exception-hierarchy)
3. [try-catch-finally](#try-catch-finally)
4. [throw vs throws](#throw-vs-throws)
5. [Common Exceptions](#common-exceptions)
6. [Custom Exceptions](#custom-exceptions)
7. [Practice Questions](#-practice-questions)

---

## ⚠️ What is Exception?

### Definition:
An **Exception** is an unwanted or unexpected event that occurs during program execution, disrupting the normal flow of the program.

### In Simple Terms:
```
┌─────────────────────────────────────────────────────────────┐
│                    NORMAL EXECUTION                         │
│                                                             │
│   Statement 1  ──►  Statement 2  ──►  Statement 3         │
│        ✅                ✅                ✅                │
│                                                             │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                   EXCEPTION OCCURS                         │
│                                                             │
│   Statement 1  ──►  Statement 2  ──►  Statement 3          │
│        ✅                ✅                ✅                │
│                                              ↓              │
│                                    ┌──────────┐            │
│                                    │EXCEPTION!│            │
│                                    │ Division │            │
│                                    │   by 0   │            │
│                                    └──────────┘            │
│                                              ↓              │
│                                       PROGRAM CRASHES       │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│              WITH EXCEPTION HANDLING                       │
│                                                             │
│   Statement 1  ──►  Statement 2  ──►  Statement 3          │
│        ✅                ✅                ✅                │
│                                              ↓              │
│                                    ┌──────────┐            │
│                                    │EXCEPTION!│            │
│                                    └────┬─────┘            │
│                                         ↓                  │
│                                    ┌──────────┐            │
│                                    │  try     │            │
│                                    │   ↓      │            │
│                                    │  catch   │            │
│                                    │   ↓      │            │
│                                    │ handle!  │            │
│                                    └────┬─────┘            │
│                                         ↓                  │
│                                    ┌──────────┐            │
│                                    │ Finally  │            │
│                                    │ continues│            │
│                                    └──────────┘            │
│                                              ↓              │
│                                        PROGRAM OK!         │
└─────────────────────────────────────────────────────────────┘
```

### Exception vs Error:

| Exception | Error |
|----------|-------|
| Recoverable | Irrecoverable |
| Caused by program | Caused by system |
| Can be handled | Cannot be handled |
| Example: ArithmeticException | Example: OutOfMemoryError |

---

## 📊 Exception Hierarchy

```
                    Throwable
                         │
          ┌──────────────┴──────────────┐
          │                              │
        Error                          Exception
   (Irrecoverable)                (Recoverable)
          │                              │
   ┌──────┴──────┐            ┌─────────┴─────────┐
   │             │            │                   │
OutOfMemory  StackOverflow  Checked           Unchecked
   │             │            │                   │
VirtualMachine Assertion    IOException         RuntimeException
  Error           Error    SQLException         │
                               │        ┌────────┴────────┐
                          ClassNotFound     │                 │
                            Exception   ArithmeticException │
                                         NullPointerException│
                                         ArrayIndexOutOfBounds│
                                         NumberFormatException│
```

### Types of Exceptions:

**1. Checked Exceptions (Compile-time):**
```java
// Checked at COMPILE TIME by compiler
// Compiler forces you to handle them

import java.io.*;

class CheckedDemo {
    void readFile() throws IOException {
        FileReader f = new FileReader("test.txt");  // IOException
    }
}
```

**2. Unchecked Exceptions (Runtime):**
```java
// Not checked at compile time
// Occur at RUNTIME

int result = 10 / 0;           // ArithmeticException
String s = null;
s.length();                      // NullPointerException
int[] arr = new int[5];
arr[10] = 100;                  // ArrayIndexOutOfBoundsException
```

**3. Errors:**
```java
// Irrecoverable - program will crash

void recursive() {
    recursive();  // StackOverflowError
}

int[] huge = new int[Integer.MAX_VALUE];  // OutOfMemoryError
```

---

## 🔄 try-catch-finally

### Complete Syntax:
```java
try {
    // Risky code that may throw exception
    // Write code that might fail here
    
} catch (ExceptionType1 e) {
    // Handle ExceptionType1
    // This block runs if exception occurs
    
} catch (ExceptionType2 e) {
    // Handle ExceptionType2
    // This block runs if different exception occurs
    
} catch (Exception e) {
    // Handle any other exception
    // Parent exception should be last!
    
} finally {
    // ALWAYS executes regardless of exception
    // Use for cleanup code (closing files, connections, etc.)
}
```

### Example 1: Basic try-catch:
```java
public class BasicException {
    public static void main(String args[]) {
        try {
            int result = 10 / 0;  // This will throw ArithmeticException
            System.out.println("Result: " + result);  // Not executed
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero!");
            System.out.println("Error: " + e.getMessage());
        }
        
        System.out.println("Program continues...");  // This WILL execute
    }
}
```

### Example 2: try-catch-finally:
```java
public class FinallyDemo {
    public static void main(String args[]) {
        try {
            System.out.print("A ");
            int result = 10 / 2;  // No exception here
            System.out.print("B ");
        } catch (ArithmeticException e) {
            System.out.print("C ");
        } finally {
            System.out.print("D ");  // ALWAYS executes
        }
        
        System.out.print(" E");
    }
}

// Output: A B D E
```

### Example 3: Multiple catch blocks:
```java
public class MultiCatch {
    public static void main(String args[]) {
        try {
            int[] arr = new int[5];
            arr[10] = 100;  // ArrayIndexOutOfBoundsException
            
            // If above line worked:
            // int result = 10 / 0;  // Would be ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Error: " + e.getMessage());
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Error: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("General Error: " + e.getMessage());
        } finally {
            System.out.println("Finally block executed");
        }
    }
}
```

### Example 4: Exception with return:
```java
public class ReturnDemo {
    static int test() {
        try {
            System.out.println("Inside try");
            return 100;  // Will try to return
        } catch (Exception e) {
            System.out.println("Inside catch");
            return 200;
        } finally {
            System.out.println("Inside finally");  // ALWAYS executes!
            // return 300;  // If uncommented, this return wins!
        }
    }
    
    public static void main(String args[]) {
        int result = test();
        System.out.println("Result: " + result);
    }
}

// Output:
// Inside try
// Inside finally
// Result: 100
```

### Important Rules:
```java
// Rule 1: Child exception first, then parent exception
try {
    int[] arr = new int[5];
    arr[10] = 100;
} catch (ArrayIndexOutOfBoundsException e) {  // ✅ Child first
    System.out.println("Array error");
} catch (Exception e) {  // ✅ Parent last
    System.out.println("General error");
}

// Rule 2: Parent cannot come before child
try {
    int[] arr = new int[5];
    arr[10] = 100;
} catch (Exception e) {  // ❌ Parent first - never reaches Array catch!
    System.out.println("General error");
} catch (ArrayIndexOutOfBoundsException e) {  // ❌ Dead code!
    System.out.println("Array error");
}
```

---

## ↗️ throw vs throws

### throw (Singular - Throw):

Used to **manually throw** an exception.

```java
// Syntax: throw new ExceptionType("message");

void validate(int age) {
    if (age < 18) {
        // Manually throw exception
        throw new ArithmeticException("Age must be 18 or above!");
    }
    System.out.println("Valid age");
}

// Usage
public class ThrowDemo {
    public static void main(String args[]) {
        Validate v = new Validate();
        v.validate(15);  // Will throw ArithmeticException
    }
}
```

### throws (Plural - Declares):

Used to **declare** that a method may throw exceptions.

```java
// Syntax: returnType method() throws ExceptionType

import java.io.*;

class FileHandler {
    // Declare that this method may throw IOException
    void readFile() throws IOException {
        FileReader fr = new FileReader("test.txt");
        // File reading code
    }
}

// Usage
public class ThrowsDemo {
    public static void main(String args[]) {
        FileHandler fh = new FileHandler();
        try {
            fh.readFile();  // Must handle the declared exception
        } catch (IOException e) {
            System.out.println("File error: " + e.getMessage());
        }
    }
}
```

### throw vs throws Comparison:

| Aspect | throw | throws |
|--------|-------|--------|
| **Purpose** | Throw exception explicitly | Declare exceptions |
| **Syntax** | `throw new Exception()` | `void m() throws Exception` |
| **Location** | Inside method body | With method signature |
| **Number** | One exception at a time | Multiple exceptions |
| **Type** | Any exception | Usually checked exceptions |

### Combined Example:
```java
// Custom exception class
class InvalidAgeException extends Exception {
    InvalidAgeException(String msg) {
        super(msg);
    }
}

class User {
    // Method declares it throws, then manually throws
    void register(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Must be 18+ to register!");
        }
        System.out.println("Registration successful!");
    }
}

public class CombinedDemo {
    public static void main(String args[]) {
        User u = new User();
        try {
            u.register(15);  // Will throw
        } catch (InvalidAgeException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

---

## 🔥 Common Exceptions

### 1. ArithmeticException:
```java
// Division by zero

try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero!");
}
```

### 2. NullPointerException:
```java
// Accessing null object

try {
    String s = null;
    int length = s.length();  // NullPointerException
} catch (NullPointerException e) {
    System.out.println("Object is null!");
}
```

### 3. ArrayIndexOutOfBoundsException:
```java
// Accessing invalid array index

try {
    int[] arr = new int[5];
    arr[10] = 100;  // ArrayIndexOutOfBoundsException
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Invalid array index!");
}
```

### 4. NumberFormatException:
```java
// Invalid number format

try {
    String str = "abc";
    int num = Integer.parseInt(str);  // NumberFormatException
} catch (NumberFormatException e) {
    System.out.println("Invalid number format!");
}
```

### 5. StringIndexOutOfBoundsException:
```java
// Invalid string index

try {
    String s = "Hello";
    char c = s.charAt(10);  // StringIndexOutOfBoundsException
} catch (StringIndexOutOfBoundsException e) {
    System.out.println("Invalid string index!");
}
```

---

## 🎯 Custom Exceptions

### Creating Your Own Exception:
```java
// Step 1: Create exception class extending Exception
class InvalidScoreException extends Exception {
    // Constructor
    InvalidScoreException(String msg) {
        super(msg);  // Pass message to parent
    }
}

// Step 2: Use it in your code
class Student {
    String name;
    int score;
    
    Student(String n, int s) {
        name = n;
        score = s;
    }
    
    void validate() throws InvalidScoreException {
        if (score < 0 || score > 100) {
            throw new InvalidScoreException("Score must be 0-100!");
        }
        System.out.println(name + " - Score: " + score);
    }
}

// Step 3: Handle it
public class CustomExceptionDemo {
    public static void main(String args[]) {
        Student[] students = {
            new Student("Rahul", 85),
            new Student("Priya", 105),  // Invalid
            new Student("Amit", -10)     // Invalid
        };
        
        for (Student s : students) {
            try {
                s.validate();
            } catch (InvalidScoreException e) {
                System.out.println(s.name + " - Error: " + e.getMessage());
            }
        }
    }
}
```

### Real-World Example:
```java
// Banking application with custom exceptions

class InsufficientFundsException extends Exception {
    InsufficientFundsException(double balance, double amount) {
        super("Insufficient funds! Balance: " + balance + ", Required: " + amount);
    }
}

class BankAccount {
    private double balance;
    
    BankAccount(double initialBalance) {
        balance = initialBalance;
    }
    
    void withdraw(double amount) throws InsufficientFundsException {
        if (amount > balance) {
            throw new InsufficientFundsException(balance, amount);
        }
        balance -= amount;
        System.out.println("Withdrawn: " + amount + ", New Balance: " + balance);
    }
}

public class BankDemo {
    public static void main(String args[]) {
        BankAccount acc = new BankAccount(5000);
        
        try {
            acc.withdraw(3000);  // Success
            acc.withdraw(3000);  // Will throw exception
        } catch (InsufficientFundsException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

---

## 🎯 Practice Questions

### MCQs:

**Q1. Which block is always executed?**
- A) try
- B) catch
- C) **finally** ✅
- D) throw

**Q2. Which keyword throws an exception manually?**
- A) throws
- B) **throw** ✅
- C) try
- D) catch

**Q3. Which is a checked exception?**
- A) ArithmeticException
- B) NullPointerException
- C) **IOException** ✅
- D) ArrayIndexOutOfBoundsException

**Q4. What is the output?**

```java
try {
    System.out.print("A ");
    int x = 10/0;
    System.out.print("B ");
} catch (Exception e) {
    System.out.print("C ");
} finally {
    System.out.print("D");
}
```
**Answer: A C D**

**Q5. Which is NOT an unchecked exception?**
- A) ArithmeticException
- B) NullPointerException
- C) **IOException** ✅
- D) NumberFormatException

---

### Coding Questions:

**Q6. Write a program with multiple catch blocks:**
```java
public class MultiExceptionDemo {
    public static void main(String args[]) {
        try {
            int[] arr = new int[3];
            arr[5] = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic: " + e.getMessage());
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("General: " + e.getMessage());
        } finally {
            System.out.println("Finally executed");
        }
    }
}
```

**Q7. Write a program demonstrating throws:**
```java
import java.io.*;

class FileProcessor {
    void process() throws IOException {
        throw new IOException("File not found!");
    }
}

public class ThrowsDemo {
    public static void main(String args[]) {
        FileProcessor fp = new FileProcessor();
        try {
            fp.process();
        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

---

## 📋 Quick Reference

### Exception Keywords:

| Keyword | Purpose | Example |
|---------|---------|---------|
| try | Code that may throw exception | `try { }` |
| catch | Handle the exception | `catch (Exception e) { }` |
| finally | Always execute | `finally { }` |
| throw | Throw manually | `throw new Exception()` |
| throws | Declare in method | `void m() throws Exception` |

### Common Exceptions:

| Exception | When | Example |
|-----------|------|---------|
| ArithmeticException | Division by zero | `10/0` |
| NullPointerException | Null access | `null.length()` |
| ArrayIndexOutOfBoundsException | Invalid index | `arr[10]` when size=5 |
| NumberFormatException | Invalid format | `Integer.parseInt("abc")` |
| StringIndexOutOfBoundsException | Invalid string index | `"Hello".charAt(10)` |

### Exception Hierarchy:
```
Throwable
├── Error (irrecoverable)
└── Exception (recoverable)
    ├── Checked (compile-time)
    │   ├── IOException
    │   └── SQLException
    └── Unchecked (runtime)
        ├── ArithmeticException
        ├── NullPointerException
        └── ArrayIndexOutOfBoundsException
```

---

## 🎓 Day 4 Summary

### Key Takeaways:
```
✅ Exception = Runtime error that disrupts flow
✅ try = Risky code
✅ catch = Handle exception
✅ finally = Always execute (cleanup)
✅ throw = Manually throw exception
✅ throws = Declare in method signature
✅ Child exception before parent in catch
✅ finally always executes (even with return)
✅ Custom exceptions extend Exception
```

---

## 💪 Motivational Quote

> *"In the middle of difficulty lies opportunity."*
> — Albert Einstein

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

⬅️ **[Day 3 - Interface & Abstract Class](../Day-3/README.md)** | **[Day 5 - Final Revision](../Day-5/README.md)** ➡️

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day4)
