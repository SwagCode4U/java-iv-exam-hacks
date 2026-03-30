# 🔄 Java vs C++ - Complete Comparison

![Java vs C++](https://img.shields.io/badge/Java%20vs%20C%2B%2B-Comparison-orange?style=for-the-badge)
![CodersJaunt](https://img.shields.io/badge/CodersJaunt-Java%20OOP-blue?style=for-the-badge)

> *Understanding the differences between Java and C++ is essential for exams!*

---

## 📊 Quick Comparison Table

| Feature | Java | C++ |
|---------|------|-----|
| **OOP** | Pure Object-Oriented | Supports both procedural & OOP |
| **Multiple Inheritance** | Not supported via classes (use interfaces) | Supported |
| **Operator Overloading** | Not supported | Supported |
| **Pointers** | Not supported (secure) | Supported |
| **goto Statement** | Not supported | Supported |
| **Header Files** | Not required | Required |
| **Global Variables** | Not supported | Supported |
| **Platform Dependency** | Platform Independent (WORA) | Platform Dependent |
| **Compilation** | Bytecode (.class) | Machine Code (.exe) |
| **Memory Management** | Automatic (Garbage Collection) | Manual (delete keyword) |
| **Thread Support** | Built-in | Requires threading libraries |
| **Virtual Machine** | JVM required | Not required |

---

## 🎯 Detailed Differences

### 1. Multiple Inheritance

**Java:**
```java
// ❌ NOT ALLOWED via classes
class A { }
class B { }
class C extends A, B { }  // ERROR!

// ✅ ALLOWED via interfaces
interface A { }
interface B { }
class C implements A, B { }  // OK!
```

**C++:**
```cpp
// ✅ ALLOWED
class A {
    void display() { cout << "A"; }
};

class B {
    void show() { cout << "B"; }
};

class C : public A, public B {
    // Can inherit from both A and B
};
```

---

### 2. Operator Overloading

**Java:**
```java
// ❌ NOT ALLOWED
class Complex {
    int real, imag;
    
    Complex operator+(Complex c) {  // ERROR!
        // Cannot overload operators
    }
}
```

**C++:**
```cpp
// ✅ ALLOWED
class Complex {
public:
    int real, imag;
    
    Complex operator+(Complex c) {
        Complex temp;
        temp.real = real + c.real;
        temp.imag = imag + c.imag;
        return temp;
    }
};
```

---

### 3. Pointers

**Java:**
```java
// ❌ Pointers NOT supported
class Test {
    public static void main(String args[]) {
        int x = 10;
        // int *ptr = &x;  // ERROR! Pointers not allowed
        
        // But we have references!
        String s = "Hello";
        // Direct reference works
    }
}
```

**C++:**
```cpp
// ✅ Pointers fully supported
int x = 10;
int *ptr = &x;        // Pointer to x
cout << *ptr;          // Dereferencing: 10

int arr[5] = {1,2,3,4,5};
int *p = arr;          // Array name is pointer
cout << *(p + 2);     // 3
```

---

### 4. goto Statement

**Java:**
```java
// ❌ goto NOT available
class Test {
    public static void main(String args[]) {
        // Cannot use goto
        // Use break, continue, return instead
    }
}
```

**C++:**
```cpp
// ✅ goto IS available
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    
    loop:
    cout << i << " ";
    i++;
    
    if (i <= 5)
        goto loop;  // Jumps to 'loop' label
    
    return 0;
}
// Output: 0 1 2 3 4 5
```

---

### 5. Header Files

**Java:**
```java
// ❌ No header files
// Just use import statements
import java.util.Scanner;
import java.io.*;

public class Hello {
    public static void main(String[] args) {
        System.out.println("No headers!");
    }
}
```

**C++:**
```cpp
// ✅ Header files required
#include <iostream>    // Input/Output
#include <string>      // String handling
#include <vector>      // Vectors

using namespace std;

int main() {
    cout << "Headers required!";
    return 0;
}
```

---

### 6. Global Variables

**Java:**
```java
// ❌ Global variables NOT allowed
public class Test {
    // All variables must be in class!
    
    static int count = 0;  // Class variable, not global
    
    void display() {
        // Cannot have standalone global variables
    }
}
```

**C++:**
```cpp
// ✅ Global variables allowed
#include <iostream>
using namespace std;

int globalVar = 100;  // Global variable

class Test {
public:
    void display() {
        cout << globalVar;  // Access global variable
    }
};
```

---

### 7. Platform Independence

**Java:**
```
┌──────────────┐
│  Source Code │
│  (.java)     │
└──────┬───────┘
       ↓ javac
┌──────────────┐
│   Bytecode    │
│  (.class)    │
└──────┬───────┘
       ↓
    ┌───────┐
    │  JVM  │
    └───────┘
       ↓
┌──────┴───────┐
│ Windows JVM  │
│  Linux JVM  │   ← Same bytecode runs everywhere!
│   Mac JVM   │
└─────────────┘
```

**C++:**
```
┌──────────────┐
│  Source Code │
│   (.cpp)    │
└──────┬──────┘
       ↓ g++
┌──────────────┐
│  Object Code │
│   (.o)       │
└──────┬───────┘
       ↓
┌──────────────┐
│ Windows .exe │   ← Different executables
│ Linux Binary │      for each platform!
│  Mac Binary  │
└──────────────┘
```

---

### 8. Memory Management

**Java:**
```java
// ✅ Automatic garbage collection
class Test {
    public static void main(String args[]) {
        String s = new String("Hello");
        s = null;  // Object becomes eligible for GC
        // No need to free memory manually
        // Garbage collector automatically frees memory
    }
}
```

**C++:**
```cpp
// ✅ Manual memory management
#include <iostream>
using namespace std;

int main() {
    int* ptr = new int[5];  // Allocate memory
    
    ptr[0] = 10;
    cout << ptr[0];
    
    delete[] ptr;  // Must free memory manually!
    ptr = NULL;
    
    return 0;
}
```

---

## 🎯 Exam Questions: Java vs C++

### Q1. Java does not support which of the following?
- A) Inheritance
- B) Multiple Inheritance via classes ✅
- C) Interfaces
- D) Packages

> **Hinglish:** Java mein classes se multiple inheritance nahi kar sakte. Interfaces se kar sakte ho.

---

### Q2. Which feature makes Java more secure than C++?
- A) Compiled language
- B) No pointers ✅
- C) Object-oriented
- D) Platform independent

> **Hinglish:** Java mein pointers nahi hain, isliye yeh C++ se zyada secure hai.

---

### Q3. C++ uses _____ for memory deallocation:
- A) Garbage Collector
- B) delete keyword ✅
- C) free() function
- D) System.gc()

> **Hinglish:** C++ mein memory free karne ke liye delete keyword use hota hai.

---

### Q4. Which is TRUE about operator overloading?
- A) Supported in both Java and C++
- B) Supported only in C++ ✅
- C) Supported only in Java
- D) Not supported in either

> **Hinglish:** Operator overloading sirf C++ mein supported hai, Java mein nahi.

---

### Q5. Header files are required in:
- A) Java
- B) C++
- C) Both
- D) Neither

> **Hinglish:** Header files sirf C++ mein zaroori hain, Java mein nahi.

---

## 📋 Summary Table for Quick Revision

| Feature | Java | C++ | Who Wins? |
|---------|------|-----|----------|
| Multiple Inheritance | ❌ Classes, ✅ Interfaces | ✅ Classes | Tie |
| Operator Overloading | ❌ | ✅ | C++ |
| Pointers | ❌ (Safe) | ✅ (Unsafe) | Java |
| goto | ❌ | ✅ | Java |
| Header Files | ❌ | ✅ | Java |
| Global Variables | ❌ | ✅ | C++ |
| Platform Independent | ✅ | ❌ | Java |
| Memory Management | Auto | Manual | Java |
| Speed | Slightly slower | Faster | C++ |

---

## 💡 Key Points for Exam

1. **Java = Pure OOP, C++ = Hybrid** (supports procedural)
2. **Java = No pointers, C++ = Full pointer support**
3. **Java = Automatic GC, C++ = Manual delete**
4. **Java = Bytecode, C++ = Machine code**
5. **Java = WORA (Write Once Run Anywhere), C++ = Platform dependent**
6. **Multiple inheritance in Java = Via interfaces only**
7. **No operator overloading in Java**
8. **No header files, goto, or global variables in Java**

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.JavaVSCPlusPlus)
