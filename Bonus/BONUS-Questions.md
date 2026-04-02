# 🎁 Bonus Questions - Additional Practice

![Bonus](https://img.shields.io/badge/Java-Bonus%20Questions-orange?style=for-the-badge&logo=java)
![CodersJaunt](https://img.shields.io/badge/CodersJaunt-Extra%20Practice-blue?style=for-the-badge)

> *Extra questions covering all topics for comprehensive preparation!*

---

## 📚 Section 1: Java Basics & OOP Concepts

### Q1. What is the full form of JDK?
- A) Java Development Kit ✅
- B) Java Design Kit
- C) Java Data Kit
- D) Java Documentation Kit

> **Hinglish:** JDK = **Java Development Kit** - Yehi sab tools contain karta hai Java develop karne ke liye.

---

### Q2. Which is NOT a Java feature?
- A) Platform Independent
- B) Object-Oriented
- C) Uses Pointers ✅
- D) Robust and Secure

> **Hinglish:** Java mein **pointers use nahi hote** - yeh iski security feature hai!

---

### Q3. What is bytecode in Java?
- A) Machine code
- B) Source code
- C) Intermediate code that runs on JVM ✅
- D) Assembly code

> **Hinglish:** Bytecode ek intermediate code hai jo JVM pe run hota hai - isiliye Java platform independent hai.

---

### Q4. Who is known as the father of Java programming?
- A) Dennis Ritchie
- B) James Gosling ✅
- C) Bjarne Stroustrup
- D) Guido van Rossum

> **Hinglish:** **James Gosling** ne Java create kiya tha 1991 mein Sun Microsystems mein.

---

### Q5. What is the default value of an uninitialized local variable in Java?
- A) null
- B) 0
- C) No default value (compile error) ✅
- D) false

> **Hinglish:** Local variables ko initialize karna zaroori hai, warna **compile error** aayega!

---

### Q6. What will be the output?

```java
class Test {
    public static void main(String args[]) {
        System.out.println("Hello" + 10 + 20);
    }
}
```
- A) Hello30
- B) Hello1020 ✅
- C) Hello30.0
- D) Compilation Error

> **Hinglish:** String ke baad sab String mein convert ho jata hai. "Hello" + "10" + "20" = "Hello1020"

---

### Q7. What will be the output?

```java
class Test {
    public static void main(String args[]) {
        System.out.println(10 + 20 + "Hello");
    }
}
```
- A) 30Hello ✅
- B) Hello30
- C) 1020Hello
- D) Compilation Error

> **Hinglish:** Pehle numbers add hote hain, phir String join hota hai. 10 + 20 = 30, 30 + "Hello" = "30Hello"

---

### Q8. Which of these is a valid identifier?
- A) 2variable
- B) my-variable
- C) $price ✅
- D) class

> **Hinglish:** $price valid hai kyunki $ allowed hai identifier mein. Lekin class keyword hai.

---

### Q9. What is the size of char in Java?
- A) 1 byte
- B) 2 bytes ✅
- C) 4 bytes
- D) Depends on OS

> **Hinglish:** Java mein char **2 bytes** ka hota hai kyunki yeh Unicode support karta hai.

---

### Q10. Which keyword is used to inherit a class?
- A) inherit
- B) extends ✅
- C) implements
- D) derive

> **Hinglish:** **extends** keyword se inheritance hoti hai.

---

## 📚 Section 2: Classes, Objects & Inheritance

### Q11. What is the output?

```java
class Parent {
    static {
        System.out.print("Parent ");
    }
}
class Child extends Parent {
    static {
        System.out.print("Child ");
    }
}
class Test {
    public static void main(String args[]) {
        Child c = new Child();
    }
}
```
- A) Child Parent
- B) Parent Child ✅
- C) Parent
- D) Child

> **Hinglish:** Static blocks parent class ke pehle execute hote hain.

---

### Q12. Can a class extend multiple classes in Java?
- A) Yes
- B) No ✅
- C) Only with interfaces
- D) Only in Java 8+

> **Hinglish:** Java mein class multiple classes extend nahi kar sakti. Sirf interfaces se multiple inheritance possible hai.

---

### Q13. What is the output?

```java
class A {
    int i = 10;
}
class B extends A {
    int i = 20;
}
class Test {
    public static void main(String args[]) {
        A a = new B();
        System.out.println(a.i);
    }
}
```
- A) 10 ✅
- B) 20
- C) 10 20
- D) Compilation Error

> **Hinglish:** Reference type decide karta hai kaunsa variable access hoga. a.i = 10 (Parent ka)

---

### Q14. Which of these cannot be inherited?
- A) Private methods
- B) Private constructors
- C) Both A and B ✅
- D) Protected methods

> **Hinglish:** Private members (methods aur constructors) inherit nahi hote.

---

### Q15. What is the output?

```java
class Test {
    static int x = 5;
    static { x = 10; }
    public static void main(String args[]) {
        System.out.println(x);
    }
}
```
- A) 5
- B) 10 ✅
- C) 0
- D) Compilation Error

> **Hinglish:** Static block variable ko change kar deta hai. x = 10

---

## 📚 Section 3: Abstract Class & Interface

### Q16. Which is TRUE about interfaces?
- A) Can have constructors
- B) Can have instance variables
- C) Variables are public static final by default ✅
- D) Methods must have body

> **Hinglish:** Interface variables **public static final** hote hain automatically.

---

### Q17. Can an interface extend another interface?
- A) No
- B) Yes ✅
- C) Only one level
- D) Not defined

> **Hinglish:** Haan, interface doosre interface ko **extend** kar sakta hai.

---

### Q18. What is the output?

```java
interface A {
    int x = 10;
}
interface B extends A {
    int y = 20;
}
class Test {
    public static void main(String args[]) {
        System.out.println(B.x + B.y);
    }
}
```
- A) 30 ✅
- B) 10
- C) 20
- D) Compilation Error

> **Hinglish:** B, A ko extend karta hai, toh B.x accessible hai. 10 + 20 = 30

---

### Q19. Which is NOT a feature of abstract class?
- A) Can have abstract methods
- B) Can have constructors
- C) Can be instantiated directly ✅
- D) Can have non-abstract methods

> **Hinglish:** Abstract class ko **directly instantiate nahi kar sakte**.

---

### Q20. How to achieve 100% abstraction?
- A) Abstract class
- B) Interface ✅
- C) Both
- D) None

> **Hinglish:** Interface 100% abstraction deta hai.

---

## 📚 Section 4: Exception Handling

### Q21. Which is the root class of exception hierarchy?
- A) Exception
- B) Error
- C) Throwable ✅
- D) RuntimeException

> **Hinglish:** **Throwable** parent hai Exception aur Error dono ka.

---

### Q22. What is the output?

```java
class Test {
    public static void main(String args[]) {
        try {
            System.out.print("A ");
            int x = 10/0;
        } catch(Exception e) {
            System.out.print("B ");
        } catch(ArithmeticException e) {
            System.out.print("C ");
        }
    }
}
```
- A) A B
- B) A C
- C) Compilation Error ✅
- D) A B C

> **Hinglish:** ArithmeticException, Exception ka child hai. Child ko baad mein catch nahi kar sakte.

---

### Q23. Which is a checked exception?
- A) NullPointerException
- B) ArithmeticException
- C) IOException ✅
- D) ArrayIndexOutOfBoundsException

> **Hinglish:** Checked exceptions compile-time pe check hote hain.

---

### Q24. What happens if finally block has return statement?

```java
try {
    return 1;
} finally {
    return 2;
}
```
- A) Returns 1
- B) Returns 2 ✅
- C) Compilation Error
- D) Runtime Error

> **Hinglish:** finally ki return statement priority leti hai.

---

### Q25. Can we have try without catch?
- A) No
- B) Yes, if finally is present ✅
- C) Only in Java 7
- D) Only in Java 8

> **Hinglish:** try-finally allowed hai, catch optional hai.

---

## 📚 Section 5: Coding Practice Questions

### Q26. Write a program to check if a number is prime.

```java
class PrimeCheck {
    static boolean isPrime(int n) {
        if (n <= 1) return false;
        if (n == 2) return true;
        if (n % 2 == 0) return false;
        
        for (int i = 3; i <= Math.sqrt(n); i += 2) {
            if (n % i == 0) return false;
        }
        return true;
    }
    
    public static void main(String args[]) {
        int num = 17;
        if (isPrime(num))
            System.out.println(num + " is Prime");
        else
            System.out.println(num + " is Not Prime");
    }
}
```

---

### Q27. Write a program to reverse a string.

```java
class StringReverse {
    public static void main(String args[]) {
        String s = "Java";
        
        // Method 1: Using StringBuilder
        String rev = new StringBuilder(s).reverse().toString();
        System.out.println("Reversed: " + rev);
        
        // Method 2: Manual
        String rev2 = "";
        for (int i = s.length() - 1; i >= 0; i--) {
            rev2 += s.charAt(i);
        }
        System.out.println("Reversed: " + rev2);
    }
}
```

---

### Q28. Write a program to demonstrate method overloading and overriding together.

```java
class Parent {
    void show(int x) {
        System.out.println("Parent show(int): " + x);
    }
    
    void display() {
        System.out.println("Parent display");
    }
}

class Child extends Parent {
    @Override
    void display() {
        System.out.println("Child display");
    }
    
    // Overloading - same class
    void show(int x, int y) {
        System.out.println("Child show(int, int): " + (x + y));
    }
}

class Test {
    public static void main(String args[]) {
        Child c = new Child();
        c.show(10);       // Overloading
        c.show(10, 20);  // Overloading
        c.display();      // Overriding
    }
}
```

---

### Q29. Write a program to demonstrate custom exception.

```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String msg) {
        super(msg);
    }
}

class Voter {
    static void checkAge(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Age must be 18 or above!");
        }
        System.out.println("Eligible to vote");
    }
    
    public static void main(String args[]) {
        try {
            checkAge(16);
        } catch (InvalidAgeException e) {
            System.out.println("Exception: " + e.getMessage());
        }
    }
}
```

---

### Q30. Write a program using interface and abstract class.

```java
abstract class Shape {
    protected String color;
    
    Shape(String c) {
        color = c;
    }
    
    abstract double area();
}

interface Printable {
    void print();
}

class Circle extends Shape implements Printable {
    double radius;
    
    Circle(String c, double r) {
        super(c);
        radius = r;
    }
    
    double area() {
        return Math.PI * radius * radius;
    }
    
    public void print() {
        System.out.println("Circle: " + color + ", Area: " + area());
    }
}

class Test {
    public static void main(String args[]) {
        Circle c = new Circle("Red", 5);
        c.print();
    }
}
```

---

## 📚 Section 6: Advanced MCQs

### Q31. What is the output?

```java
class Test {
    public static void main(String args[]) {
        String s1 = "Java";
        String s2 = "Java";
        String s3 = new String("Java");
        
        System.out.println(s1 == s2);
        System.out.println(s1 == s3);
        System.out.println(s1.equals(s3));
    }
}
```
- A) true false true ✅
- B) true true true
- C) false false false
- D) true true false

> **Hinglish:** == reference compare karta hai, equals() content compare karta hai.

---

### Q32. Which of these is not a wrapper class?
- A) Integer
- B) Boolean
- C) String ✅
- D) Character

> **Hinglish:** String ek class hai, wrapper class nahi.

---

### Q33. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int a = 10, b = 5;
        int c = (a > b) ? a : b;
        System.out.println(c);
    }
}
```
- A) 5
- B) 10 ✅
- C) 15
- D) Compilation Error

> **Hinglish:** Ternary operator: agar condition true hai toh a, false hai toh b.

---

### Q34. Which collection class allows duplicate elements?
- A) Set
- B) HashSet
- C) List ✅
- D) Map

> **Hinglish:** List duplicate allow karta hai, Set nahi.

---

### Q35. What is the default capacity of ArrayList?
- A) 5
- B) 10 ✅
- C) 15
- D) 0

> **Hinglish:** ArrayList ka default capacity **10** hai.

---

### Q36. Which keyword is used to prevent method overriding?
- A) static
- B) final ✅
- C) private
- D) abstract

> **Hinglish:** **final** keyword method ko override hone se bachata hai.

---

### Q37. What is the output?

```java
class Test {
    static int x = 5;
    int y = 10;
    
    static void staticMethod() {
        // System.out.println(y);  // ERROR!
        System.out.println(x);
    }
    
    public static void main(String args[]) {
        staticMethod();
    }
}
```
- A) 5
- B) 10
- C) Compilation Error ✅
- D) 5 10

> **Hinglish:** Static method se instance variable access nahi kar sakte.

---

### Q38. Which of these is automatically called when object is created?
- A) main()
- B) constructor ✅
- C) finalize()
- D) start()

> **Hinglish:** Constructor object create hote waqt automatically call hota hai.

---

### Q39. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int arr[][] = {{1, 2}, {3, 4}};
        for (int i[] : arr) {
            for (int j : i) {
                System.out.print(j + " ");
            }
        }
    }
}
```
- A) 1 2 3 4 ✅
- B) 1 2
- C) 3 4
- D) Compilation Error

> **Hinglish:** Enhanced for loop se 2D array traverse karte hain.

---

### Q40. What is the output?

```java
class Base {
    void method() {
        System.out.println("Base");
    }
}

class Derived extends Base {
    void method() {
        System.out.println("Derived");
    }
}

class Test {
    public static void main(String args[]) {
        Base b = new Derived();
        b.method();
    }
}
```
- A) Base
- B) Derived ✅
- C) Base Derived
- D) Compilation Error

> **Hinglish:** Runtime polymorphism - child ka method call hoga.

---

## 📚 Section 7: Real-Life Scenario Questions

### Q41. Which design pattern is demonstrated by this code?

```java
// Single object throughout application
class Singleton {
    private static Singleton instance;
    
    private Singleton() { }
    
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```
- A) Factory
- B) Singleton ✅
- C) Observer
- D) Adapter

---

### Q42. A bank application needs to support multiple payment methods. Which is best suited?

```java
interface Payment {
    void pay(double amount);
}

class CreditCard implements Payment {
    public void pay(double amount) {
        System.out.println("Credit Card: " + amount);
    }
}

class UPI implements Payment {
    public void pay(double amount) {
        System.out.println("UPI: " + amount);
    }
}
```
- A) Abstract Class
- B) Interface ✅
- C) Inheritance
- D) Encapsulation

---

### Q43. Why do we use packages in Java?
- A) To organize classes
- B) To avoid naming conflicts
- C) To control access
- D) All of the above ✅

---

### Q44. Which is an example of aggregation?

```java
class Address {
    String city, state;
}

class Employee {
    String name;
    Address address;  // Employee HAS-A Address
}
```
- A) Composition
- B) Aggregation ✅
- C) Inheritance
- D) None

---

### Q45. What is tighter coupling?

```java
class Engine {
    void start() { }
}

class Car {
    Engine engine = new Engine();  // Tight coupling
}
```
- A) Car has Engine object directly ✅
- B) Car uses interface
- C) Car uses inheritance
- D) None

---

## 📚 Section 8: Tricky Questions

### Q46. What is the output?

```java
class Test {
    public static void main(String args[]) {
        System.out.println(10 * 20 + "Java");
        System.out.println("Java" + 10 * 20);
    }
}
```
- A) 200Java Java200
- B) 200Java Java200 ✅
- C) 200Java 200Java
- D) 300Java Java300

---

### Q47. What is the output?

```java
class Test {
    static { int x = 10; }
    static { int x = 20; }  // What happens?
    
    public static void main(String args[]) {
        System.out.println(x);
    }
}
```
- A) 10
- B) 20
- C) Compilation Error ✅
- D) 30

---

### Q48. Which of these cannot be overloaded?

```java
class Demo {
    void method() { }
    // Which cannot be added?
}
```
- A) void method(int a)
- B) int method()
- C) static void method() ✅
- D) void method(String s)

> **Hinglish:** Static method ko overload kar sakte ho, lekin static context se instance access nahi kar sakte.

---

### Q49. What is the output?

```java
class Parent {
    static void show() {
        System.out.println("Parent");
    }
}

class Child extends Parent {
    static void show() {
        System.out.println("Child");
    }
}

class Test {
    public static void main(String args[]) {
        Parent p = new Child();
        p.show();
    }
}
```
- A) Parent ✅
- B) Child
- C) Both
- D) Compilation Error

> **Hinglish:** Static methods override nahi hote, yeh method hiding hai.

---

### Q50. What is the output?

```java
class Test {
    public static void main(String args[]) {
        String s = null;
        System.out.println(s);
        System.out.println(s.length());
    }
}
```
- A) null NullPointerException ✅
- B) null null
- C) Compilation Error
- D) null

---

## 📚 Section 9: Packages & Import Statements

### Q51. What is a package in Java?
- A) Collection of classes and interfaces ✅
- B) Collection of methods
- C) Collection of variables
- D) Type of class

> **Hinglish:** Package ek folder jaisa hai jo related classes aur interfaces ko ek saath rakhta hai. Jaise `java.util`, `java.io`, etc.

---

### Q52. Which statement is used to create a package?
- A) package ✅
- B) import
- C) include
- D) require

> **Hinglish:** Package create karne ke liye `package` keyword use karte hain. Yeh class file ke sabse upar likha jata hai.

---

### Q53. What is the correct way to import all classes from a package?
- A) import java.util.*;
- B) import java.util
- C) include java.util.*
- D) use java.util.*

> **Hinglish:** `import java.util.*;` se util package ki saari classes import ho jati hain.

---

### Q54. Which package is automatically imported in every Java program?
- A) java.io
- B) java.net
- C) java.lang ✅
- D) java.applet

> **Hinglish:** `java.lang` package automatically import hota hai har Java program mein. Isme String, System, Math, etc. hain.

---

### Q55. What will be the output?

```java
package college;
class Student {
    void display() {
        System.out.println("Student class");
    }
}
```
- A) Student class
- B) Compilation Error
- C) No output
- D) college.Student

> **Hinglish:** Agar package declare kiya hai toh file ka naam `Student.java` hona chahiye, warna compilation error aayega.

---

### Q56. How do you access a class from a different package?
- A) Using import statement ✅
- B) Using include statement
- C) Using package statement
- D) Cannot access

> **Hinglish:** Doosre package ki class access karne ke liye `import packageName.ClassName;` use karte hain.

---

### Q57. Which is NOT a standard Java package?
- A) java.util
- B) java.io
- C) java.common ✅
- D) java.awt

> **Hinglish:** `java.common` koi standard package nahi hai. Standard packages hain: java.util, java.io, java.awt, java.lang, etc.

---

### Q58. What is the purpose of access protected member from different package?
```java
// In pack1/Parent.java
package pack1;
public class Parent {
    protected int x = 10;
}

// In pack2/Child.java
package pack2;
import pack1.Parent;
class Child extends Parent {
    void show() {
        System.out.println(x);  // Works?
    }
}
```
- A) Works ✅
- B) Does not work
- C) Compilation Error
- D) Runtime Error

> **Hinglish:** Protected members subclass mein inheritance ke through access ho sakte hain, chahe different package kyun na ho.

---

### Q59. What is fully qualified class name?
- A) Short name of class
- B) Complete name with package ✅
- C) Name with .class extension
- D) Name without package

> **Hinglish:** Fully qualified name mein package bhi shamil hota hai. Jaise `java.util.ArrayList` ArrayList ka fully qualified name hai.

---

### Q60. Can we import same class from two different packages?
- A) Yes
- B) No ✅
- C) Only in Java 8+
- D) Only with static import

> **Hinglish:** Agar do packages mein same class naam hai toh import se conflict hoga. Tab fully qualified name use karna padta hai.

---

## 📚 Section 10: String Handling

### Q61. Which of these is NOT a way to create a String?
- A) String s = "Hello";
- B) String s = new String("Hello");
- C) String s = char[] {'H','e','l','l','o'}; ✅
- D) String s = new String(charArray);

> **Hinglish:** Direct char array se String nahi bana sakte. Ya toh String constructor use karo ya new String() mein convert karo.

---

### Q62. What is the output?

```java
class Test {
    public static void main(String args[]) {
        String s1 = "Java";
        String s2 = "Java";
        String s3 = new String("Java");
        
        System.out.println(s1 == s2);
        System.out.println(s1 == s3);
        System.out.println(s1.equals(s3));
    }
}
```
- A) true false true ✅
- B) true true true
- C) false false true
- D) true false false

> **Hinglish:** s1 == s2 (same object in string pool) = true. s1 == s3 (different objects) = false. equals() content compare karta hai = true.

---

### Q63. Which method is used to compare two strings?
- A) compare()
- B) compareTo() ✅
- C) equals()
- D) Both B and C

> **Hinglish:** equals() true/false deta hai. compareTo() 0, positive ya negative integer deta hai (lexicographical comparison).

---

### Q64. What is the output?

```java
class Test {
    public static void main(String args[]) {
        String s = "JavaProgramming";
        System.out.println(s.length());
        System.out.println(s.charAt(4));
        System.out.println(s.substring(4, 8));
    }
}
```
- A) 15, 'P', "Prog"
- B) 15, 'P', "Pro"
- C) 15, 'a', "Pro"
- D) 14, 'P', "Prog"

> **Hinglish:** length() = 15, charAt(4) = 'P' (0-based), substring(4,8) = positions 4,5,6,7 = "Prog".

---

### Q65. What does "Hello".replace('l', 'L') return?
- A) HeLLo ✅
- B) Hello
- C) HELLO
- D) HeLLo

> **Hinglish:** replace() sab 'l' ko 'L' se replace karta hai. Dono 'l' replace hote hain.

---

### Q66. What does "Java".toUpperCase().toLowerCase() return?
- A) JAVA
- B) java ✅
- C) Java
- D) Compilation Error

> **Hinglish:** toUpperCase() se "JAVA" hoga, phir toLowerCase() se "java" hoga.

---

### Q67. Which method splits a string?
- A) split()
- B) tokenize()
- C) divide()
- D) separate()

> **Hinglish:** split() method string ko delimiter ke basis pe parts mein divide karta hai aur String array return karta hai.

---

### Q68. What is the output?

```java
class Test {
    public static void main(String args[]) {
        String s = "Java";
        s.concat(" Programming");
        System.out.println(s);
    }
}
```
- A) Java Programming
- B) Java ✅
- C) Compilation Error
- D) null

> **Hinglish:** Strings immutable hain! concat() naya String return karta hai, original change nahi karta. result store nahi kiya.

---

### Q69. What is the difference between String, StringBuilder, and StringBuffer?
- A) String is mutable, others immutable
- B) String immutable, others mutable ✅
- C) All are same
- D) StringBuffer mutable, others immutable

> **Hinglish:** String immutable hai (change nahi ho sakta). StringBuilder aur StringBuffer mutable hain. StringBuilder faster hai (not synchronized).

---

### Q70. What is the output?

```java
class Test {
    public static void main(String args[]) {
        StringBuffer sb = new StringBuffer("Hello");
        sb.append(" World");
        sb.insert(5, ",");
        System.out.println(sb);
    }
}
```
- A) Hello World,
- B) Hello, World ✅
- C) ,Hello World
- D) HelloWorld,

> **Hinglish:** append() end mein add karta hai. insert(5, ",") position 5 pe comma lagata hai.

---

### Q71. What does String.trim() do?
- A) Removes leading and trailing spaces ✅
- B) Removes all spaces
- C) Converts to uppercase
- D) Removes vowels

> **Hinglish:** trim() string ke starting aur ending ke spaces (whitespace) remove karta hai. Middle spaces unchanged rehte hain.

---

### Q72. What does "Java".indexOf('a') return?
- A) 1
- B) 3
- C) -1
- D) Both A and B ✅

> **Hinglish:** indexOf() first occurrence return karta hai. 'J' = 0, 'a' = 1, 'v' = 2, 'a' = 3. So indexOf('a') = 1 return karega.

---

## 📚 Section 11: Wrapper Classes & Autoboxing

### Q73. Which is NOT a wrapper class?
- A) Integer
- B) String ✅
- C) Boolean
- D) Character

> **Hinglish:** String ek class hai, wrapper class nahi. Wrapper classes hain: Integer, Long, Short, Byte, Float, Double, Character, Boolean.

---

### Q74. What is boxing in Java?
- A) Converting primitive to wrapper ✅
- B) Converting wrapper to primitive
- C) Creating object
- D) Creating array

> **Hinglish:** Boxing primitive type ko wrapper class object mein convert karta hai. Jaise int ko Integer mein.

---

### Q75. What is unboxing?
- A) Converting primitive to wrapper
- B) Converting wrapper to primitive ✅
- C) Creating primitive
- D) None

> **Hinglish:** Unboxing wrapper object ko primitive mein convert karta hai. Jaise Integer ko int mein.

---

### Q76. What is the output?

```java
class Test {
    public static void main(String args[]) {
        Integer a = 10;
        Integer b = 10;
        System.out.println(a == b);
        
        Integer c = 200;
        Integer d = 200;
        System.out.println(c == d);
    }
}
```
- A) true true
- B) true false ✅
- C) false true
- D) false false

> **Hinglish:** Integer cache -128 to 127 tak hoti hai. 10 cache mein hai (true), 200 nahi (false, different objects).

---

### Q77. Which method converts String to int?
- A) Integer.parseInt() ✅
- B) Integer.valueOf()
- C) String.valueOf()
- D) Both A and B

> **Hinglish:** parseInt() primitive int deta hai. valueOf() Integer object deta hai.

---

### Q78. What is autoboxing?
- A) Automatic boxing by compiler ✅
- B) Manual boxing
- C) Creating wrapper manually
- D) None

> **Hinglish:** Autoboxing compiler ka feature hai jo automatically primitive ko wrapper mein convert karta hai. Jaise: `Integer i = 10;` (no need to write `Integer.valueOf(10)`)

---

### Q79. What is the output?

```java
class Test {
    public static void main(String args[]) {
        Double d = 10.5;
        int x = d.intValue();
        System.out.println(x);
    }
}
```
- A) 10.5
- B) 10 ✅
- C) 10.0
- D) Compilation Error

> **Hinglish:** intValue() Double ko int mein convert karta hai (decimal part remove hota hai).

---

### Q80. Which wrapper class is used for char?
- A) Character ✅
- B) Char
- C) String
- D) Boolean

> **Hinglish:** Character wrapper class hai char ke liye. Isme isDigit(), isLetter(), isUpperCase() jaise utility methods hain.

---

## 📚 Section 12: Multithreading

### Q81. How many ways to create a thread in Java?
- A) 1
- B) 2 ✅
- C) 3
- D) 4

> **Hinglish:** Thread do tarike se bana sakte hain: 1) Thread class extend karna, 2) Runnable interface implement karna.

---

### Q82. Which interface is used to create a thread?
- A) Thread
- B) Runnable ✅
- C) Callable
- D) Executor

> **Hinglish:** Runnable interface ko implement karke thread bana sakte hain. Yeh preferred way hai kyunki Java single inheritance deta hai.

---

### Q83. What is the output?

```java
class MyThread extends Thread {
    public void run() {
        System.out.print("Thread ");
    }
}

class Test {
    public static void main(String args[]) {
        MyThread t = new MyThread();
        t.start();
        System.out.print("Main ");
    }
}
```
- A) Thread Main
- B) Main Thread
- C) Either A or B ✅
- D) Thread Thread

> **Hinglish:** Thread scheduling JVM pe depend karta hai. Output unpredictable ho sakta hai.

---

### Q84. Which method is used to pause a thread temporarily?
- A) wait()
- B) sleep() ✅
- C) pause()
- D) stop()

> **Hinglish:** sleep() thread ko specified milliseconds ke liye rookta hai. Wait() synchronized block mein use hota hai.

---

### Q85. What is synchronization in Java?
- A) Making method static
- B) Preventing concurrent access ✅
- C) Making variable final
- D) Creating thread

> **Hinglish:** Synchronization se ek time pe sirf ek thread shared resource access kar sakta hai. Yeh data inconsistency avoid karta hai.

---

### Q86. Which keyword is used for synchronization?
- A) synchronized ✅
- B) static
- C) final
- D) volatile

> **Hinglish:** synchronized keyword method ya block ke liye use hota hai. Yeh lock mechanism provide karta hai.

---

### Q87. What is the output?

```java
class Counter {
    int count = 0;
    synchronized void increment() {
        count++;
    }
}

public class Test {
    public static void main(String args[]) {
        Counter c = new Counter();
        // Two threads incrementing c
        // What is final count?
    }
}
```
- A) 1
- B) 2 ✅
- C) 0
- D) Unpredictable

> **Hinglish:** Synchronized method mein ek time pe sirf ek thread enter kar sakta hai. Dono threads sequentially increment karenge = 2.

---

### Q88. What is the difference between wait() and sleep()?
- A) wait() releases lock, sleep() does not ✅
- B) sleep() releases lock, wait() does not
- C) Both are same
- D) Both release lock

> **Hinglish:** wait() lock release karta hai (synchronized context mein). sleep() lock hold karta rhta hai.

---

### Q89. What does Thread.yield() do?
- A) Pauses current thread ✅
- B) Stops thread permanently
- C) Kills thread
- D) Starts new thread

> **Hinglish:** yield() current thread ko ready state mein wapas jane deta hai taaki same priority ke threads ko chance mile.

---

### Q90. What is daemon thread?
- A) High priority thread
- B) Low priority thread that runs in background ✅
- C) Main thread
- D) Fast thread

> **Hinglish:** Daemon threads background mein run karte hain (Garbage Collector jaisa). Program end hone pe ye automatically stop ho jate hain.

---

## 📚 Section 13: Collections Framework

### Q91. Which collection does NOT allow duplicates?
- A) List
- B) Set ✅
- C) ArrayList
- D) LinkedList

> **Hinglish:** Set interface duplicate elements allow nahi karta hai. List allow karta hai.

---

### Q92. What is the default capacity of ArrayList?
- A) 5
- B) 10 ✅
- C) 15
- D) 0

> **Hinglish:** ArrayList ka default capacity **10** hai. Yeh dynamically grow kar sakta hai.

---

### Q93. Which is the correct way to iterate over ArrayList?
```java
ArrayList<String> list = new ArrayList<>();
list.add("A");
list.add("B");
```
- A) for(String s : list)
- B) Iterator it = list.iterator(); while(it.hasNext())
- C) for(int i=0; i<list.size(); i++)
- D) All of the above ✅

> **Hinglish:** ArrayList ko three tarike se iterate kar sakte hain: enhanced for loop, Iterator, ya simple for loop with index.

---

### Q94. What is the output?

```java
import java.util.*;

class Test {
    public static void main(String args[]) {
        ArrayList<String> al = new ArrayList<>();
        al.add("Java");
        al.add("Python");
        al.add("Java");
        
        System.out.println(al.size());
        System.out.println(al.contains("Java"));
        System.out.println(al.get(1));
    }
}
```
- A) 3 true Python
- B) 2 true Python
- C) 3 true Java
- D) 2 false Python

> **Hinglish:** ArrayList duplicate allow karta hai. size = 3, contains("Java") = true, get(1) = "Python" (0-based index).

---

### Q95. Which interface does HashMap implement?
- A) List
- B) Set
- C) Map ✅
- D) Collection

> **Hinglish:** HashMap Map interface implement karta hai, List ya Set nahi. Map key-value pairs store karta hai.

---

### Q96. What is the output?

```java
import java.util.*;

class Test {
    public static void main(String args[]) {
        HashMap<Integer, String> hm = new HashMap<>();
        hm.put(1, "Java");
        hm.put(2, "Python");
        hm.put(1, "C++");
        
        System.out.println(hm.size());
        System.out.println(hm.get(1));
    }
}
```
- A) 2 C++
- B) 2 Java
- C) 3 C++
- D) 3 Java

> **Hinglish:** HashMap mein key unique honi chahiye. put(1, "C++") se pehle wala "Java" replace ho jayega. size = 2, get(1) = "C++".

---

### Q97. Which collection maintains insertion order?
- A) HashSet
- B) LinkedHashSet ✅
- C) TreeSet
- D) HashMap

> **Hinglish:** LinkedHashSet insertion order maintain karta hai. HashSet aur TreeSet yeh nahi karte.

---

### Q98. What is the difference between HashSet and TreeSet?
- A) HashSet maintains order, TreeSet does not
- B) HashSet does not maintain order, TreeSet maintains sorted order ✅
- C) Both are same
- D) TreeSet allows null, HashSet does not

> **Hinglish:** HashSet koi order maintain nahi karta. TreeSet elements ko sorted (ascending) order mein rakhta hai.

---

### Q99. Which interface is used to sort elements?
- A) Comparable ✅
- B) Comparator
- C) Both A and B
- D) Serializable

> **Hinglish:** Comparable interface se class apne elements ko compare kar sakti hai (compareTo method). Comparator alag se sorting logic provide karta hai.

---

### Q100. What will be the output?

```java
import java.util.*;

class Test {
    public static void main(String args[]) {
        Vector<Integer> v = new Vector<>();
        v.add(10);
        v.add(20);
        v.add(10);
        
        System.out.println(v);
    }
}
```
- A) [10, 20, 10]
- B) [10, 20]
- C) Compilation Error
- D) [20, 10]

> **Hinglish:** Vector List ki tarah kaam karta hai aur insertion order maintain karta hai. Ye duplicate allow karta hai.

---

## 📚 Section 14: File I/O (Input/Output)

### Q101. Which class is used to read bytes from a file?
- A) FileInputStream ✅
- B) FileReader
- C) BufferedReader
- D) Scanner

> **Hinglish:** FileInputStream bytes read karne ke liye hai. Character data ke liye FileReader use hota hai.

---

### Q102. Which class is used to write text to a file?
- A) FileWriter ✅
- B) FileOutputStream
- C) FileInputStream
- D) InputStream

> **Hinglish:** FileWriter character stream ke liye hai (text files). Binary data ke liye FileOutputStream use hota hai.

---

### Q103. What is the output?

```java
import java.io.*;

class Test {
    public static void main(String args[]) throws IOException {
        FileWriter fw = new FileWriter("test.txt");
        fw.write("Hello Java");
        fw.close();
        
        FileReader fr = new FileReader("test.txt");
        System.out.println(fr.read());
        fr.close();
    }
}
```
- A) Hello Java
- B) H ✅
- C) 72
- D) Compilation Error

> **Hinglish:** read() ek baar mein sirf ek character ya ek byte return karta hai. 'H' ka ASCII value 72 hai, jo print hoga.

---

### Q104. Which class provides readLine() method?
- A) BufferedReader ✅
- B) BufferedWriter
- C) FileReader
- D) InputStreamReader

> **Hinglish:** BufferedReader ka readLine() method ek poora line read karta hai. Yeh efficient bhi hai kyunki buffering use karta hai.

---

### Q105. What is the difference between byte stream and character stream?
- A) Byte for images, character for text ✅
- B) No difference
- C) Character for images, byte for text
- D) Both are same

> **Hinglish:** Byte streams (InputStream/OutputStream) binary data ke liye. Character streams (Reader/Writer) text data ke liye.

---

### Q106. Which keyword is used to handle checked exceptions in method signature?
- A) throw
- B) throws ✅
- C) try
- D) catch

> **Hinglish:** throws keyword method signature mein lagta hai indicate karne ke liye ki yeh method exception throw kar sakta hai.

---

### Q107. What is serialization?
- A) Converting object to bytes ✅
- B) Converting bytes to object
- C) Reading from file
- D) Writing to file

> **Hinglish:** Serialization object ko byte stream mein convert karta hai taaki ise file mein ya network pe bhej saken. Deserialization reverse hai.

---

### Q108. Which interface must a class implement for serialization?
- A) Serializable ✅
- B) Externalizable
- C) Both A and B
- D) None

> **Hinglish:** Object ko serialize karne ke liye class ko Serializable interface implement karna hota hai.

---

## 📚 Section 15: Generics & Annotations

### Q109. What is the purpose of generics in Java?
- A) Type safety at compile time ✅
- B) Memory optimization
- C) Faster execution
- D) Security

> **Hinglish:** Generics compile-time type checking provide karte hain. Yeh ClassCastException se bachate hain aur code clean hota hai.

---

### Q110. What is the output?

```java
class Test {
    public static void main(String args[]) {
        ArrayList<String> al = new ArrayList<>();
        al.add("Java");
        al.add(100);  // What happens?
    }
}
```
- A) Works fine
- B) Compilation Error ✅
- C) Runtime Error
- D) null

> **Hinglish:** Generic type <String> declare kiya hai, toh sirf String hi add kar sakte hain. Integer add karne pe compilation error aayega.

---

### Q111. What is an annotation in Java?
- A) Metadata about a program ✅
- B) Type of variable
- C) Access modifier
- D) Type of loop

> **Hinglish:** Annotations metadata provide karte hain jo program ke baare mein information dete hain. Jaise @Override, @Deprecated, etc.

---

### Q112. Which annotation indicates a method overrides a superclass method?
- A) @Override ✅
- B) @Overload
- C) @Inherited
- D) @Polymorphism

> **Hinglish:** @Override annotation lagane se compiler check karta hai ki method actually parent class ko override kar raha hai ya nahi.

---

## 📚 Section 16: Important Programs for Exams

### Q113. Write a program to demonstrate StringBuffer methods.

```java
class StringBufferDemo {
    public static void main(String args[]) {
        StringBuffer sb = new StringBuffer("Hello");
        
        // append
        sb.append(" World");
        System.out.println("After append: " + sb);
        
        // insert
        sb.insert(5, ",");
        System.out.println("After insert: " + sb);
        
        // replace
        sb.replace(6, 11, "Java");
        System.out.println("After replace: " + sb);
        
        // delete
        sb.delete(5, 10);
        System.out.println("After delete: " + sb);
        
        // reverse
        sb.reverse();
        System.out.println("After reverse: " + sb);
        
        // capacity
        System.out.println("Capacity: " + sb.capacity());
    }
}
```

---

### Q114. Write a program to demonstrate HashMap.

```java
import java.util.*;

class HashMapDemo {
    public static void main(String args[]) {
        HashMap<Integer, String> hm = new HashMap<>();
        
        // Add elements
        hm.put(1, "Java");
        hm.put(2, "Python");
        hm.put(3, "C++");
        
        // Get element
        System.out.println("Key 2: " + hm.get(2));
        
        // Check key
        System.out.println("Contains key 1: " + hm.containsKey(1));
        
        // Remove
        hm.remove(2);
        
        // Iterate
        for(Map.Entry m : hm.entrySet()) {
            System.out.println(m.getKey() + ": " + m.getValue());
        }
    }
}
```

---

### Q115. Write a program demonstrating thread creation using Runnable.

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread running via Runnable");
    }
}

class Test {
    public static void main(String args[]) {
        MyRunnable r = new MyRunnable();
        Thread t = new Thread(r);
        t.start();
    }
}
```

---

### Q116. Write a program to demonstrate synchronized method.

```java
class Counter {
    int count = 0;
    
    synchronized void increment() {
        count++;
        System.out.println("Count: " + count);
    }
}

class MyThread extends Thread {
    Counter c;
    MyThread(Counter c) {
        this.c = c;
    }
    
    public void run() {
        for(int i = 0; i < 5; i++) {
            c.increment();
        }
    }
}

class Test {
    public static void main(String args[]) {
        Counter c = new Counter();
        MyThread t1 = new MyThread(c);
        MyThread t2 = new MyThread(c);
        t1.start();
        t2.start();
    }
}
```

---

### Q117. Write a program to read file using BufferedReader.

```java
import java.io.*;

class FileReadDemo {
    public static void main(String args[]) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader("test.txt"));
        
        String line;
        while((line = br.readLine()) != null) {
            System.out.println(line);
        }
        br.close();
    }
}
```

---

### Q118. Write a program to demonstrate ArrayList.

```java
import java.util.*;

class ArrayListDemo {
    public static void main(String args[]) {
        ArrayList<String> al = new ArrayList<>();
        
        // Add elements
        al.add("Java");
        al.add("Python");
        al.add("C++");
        al.add(1, "JavaScript");  // Insert at index
        
        // Size
        System.out.println("Size: " + al.size());
        
        // Get
        System.out.println("Element at 2: " + al.get(2));
        
        // Contains
        System.out.println("Contains Java: " + al.contains("Java"));
        
        // Remove
        al.remove("Python");
        
        // Iterate
        for(String s : al) {
            System.out.println(s);
        }
    }
}
```

---

### Q119. Write a program to demonstrate autoboxing and unboxing.

```java
class AutoboxingDemo {
    public static void main(String args[]) {
        // Autoboxing: primitive to wrapper
        Integer i = 100;  // Automatically boxed
        
        // Unboxing: wrapper to primitive
        int j = i;  // Automatically unboxed
        
        // Method with wrapper
        process(Integer.valueOf(50));
    }
    
    static void process(Integer num) {
        System.out.println("Processing: " + num);
        int x = num + 10;  // Unboxing in expression
        System.out.println("Result: " + x);
    }
}
```

---

### Q120. Write a program demonstrating custom exception.

```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String msg) {
        super(msg);
    }
}

class VoterCheck {
    static void checkAge(int age) throws InvalidAgeException {
        if(age < 18) {
            throw new InvalidAgeException("Age must be 18 or above!");
        }
        System.out.println("Eligible to vote");
    }
    
    public static void main(String args[]) {
        try {
            checkAge(16);
        } catch(InvalidAgeException e) {
            System.out.println("Exception: " + e.getMessage());
        }
    }
}
```

---

## 🎯 Final Practice Tips

1. **Practice code daily** - Type programs manually
2. **Understand concepts** - Don't just memorize
3. **Draw diagrams** - For inheritance, memory
4. **Solve MCQs** - Focus on tricky ones
5. **Time management** - Don't spend too long on one question

### Topic-wise Quick Summary:

**Packages:** package keyword, import statements, java.lang auto-import
**Strings:** Immutable, String pool, StringBuffer/StringBuilder (mutable)
**Wrapper Classes:** Integer, Double, etc., autoboxing/unboxing, cache
**Multithreading:** Thread vs Runnable, synchronized, wait/sleep
**Collections:** List (allow duplicates), Set (no duplicates), Map (key-value)
**File I/O:** Streams (byte), Readers/Writers (character), Serialization

### Important Methods to Remember:

```
String:     length(), charAt(), substring(), equals(), indexOf(), split()
StringBuffer: append(), insert(), replace(), delete(), reverse()
ArrayList:  add(), get(), remove(), size(), contains()
HashMap:    put(), get(), remove(), keySet(), entrySet()
Thread:     start(), run(), sleep(), join(), yield()
```

---

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.BonusQuestions)
