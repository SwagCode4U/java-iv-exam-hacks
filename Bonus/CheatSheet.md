# 📚 Java OOP Complete Cheat Sheet

![CheatSheet](https://img.shields.io/badge/Java%20OOP-Cheat%20Sheet-green?style=for-the-badge&logo=java)
![CodersJaunt](https://img.shields.io/badge/CodersJaunt-Quick%20Reference-blue?style=for-the-badge)

> *All important concepts in one place for quick revision!*

---

## 📑 Table of Contents

1. [Data Types](#-data-types)
2. [Operators](#-operators)
3. [Control Statements](#-control-statements)
4. [Loops](#-loops)
5. [OOP Concepts](#-oop-concepts)
6. [Inheritance](#-inheritance)
7. [Access Modifiers](#-access-modifiers)
8. [Constructors](#-constructors)
9. [Abstract Class vs Interface](#-abstract-class-vs-interface)
10. [Exception Handling](#-exception-handling)
11. [Keywords Summary](#-keywords-summary)
12. [Common Methods](#-common-methods)

---

## 🔢 Data Types

### Primitive Data Types

| Type | Size | Range | Default |
|------|------|-------|---------|
| `byte` | 1 B | -128 to 127 | 0 |
| `short` | 2 B | -32,768 to 32,767 | 0 |
| `int` | 4 B | -2 billion to 2 billion | 0 |
| `long` | 8 B | Very large | 0L |
| `float` | 4 B | Decimal | 0.0f |
| `double` | 8 B | Large decimal | 0.0d |
| `char` | 2 B | Unicode | '\u0000' |
| `boolean` | 1 B | true/false | false |

### Data Type Conversion

```
char → byte → short → int → long → float → double
       (Automatic/Widening)
       
reverse direction = Explicit Casting required
```

---

## 🔣 Operators

### Operator Precedence

| Priority | Operators |
|----------|-----------|
| 1 | `()` `[]` `.` |
| 2 | `++` `--` `!` `~` |
| 3 | `*` `/` `%` |
| 4 | `+` `-` |
| 5 | `<<` `>>` `>>>` |
| 6 | `<` `<=` `>` `>=` |
| 7 | `==` `!=` |
| 8 | `&` |
| 9 | `^` |
| 10 | `|` |
| 11 | `&&` |
| 12 | `||` |
| 13 | `?:` |
| 14 | `=` `+=` `-=` etc. |

### Types of Operators

```java
// Arithmetic: + - * / %
// Relational: < > <= >= == !=
// Logical: && || !
// Assignment: = += -= *= /= %=
// Increment/Decrement: ++ --
// Bitwise: & | ^ << >> >>>
// Ternary: condition ? val1 : val2
```

---

## 🔀 Control Statements

### if-else
```java
if (condition) {
    // statements
} else if (condition) {
    // statements
} else {
    // statements
}
```

### switch
```java
switch(expression) {
    case value1:
        // statements
        break;
    case value2:
        // statements
        break;
    default:
        // statements
}
```

---

## 🔁 Loops

| Loop | Type | Min Executions |
|------|------|----------------|
| `for` | Entry Control | 0 |
| `while` | Entry Control | 0 |
| `do-while` | Exit Control | 1 |

```java
// for loop
for (int i = 0; i < n; i++) { }

// while loop
while (condition) { }

// do-while
do {
} while (condition);

// enhanced for (for-each)
for (type var : array) { }
```

### Jump Statements

| Statement | Purpose |
|-----------|---------|
| `break` | Exit loop |
| `continue` | Skip iteration |
| `return` | Exit method |

---

## 🏗️ OOP Concepts

### The 6 Pillars of OOP

```
1. Object & Class      → Blueprint & Instance
2. Encapsulation       → Data + Methods in one unit
3. Abstraction         → Hide complexity
4. Inheritance         → Parent → Child
5. Polymorphism        → One name, many forms
6. Dynamic Binding     → Runtime method resolution
```

### Class Structure
```java
[access] class ClassName [extends Parent] [implements Interfaces] {
    // Fields (variables)
    // Constructors
    // Methods
}
```

### Object Creation
```java
ClassName obj = new ClassName();
```

---

## 🔗 Inheritance

### Types of Inheritance

| Type | Diagram | Supported |
|------|---------|-----------|
| Single | A → B | ✅ |
| Multilevel | A → B → C | ✅ |
| Hierarchical | A ↘ ↙ B C | ✅ |
| Multiple | A B → C | ❌ (use Interface) |

### Keywords for Inheritance

```java
class Parent { }
class Child extends Parent { }  // extends for inheritance
class Child implements Interface { }  // implements for interface
```

---

## 🔐 Access Modifiers

| Modifier | Same Class | Same Package | Subclass (Diff) | Other (Diff) |
|----------|------------|--------------|-----------------|--------------|
| `public` | ✅ | ✅ | ✅ | ✅ |
| `protected` | ✅ | ✅ | ✅ | ❌ |
| `default` | ✅ | ✅ | ❌ | ❌ |
| `private` | ✅ | ❌ | ❌ | ❌ |

**Most Open → Most Restricted:**
```
public > protected > default > private
```

---

## 🏗️ Constructors

### Types

```java
class Demo {
    int x;
    
    Demo() { }  // Default (no-arg)
    
    Demo(int a) {  // Parameterized
        x = a;
    }
    
    Demo(Demo d) {  // Copy
        x = d.x;
    }
}
```

### Constructor Rules
1. Same name as class
2. No return type
3. Called automatically on object creation

---

## 🧩 Abstract Class vs Interface

| Feature | Abstract Class | Interface |
|---------|---------------|-----------|
| **Methods** | Abstract + Concrete | Abstract only (Java 7) |
| **Variables** | Any type | public static final only |
| **Constructor** | ✅ Yes | ❌ No |
| **Multiple Inheritance** | ❌ No | ✅ Yes |
| **Keyword** | extends | implements |
| **Abstraction** | 0-100% | 100% |

### Abstract Class
```java
abstract class Shape {
    abstract void draw();  // Abstract
    void color() { }      // Concrete
}
```

### Interface
```java
interface Drawable {
    void draw();  // Always abstract
    int MAX = 100;  // Always public static final
}
```

---

## ⚠️ Exception Handling

### Exception Hierarchy
```
Throwable
├── Error (irrecoverable)
└── Exception (recoverable)
    ├── Checked (IOException, SQLException)
    └── Unchecked (RuntimeException)
```

### Keywords

```java
try {
    // Code that may throw exception
} catch (ExceptionType e) {
    // Handle exception
} finally {
    // Always executes
}

throw new ExceptionType("message");  // Manual throw
void method() throws Exception { }    // Declare exception
```

### Common Exceptions

| Exception | When Occurs |
|-----------|-------------|
| ArithmeticException | Division by zero |
| NullPointerException | null object access |
| ArrayIndexOutOfBoundsException | Invalid array index |
| NumberFormatException | Invalid number format |

---

## 📝 Keywords Summary

### Access Modifiers
```java
public, protected, private, (default)
```

### Class-related
```java
class, extends, implements, new, this, super
```

### Object-related
```java
new, instanceof
```

### Method-related
```java
void, static, final, abstract, return
```

### Control
```java
if, else, switch, case, default, for, while, do, break, continue
```

### Exception
```java
try, catch, finally, throw, throws
```

### Others
```java
import, package, true, false, null
```

---

## 📞 Common Methods

### String Methods
```java
s.length()           // Length
s.charAt(index)      // Character at index
s.substring(start)   // Substring
s.equals(s2)         // Compare strings
s.toLowerCase()      // Convert to lowercase
s.toUpperCase()      // Convert to uppercase
s.trim()             // Remove spaces
```

### Scanner Methods
```java
sc.nextInt()         // Read int
sc.nextFloat()       // Read float
sc.nextLine()        // Read line
sc.next()            // Read word
```

### Array Methods
```java
arr.length           // Array length
Arrays.sort(arr)     // Sort array
Arrays.toString(arr) // Convert to string
```

### Character Methods
```java
Character.isDigit(c)     // Is digit?
Character.isLetter(c)    // Is letter?
Character.isUpperCase(c) // Is uppercase?
Character.toLowerCase(c) // To lowercase
```

---

## ⏱️ Quick Reference: Time Complexity

| Operation | Array | ArrayList | LinkedList |
|-----------|-------|-----------|------------|
| Access | O(1) | O(1) | O(n) |
| Insert | O(n) | O(n) | O(1) |
| Delete | O(n) | O(n) | O(1) |
| Search | O(n) | O(n) | O(n) |

---

## 📌 Must Remember Points

1. **Java has NO pointers** - Security feature
2. **Java is platform independent** - Uses bytecode + JVM
3. **Object class** is parent of all classes
4. **main() method** is the entry point
5. **String args[]** - Command line arguments
6. **Package** - Group of related classes
7. **Interface** - 100% abstraction
8. **abstract** - Cannot be instantiated
9. **static** - Class level, shared
10. **final** - Cannot change/override/extend

---

## 🎯 Common Patterns

### Fibonacci Series
```java
int n = 10, a = 0, b = 1;
for (int i = 0; i < n; i++) {
    System.out.print(a + " ");
    int c = a + b;
    a = b;
    b = c;
}
```

### Factorial
```java
int fact = 1;
for (int i = 1; i <= n; i++) {
    fact *= i;
}
```

### Palindrome Check
```java
String s = "radar";
String rev = new StringBuilder(s).reverse().toString();
boolean isPalindrome = s.equals(rev);
```

### Prime Check
```java
boolean isPrime = true;
for (int i = 2; i <= n/2; i++) {
    if (n % i == 0) {
        isPrime = false;
        break;
    }
}
```

### Swapping Two Numbers
```java
// Without temp
a = a + b;
b = a - b;
a = a - b;

// With temp
int temp = a;
a = b;
b = temp;
```

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.CheatSheet)
