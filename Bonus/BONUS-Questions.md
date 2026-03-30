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

## 🎯 Final Practice Tips

1. **Practice code daily** - Type programs manually
2. **Understand concepts** - Don't just memorize
3. **Draw diagrams** - For inheritance, memory
4. **Solve MCQs** - Focus on tricky ones
5. **Time management** - Don't spend too long on one question

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.BonusQuestions)
