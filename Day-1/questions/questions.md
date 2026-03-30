# 📚 Day 1: OOP Concepts & Java Basics - Question Bank

![Java](https://img.shields.io/badge/Java-OOP%20Basics-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%201-success?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-50+-blue?style=for-the-badge)

> *Practice makes perfect! Let's master OOP fundamentals!*

---

## 🎯 Section A: Multiple Choice Questions (MCQs)

### Q1. What is the full form of OOP?
- A) Object Oriented Programming ✅
- B) Object Oriented Process
- C) Object Open Programming
- D) Object Operational Programming

> **Hinglish:** OOP ka matlab **Object Oriented Programming** hai - yeh ek programming tarika hai jahan sab kuch objects ke around revolve karta hai.

---

### Q2. Java was originally called:
- A) Oak ✅
- B) Pine
- C) Maple
- D) Coffee

> **Hinglish:** Java ko pehle **Oak** naam diya gaya tha James Gosling ke dwara 1991 mein. Baad mein naam Java rakh diya gaya.

---

### Q3. Java was developed by:
- A) Microsoft
- B) Google
- C) Sun Microsystems ✅
- D) IBM

> **Hinglish:** Sun Microsystems ne Java develop kiya tha, baad mein Oracle ne acquire kar liya.

---

### Q4. Which feature allows Java to "Write Once, Run Anywhere"?
- A) Compiled
- B) Platform Independent ✅
- C) Object Oriented
- D) Secure

> **Hinglish:** Java Platform Independent hai kyunki yeh **bytecode** generate karta hai jo JVM pe run hota hai.

---

### Q5. What is the size of `int` in Java?
- A) 1 byte
- B) 2 bytes
- C) 4 bytes ✅
- D) 8 bytes

> **Hinglish:** int ka size 4 bytes hota hai (approx -2 billion to +2 billion tak store kar sakta hai).

---

### Q6. Which is NOT a primitive data type?
- A) int
- B) float
- C) String ✅
- D) char

> **Hinglish:** String ek **non-primitive/reference** type hai. Yeh ek class hai.

---

### Q7. What is the output of `System.out.println(10/3)`?
- A) 3.33
- B) 3 ✅
- C) 3.0
- D) 3.333

> **Hinglish:** Dono operands integers hain, toh result bhi integer aayega (decimal cut ho jata hai).

---

### Q8. Which is a valid identifier?
- A) 2variable
- B) variable-2
- C) _variable ✅
- D) class

> **Hinglish:** Identifier digit se start nahi ho sakta, hyphen allowed nahi, keywords use nahi kar sakte.

---

### Q9. What is the default value of boolean?
- A) 0
- B) false ✅
- C) null
- D) true

> **Hinglish:** boolean ki default value **false** hoti hai Java mein.

---

### Q10. Which operator creates objects?
- A) new ✅
- B) create
- C) make
- D) alloc

> **Hinglish:** **new** keyword memory allocate karta hai aur object create karta hai.

---

### Q11. What is the parent class of all Java classes?
- A) Base
- B) Super
- C) Object ✅
- D) Root

> **Hinglish:** Object class hai parent of all classes. Agar aap extends nahi likhte, toh automatically Object se inherit hota hai.

---

### Q12. What will `10 % 3` return?
- A) 3
- B) 1 ✅
- C) 0
- D) 3.33

> **Hinglish:** % operator remainder deta hai. 10 ÷ 3 = 3 remainder 1. Answer = 1

---

### Q13. Which loop executes at least once even if condition is false?
- A) for
- B) while
- C) do-while ✅
- D) enhanced for

> **Hinglish:** do-while **exit controlled loop** hai. Pehle execute hota hai, phir condition check hota hai.

---

### Q14. What is bytecode?
- A) Machine code
- B) Source code
- C) Intermediate code ✅
- D) Assembly code

> **Hinglish:** Bytecode Java compiler generate karta hai. Yeh machine independent intermediate code hai.

---

### Q15. Which keyword is used for static variables?
- A) final
- B) static ✅
- C) abstract
- D) void

> **Hinglish:** **static** keyword variable ko class level ka bana deta hai - sab objects share karte hain.

---

### Q16. What is the range of byte data type?
- A) -256 to 255
- B) -128 to 127 ✅
- C) 0 to 255
- D) -32768 to 32767

> **Hinglish:** byte -128 se +127 tak store kar sakta hai (1 byte = 8 bits).

---

### Q17. Which of these is not a separator?
- A) ()
- B) {}
- C) <> ✅
- D) []

> **Hinglish:** Java mein separators hain: () {} [] ; , . Angular brackets nahi hain Java mein.

---

### Q18. What is the output?
```java
int x = 5;
System.out.println(x++);
```
- A) 4
- B) 5 ✅
- C) 6
- D) Error

> **Hinglish:** x++ pehle value use karta hai, phir increment karta hai. Print hoga 5, phir x=6 ho jayega.

---

### Q19. Which is NOT an OOP concept?
- A) Encapsulation
- B) Inheritance
- C) Compilation ✅
- D) Polymorphism

> **Hinglish:** Compilation ek process hai, OOP concept nahi. OOP ke 6 concepts hain.

---

### Q20. Which operator is used for modulo division?
- A) /
- B) * 
- C) % ✅
- D) +

> **Hinglish:** % operator remainder deta hai. 10 % 3 = 1 (remainder).

---

## 🎯 Section B: Long Answer Questions

### Q21. What is OOP? Explain all 6 basic concepts of OOP with real-life examples.

**Answer:**

**OOP (Object Oriented Programming):**
OOP ek software design methodology hai jo real-world entities ko classes aur objects ke form mein model karti hai.

**Six Basic Concepts:**

**1. Object aur Class:**
```java
// Class = Blueprint/Template (jaise architect ka plan)
// Object = Blueprint se banaya ghar (actual instance)

// Class declaration
class Student {
    String name;  // Properties
    int rollNo;
    
    void study() {  // Behavior
        System.out.println("Studying...");
    }
}

// Object creation
Student s1 = new Student();
s1.name = "Rahul";
s1.study();
```

**Real-life Example:**
// Class = Car ka blueprint
// Object = Ferrari, BMW, Toyota - sab cars is blueprint se bani hain

**2. Data Abstraction:**
// Sirf essential details dikhana, internal details hide karna
// Real life: ATM - aapko sirf buttons pata hain, internal working nahi

**3. Data Encapsulation:**
// Data aur functions ko ek unit mein wrap karna
// Real life: Capsule - medicines wrapped inside

**4. Inheritance:**
// Parent ki properties child ko milna
// Real life: Beta apne parents se height, color let a hai

**5. Polymorphism:**
// Ek hi entity ka multiple forms mein appear hona
// Real life: Aap akele student ho, teacher ho, friend ho

**6. Dynamic Binding:**
// Runtime pe decide hona ki kaunsa code chalega
// Parent reference, child object - runtime pe decide

---

### Q22. Explain all Java Features in detail.

**Answer:**

**1. Compiled and Interpreted:**
```java
// Java source code -> Bytecode -> Machine code
// Two-stage process hai
Source Code (.java) 
    ↓ javac
Bytecode (.class)
    ↓ java interpreter (JVM)
Machine Code
```

**2. Platform Independent:**
```java
// Bytecode kisi bhi OS pe chal sakta hai jahan JVM ho
// "Write Once, Run Anywhere" (WORA)
```

**3. Object-Oriented:**
```java
// Pure OOP - almost everything object hai
// C++ jaisi hybrid language nahi hai
```

**4. Robust and Secure:**
```java
// - Garbage Collection: Memory automatically manage
// - Exception Handling: Errors gracefully handle
// - No Pointers: Security badhti hai
// - Strong Type Checking: Compile-time errors
```

**5. Distributed:**
```java
// RMI (Remote Method Invocation) se remote access
// Multiple computers milke kaam kar sakte hain
```

**6. Simple and Small:**
```java
// No pointers, no header files, no goto statements
// Operator overloading nahi hai
```

**7. Multithreaded:**
```java
// Multiple tasks simultaneously kar sakte ho
// Web apps, games mein bahut useful
```

**8. High Performance:**
```java
// Bytecode interpretation fast hai
// JIT compiler performance improve karta hai
```

**9. Dynamic and Extensible:**
```java
// Runtime pe naye classes load kar sakte ho
// Native methods support (C/C++)
```

---

### Q23. Explain JVM architecture and platform independence.

**Answer:**

```
┌─────────────────────────────────────────┐
│         JAVA SOURCE CODE (.java)         │
└─────────────────────────────────────────┘
                    ↓ javac
┌─────────────────────────────────────────┐
│        BYTECODE (.class file)           │
│    (Machine Independent Code)           │
└─────────────────────────────────────────┘
                    ↓
        ┌───────────────────┐
        │   JVM (Java       │
        │   Virtual Machine) │
        └───────────────────┘
           ↓       ↓       ↓
       ┌────────┐ ┌──────┐ ┌──────┐
       │Windows │ │Linux │ │  Mac  │
       │  JVM   │ │ JVM  │ │  JVM  │
       └────────┘ └──────┘ └──────┘
```

**How Platform Independence Works:**

```java
// Step 1: Compilation
// Source Code (.java) → javac → Bytecode (.class)

// Step 2: Interpretation  
// Bytecode → JVM (on any OS) → Machine Code

// JVM har operating system ke liye alag hota hai
// Lekin bytecode same rehta hai
// Isiliye Java "Platform Independent" hai
```

---

### Q24. What are Java Tokens? Explain all types.

**Answer:**

**Tokens = Program ke smallest building blocks**

**5 Types of Tokens:**

**1. Literals (Fixed Values):**
```java
// Integer literals
100, -50, 0, 0xFF  // decimal, negative, zero, hexadecimal

// Floating point literals
3.14, -2.5, 10e5  // decimal, negative, scientific notation

// Character literals
'A', 'z', '\n'  // single character in single quotes

// String literals
"Hello", "Java"  // sequence in double quotes

// Boolean literals
true, false
```

**2. Identifiers (User-defined Names):**
```java
// Rules:
✅ Valid: name, _total, $price, variable2, MyClass
❌ Invalid: 2name, my-name, class, if, while
```

**3. Keywords (Reserved Words):**
```java
// Java has 50 reserved keywords
// Cannot use as identifiers
```

**4. Operators (Symbols):**
```java
// Arithmetic operators: + - * / %
// Relational operators: > < >= <= == !=
// Logical operators: && || !
// Assignment operators: = += -= *= /= %=
// Increment/Decrement: ++ --
// Bitwise operators: & | ^ << >>
// Ternary operator: ? :
```

**5. Separators (Punctuations):**
```java
()  // Method parameters, conditions
{}  // Class body, method body, blocks
[]  // Arrays
;   // Statement end
,   // Multiple declarations
.   // Package hierarchy, method call
```

---

### Q25. Explain different types of loops in Java.

**Answer:**

**1. for Loop (Entry Control):**
```java
// Syntax: for(initialization; condition; increment)
// Condition false hone tak repeat hota hai

for (int i = 1; i <= 5; i++) {
    System.out.println("Hello " + i);
}
// Output: Hello 1, Hello 2, Hello 3, Hello 4, Hello 5

// Enhanced for loop (for-each)
int[] nums = {10, 20, 30, 40, 50};
for (int num : nums) {
    System.out.println(num);
}
```

**2. while Loop (Entry Control):**
```java
// Syntax: while(condition) { statements; }
// Condition pehle check hota hai

int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
// Output: 1, 2, 3, 4, 5
```

**3. do-while Loop (Exit Control):**
```java
// Syntax: do { statements; } while(condition);
// Kam se kam ek baar toh chalega hi!

int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
// Output: 1, 2, 3, 4, 5
```

**Comparison:**

| Feature | for | while | do-while |
|---------|-----|-------|----------|
| Condition Check | Pehle | Pehle | Baad mein |
| Min Executions | 0 | 0 | 1 |
| Best For | Known iterations | Unknown iterations | Menu-driven |

---

## 🎯 Section C: Predict the Output

### Q26. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int a = 10;
        int b = 5;
        System.out.println(a++ + ++b);
    }
}
```

**Answer: 16**

**Step by Step:**
```java
// Initial: a = 10, b = 5

// a++ = 10 (value use karo, phir increment)
// ++b = 6 (pehle increment, phir use karo)

// Calculation: 10 + 6 = 16

// Final: a = 11, b = 6
```

---

### Q27. What is the output?

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
```

**Answer: 1 3**

**Explanation:**
// continue se i=2 skip ho jata hai, 1 aur 3 print hote hain

---

### Q28. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int x = 5;
        switch(x) {
            case 1: System.out.print("One ");
            case 2: System.out.print("Two ");
            case 5: System.out.print("Five ");
            default: System.out.print("Default ");
        }
    }
}
```

**Answer: Five Default**

**Explanation:**
// x=5, toh case 5 match hota hai, baaki sab fall-through hote hain

---

### Q29. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int i = 1;
        while (i <= 3) {
            System.out.print(i + " ");
            i++;
        }
    }
}
```

**Answer: 1 2 3**

---

### Q30. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int a = 5, b = 2;
        System.out.println(a / b);
    }
}
```

**Answer: 2**

**Explanation:**
// Integer division - decimal cut ho jata hai

---

## 🎯 Section D: Coding Questions

### Q31. Write a Java program to check if a number is positive, negative, or zero.

```java
import java.util.Scanner;

class CheckNumber {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        
        if (num > 0) {
            System.out.println("Positive Number");
        } else if (num < 0) {
            System.out.println("Negative Number");
        } else {
            System.out.println("Zero");
        }
    }
}
```

---

### Q32. Write a Java program to print Fibonacci series.

```java
class Fibonacci {
    public static void main(String args[]) {
        int n = 10;
        int first = 0, second = 1;
        
        System.out.print("Fibonacci Series: " + first + " " + second);
        
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

### Q33. Write a Java program to find greatest of 3 numbers.

```java
import java.util.Scanner;

class Greatest {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter 3 numbers: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();
        
        if (a > b && a > c) {
            System.out.println(a + " is greatest");
        } else if (b > c) {
            System.out.println(b + " is greatest");
        } else {
            System.out.println(c + " is greatest");
        }
    }
}
```

---

### Q34. Write a Java program to print patterns.

```java
// Pattern: 
// *
// * *
// * * *
// * * * *
// * * * * *

class Pattern {
    public static void main(String args[]) {
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```

---

### Q35. Write a Java program using switch case for calculator.

```java
import java.util.Scanner;

class Calculator {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter two numbers: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        
        System.out.println("1. Add\n2. Subtract\n3. Multiply\n4. Divide");
        System.out.print("Enter choice: ");
        int choice = sc.nextInt();
        
        switch (choice) {
            case 1: System.out.println("Result: " + (a + b)); break;
            case 2: System.out.println("Result: " + (a - b)); break;
            case 3: System.out.println("Result: " + (a * b)); break;
            case 4: System.out.println("Result: " + (a / b)); break;
            default: System.out.println("Invalid choice");
        }
    }
}
```

---

---

### Q36. Which of these is TRUE about type casting?

```java
int m = 50;
byte n = (byte)m;
```
- A) Data loss may occur ✅
- B) Always safe
- C) Compile error
- D) Runtime error

> **Hinglish:** Narrowing (larger to smaller) mein data loss ho sakta hai. Explicit cast zaruri hai.

---

### Q37. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int a = 10, b = 3;
        System.out.println(a % b);
    }
}
```
- A) 3.33
- B) 3
- C) 1 ✅
- D) 0

> **Hinglish:** % operator remainder deta hai. 10 % 3 = 1 (remainder).

---

### Q38. Command line argument in Java main method is:
- A) String args[]
- B) String[] args
- C) Both A and B ✅
- D) int args[]

> **Hinglish:** main method mein command line arguments String array mein aate hain.

---

### Q39. What is the output?

```java
class Test {
    public static void main(String args[]) {
        System.out.println("Args: " + args.length);
    }
}
```
- A) Args: null
- B) Args: 0 ✅
- C) Compilation Error
- D) Runtime Error

> **Hinglish:** Agar koi argument na diya ho toh args.length = 0 hoga, null nahi.

---

### Q40. What will be the output?

```java
class Test {
    public static void main(String args[]) {
        int a = 5, b = 10;
        System.out.println(++a * b--);
    }
}
```
- A) 50
- B) 55 ✅
- C) 60
- D) 54

> **Hinglish:** ++a = 6 (phir use), b-- = 10 (use phir decrement). 6 * 10 = 60 ❌ WAIT! Actual: b-- use karta hai phir decrement, toh 6 * 10 = 60. Correct answer is 60.
> 
> **Correction:** Answer = 60

---

## 🎯 Section E: Type Casting & Command Line Arguments

### Q41. What is Type Casting? Explain with examples.

**Answer:**

**Type Casting = Converting one data type to another**

**Two Types:**

**1. Widening (Automatic) - Smaller to Larger:**
```java
// Automatic conversion - no data loss
byte b = 75;
int a = b;  // byte to int - automatic
System.out.println(a);  // Output: 75
```

**2. Narrowing (Explicit) - Larger to Smaller:**
```java
// Manual conversion - may cause data loss
int m = 130;
byte n = (byte)m;  // explicit cast required
System.out.println(n);  // Output: -126 (data loss!)
```

**Automatic Type Conversion Chart:**

```
char → byte → short → int → long → float → double
```

```java
// Example
byte b = 50;
int i = b;      // OK - widening
int m = 130;
byte n = (byte)m;  // Needs cast - narrowing
System.out.println(n);  // -126 (overflow)
```

---

### Q42. Explain Command Line Arguments with example.

**Answer:**

**What are Command Line Arguments?**
Arguments passed to the program at runtime via command line.

**Syntax:**
```java
public static void main(String args[])
```

**Example 1: Simple Addition**
```java
class Add {
    public static void main(String args[]) {
        int a = Integer.parseInt(args[0]);
        int b = Integer.parseInt(args[1]);
        System.out.println("Sum: " + (a + b));
    }
}
```
**Run as:** `java Add 10 20`
**Output:** `Sum: 30`

**Example 2: Display All Arguments**
```java
class DisplayArgs {
    public static void main(String args[]) {
        System.out.println("Number of args: " + args.length);
        for (int i = 0; i < args.length; i++) {
            System.out.println("args[" + i + "]: " + args[i]);
        }
    }
}
```
**Run as:** `java DisplayArgs Hello Java OOP`
**Output:**
```
Number of args: 3
args[0]: Hello
args[1]: Java
args[2]: OOP
```

---

### Q43. Explain Operator Precedence in Java.

**Answer:**

**Operator Precedence (Highest to Lowest):**

| Priority | Operators | Associativity |
|----------|-----------|---------------|
| 1 | () [] . | Left to Right |
| 2 | ++ -- ! ~ | Right to Left |
| 3 | * / % | Left to Right |
| 4 | + - | Left to Right |
| 5 | << >> >>> | Left to Right |
| 6 | < <= > >= | Left to Right |
| 7 | == != | Left to Right |
| 8 | & | Left to Right |
| 9 | ^ | Left to Right |
| 10 | \| | Left to Right |
| 11 | && | Left to Right |
| 12 | \|\| | Left to Right |
| 13 | ? : | Right to Left |
| 14 | = += -= *= /= %= | Right to Left |

**Example:**
```java
int result = 10 + 5 * 2;  // NOT 30
// * has higher precedence than +
// So: 10 + (5 * 2) = 10 + 10 = 20

int result2 = (10 + 5) * 2;  // 30
// Parentheses override precedence
```

---

## 🎯 Section F: Coding Practice - Command Line & Casting

### Q44. Write a program to add two numbers using command line arguments.

```java
class AddNumbers {
    public static void main(String args[]) {
        int a = Integer.parseInt(args[0]);
        int b = Integer.parseInt(args[1]);
        int sum = a + b;
        System.out.println("Sum: " + sum);
    }
}
```

**Run:** `javac AddNumbers.java`
**Run:** `java AddNumbers 15 25`
**Output:** `Sum: 40`

---

### Q45. Write a program demonstrating type casting.

```java
class TypeCastingDemo {
    public static void main(String args[]) {
        // Widening - automatic
        byte b = 100;
        int i = b;
        System.out.println("Widening: " + i);
        
        // Narrowing - explicit
        int m = 257;
        byte n = (byte) m;
        System.out.println("Narrowing: " + n);
        System.out.println("(257 % 256 = 1, so byte wraps around)");
    }
}
```

**Output:**
```
Widening: 100
Narrowing: 1
```

---

## 📋 Quick Reference Table - Day 1

| Topic | Key Points |
|-------|-----------|
| **OOP Concepts** | Object, Class, Abstraction, Encapsulation, Inheritance, Polymorphism |
| **Java Origin** | Oak by James Gosling, Sun Microsystems, 1991 |
| **Platform Independent** | Bytecode + JVM |
| **Data Types** | byte(1), short(2), int(4), long(8), float(4), double(8), char(2), boolean(1) |
| **Loops** | for, while, do-while |
| **break vs continue** | break = exit, continue = skip iteration |
| **Type Casting** | Widening (auto), Narrowing (explicit) |
| **Command Line** | String args[], accessed via args[0], args[1], etc. |

---

## ✅ Day 1 Self-Check

Before moving to Day 2, make sure you can answer:

- [ ] What is OOP and its 6 concepts?
- [ ] Why is Java platform independent?
- [ ] What is the difference between primitive and non-primitive types?
- [ ] How do you write if-else and switch statements?
- [ ] What is the difference between while and do-while loops?
- [ ] How do break and continue work?

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

➡️ **[Day 2: Classes, Objects & Inheritance](../Day-2/)**

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day1.Questions)
