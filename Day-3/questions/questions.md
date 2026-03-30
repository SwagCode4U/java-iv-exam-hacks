# 📚 Day 3: Interface & Abstract Class - Question Bank

![Java](https://img.shields.io/badge/Java-Interface%20%26%20Abstract-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%203-success?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-40+-blue?style=for-the-badge)

> *Mastering the art of abstraction in Java!*

---

## 🎯 Section A: Multiple Choice Questions (MCQs)

### Q1. Which keyword is used to achieve 100% abstraction?
- A) abstract
- B) interface ✅
- C) extends
- D) implements

> **Hinglish:** Interface 100% abstraction deta hai kyunki isme sirf method declarations hote hain, body nahi.

---

### Q2. Can we instantiate an interface?
- A) Yes, directly
- B) Yes, using new keyword
- C) No ✅
- D) Only in Java 8+

> **Hinglish:** Interface ko directly instantiate nahi kar sakte.
> // ❌ Drawable d = new Drawable();
> // ✅ Drawable d = new Rectangle();

---

### Q3. How many interfaces can a class implement?
- A) One
- B) Two
- C) Unlimited ✅
- D) Zero

> **Hinglish:** Aap ek class ko multiple interfaces implement kar sakte ho.
> // class Demo implements IF1, IF2, IF3 {}

---

### Q4. Can an interface extend another interface?
- A) No
- B) Yes, using extends ✅
- C) Only if abstract
- D) Only in Java 8+

> **Hinglish:** Interface doosre interface ko extend kar sakta hai.
> // interface A {} interface B extends A {}

---

### Q5. Which is TRUE about abstract class?
- A) Cannot have constructors
- B) Can be instantiated directly
- C) Can have both abstract and non-abstract methods ✅
- D) Must have all abstract methods

> **Hinglish:** Abstract class mein abstract methods (without body) aur normal methods (with body) dono ho sakte hain. Direct instantiation nahi kar sakte.

---

### Q6. What is the default access modifier for interface variables?
- A) private
- B) protected
- C) public ✅
- D) default

> **Hinglish:** Interface ke variables **public static final** hote hain automatically. Matlab constants hain.

---

### Q7. Which keyword is used to implement an interface?
- A) extends
- B) implements ✅
- C) inherit
- D) override

> **Hinglish:** **implements** keyword se interface implement hota hai.
> // class Rectangle implements Drawable {}

---

### Q8. Can an abstract class have a main method?
- A) No
- B) Yes ✅
- C) Only static main
- D) Only one main

> **Hinglish:** Abstract class mein normal methods bhi ho sakte hain, toh main method bhi ho sakta hai.

---

### Q9. What is the output?

```java
interface Drawable {
    void draw();
}

class Rectangle implements Drawable {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

public class Test {
    public static void main(String args[]) {
        Drawable d = new Rectangle();
        d.draw();
    }
}
```
- A) Compilation Error
- B) Drawing Rectangle ✅
- C) Runtime Error
- D) No Output

> **Hinglish:** Interface reference se child class ka object create kar sakte ho (Runtime Polymorphism).

---

### Q10. Which is NOT a feature of interface?
- A) Can have abstract methods
- B) Can have instance variables ✅
- C) Can have default methods (Java 8+)
- D) Can extend multiple interfaces

> **Hinglish:** Interface mein constructor nahi hota, instance variables bhi nahi hote. Variables public static final hote hain.

---

### Q11. Which of these is true about abstract class?
- A) Can have only abstract methods
- B) Cannot have instance variables
- C) Cannot be instantiated ✅
- D) Cannot have constructors

> **Hinglish:** Abstract class ko instantiate nahi kar sakte, lekin constructor ho sakta hai.

---

### Q12. How to achieve multiple inheritance in Java?
- A) extends multiple classes
- B) implements multiple interfaces ✅
- C) Using inheritance keyword
- D) Not possible

> **Hinglish:** Java mein multiple inheritance sirf interfaces se possible hai.
> // class Demo implements IF1, IF2, IF3 {}

---

### Q13. What is the default value of interface variables?
- A) null
- B) 0
- C) false
- D) public static final (constants) ✅

> **Hinglish:** Interface variables **public static final** hote hain automatically, matlab constants hain.

---

### Q14. Can an abstract class contain abstract methods only?
- A) Yes, always
- B) No, can have both ✅
- C) No, only non-abstract
- D) Only one abstract method

> **Hinglish:** Abstract class mein abstract methods (without body) aur normal methods (with body) dono ho sakte hain.

---

### Q15. Which is NOT a reason to use interface?
- A) Achieve abstraction
- B) Achieve multiple inheritance
- C) Achieve loose coupling
- D) Achieve encapsulation ✅

> **Hinglish:** Encapsulation class ke through achieve hota hai, interface se nahi. Interface ka main purpose hai abstraction aur multiple inheritance.

---

### Q16. What is the output?

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing Circle");
    }
}

public class Test {
    public static void main(String args[]) {
        Shape s = new Circle();
        s.draw();
    }
}
```
- A) Compilation Error
- B) Drawing Circle ✅
- C) Runtime Error
- D) No Output

> **Hinglish:** Abstract class reference se child object create kar sakte ho.

---

### Q17. Can an interface have default methods (Java 8+)?**
- A) No, never
- B) Yes, with body using default keyword ✅
- C) Only static methods
- D) Only private methods

> **Hinglish:** Java 8 se interface mein **default methods** ho sakte hain (with body).

---

### Q18. Which keyword makes a method abstract?
- A) abstract ✅
- B) interface
- C) implements
- D) extends

> **Hinglish:** **abstract** keyword se method ko abstract banate hain (without body).

---

### Q19. What is abstraction?
- A) Hiding complexity
- B) Showing essential features
- C) Hiding implementation
- D) All of the above ✅

> **Hinglish:** Abstraction sirf essential details dikhana aur implementation hide karna hai. Dono included hain.

---

### Q20. Which is the correct syntax to declare an interface?
- A) abstract interface Drawable
- B) interface Drawable ✅
- C) class interface Drawable
- D) implement interface Drawable

> **Hinglish:** Interface declare karne ka syntax hai: `interface InterfaceName {}`

---

## 🎯 Section B: Long Answer Questions

### Q21. What is Interface? Explain with examples.

**Answer:**

**Definition:**
Interface ek blueprint hai jisme sirf abstract methods aur constants hote hain. Yeh abstraction aur multiple inheritance achieve karne ke liye use hota hai.

**Key Features:**
```java
// 1. Interface mein methods by default abstract hote hain
// 2. Variables by default public static final hote hain (constants)
// 3. Constructor nahi hota
// 4. Multiple inheritance support karta hai
// 5. Class interface ko "implements" karta hai
// 6. 100% abstraction achieve karta hai
```

**Syntax:**
```java
interface InterfaceName {
    // By default: public static final constants
    int MAX_SPEED = 120;
    
    // By default: public abstract methods
    void start();
    void stop();
}
```

**Simple Example:**
```java
// Step 1: Interface declare karo
interface Drawable {
    void draw();  // By default public abstract
}

// Step 2: Interface implement karo
class Rectangle implements Drawable {
    // Must implement all methods
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

// Step 3: Use karo
public class TestInterface {
    public static void main(String args[]) {
        Drawable d;  // Interface reference
        d = new Rectangle();  // Object create
        d.draw();  // Output: Drawing Rectangle
    }
}
```

**Multiple Interface Implementation:**
```java
interface Printable {
    void print();
}

interface Drawable {
    void draw();
}

// Aap ek class mein multiple interfaces implement kar sakte ho
class Document implements Printable, Drawable {
    public void print() {
        System.out.println("Printing Document");
    }
    
    public void draw() {
        System.out.println("Drawing Document");
    }
}
```

---

### Q22. What is Abstract Class? Explain with examples.

**Answer:**

**Definition:**
Abstract class ek class hai jise **abstract** keyword se declare kiya jata hai. Isme abstract methods (without body) aur non-abstract methods (with body) dono ho sakte hain.

**Key Features:**
```java
// 1. Abstract class ko directly instantiate nahi kar sakte
// 2. Isme abstract methods ho sakte hain (without body)
// 3. Isme non-abstract methods bhi ho sakte hain (with body)
// 4. Constructor ho sakta hai
// 5. 0% to 100% abstraction achieve kar sakta hai
```

**Example:**
```java
// Abstract class declare karo
abstract class Shape {
    String color;
    
    // Constructor - allowed in abstract class
    Shape(String c) {
        color = c;
    }
    
    // Abstract method - no body
    abstract void draw();
    
    // Non-abstract method - with body
    void displayColor() {
        System.out.println("Color: " + color);
    }
}

// Concrete class - abstract methods implement karo
class Circle extends Shape {
    Circle(String c) {
        super(c);  // Parent constructor call
    }
    
    void draw() {
        System.out.println("Drawing Circle with color: " + color);
    }
}

public class AbstractDemo {
    public static void main(String args[]) {
        // Shape s = new Shape();  // ❌ Error - cannot instantiate
        
        Shape s = new Circle("Red");  // ✅ Using reference
        s.displayColor();  // Non-abstract method
        s.draw();          // Abstract method (implemented)
    }
}
```

---

### Q23. Difference between Abstract Class and Interface.

**Answer:**

| Aspect | Abstract Class | Interface |
|--------|---------------|-----------|
| **Methods** | Abstract + Non-abstract | Only abstract (Java 7), default methods (Java 8+) |
| **Variables** | Any type | Only public static final (constants) |
| **Constructor** | Allowed | Not allowed |
| **Access Modifiers** | All modifiers | Only public (by default) |
| **Multiple Inheritance** | Not supported | Supported |
| **Inheritance Keyword** | extends | implements |
| **Speed** | Faster | Slightly slower |
| **Use Case** | "is-a" relationship | "has-a" capability |

**Abstract Class Example:**
```java
// Abstract class - common functionality share karne ke liye
abstract class Vehicle {
    String brand;
    
    Vehicle(String b) {
        brand = b;
    }
    
    // Abstract method - subclasses implement karenge
    abstract void start();
    
    // Non-abstract - shared implementation
    void displayBrand() {
        System.out.println("Brand: " + brand);
    }
}

class Car extends Vehicle {
    Car(String b) {
        super(b);
    }
    
    void start() {
        System.out.println(brand + " car started");
    }
}
```

**Interface Example:**
```java
// Interface - capability define karne ke liye
interface Drivable {
    void drive();
}

interface Flyable {
    void fly();
}

// Multiple interfaces - not possible with abstract class
class FlyingCar implements Drivable, Flyable {
    public void drive() {
        System.out.println("Driving on road");
    }
    
    public void fly() {
        System.out.println("Flying in sky");
    }
}
```

**When to Use What?**

| Use Abstract Class When | Use Interface When |
|------------------------|-------------------|
| Creating a family of related classes | Defining capabilities/contracts |
| Need constructor for initialization | Need multiple inheritance |
| Need non-abstract methods | Need 100% abstraction |
| Classes share common code | Designing unrelated classes |
| Creating "is-a" relationship | Creating "can-do" relationship |

---

### Q24. What is Abstraction? Explain with real-life examples.

**Answer:**

**Definition:**
Abstraction sirf essential details dikhana hai aur implementation details hide karna hai. User ko sirf "kya" pata hai, "kaise" nahi.

**Real-Life Examples:**

**Example 1: ATM Machine**
```
┌─────────────────────────────────┐
│         ATM MACHINE              │
│  ┌─────────────────────────────┐ │
│  │ Card Slot                  │ │
│  │ Screen                     │ │
│  │ Keypad                     │ │
│  │ Cash Dispenser             │ │
│  └─────────────────────────────┘ │
│                                 │
│  User Interface (Abstract):       │
│  ✅ Insert Card                │
│  ✅ Enter PIN                  │
│  ✅ Select Option              │
│  ✅ Get Cash                   │
│                                 │
│  Hidden Implementation:           │
│  ❌ Database connection         │
│  ❌ Transaction processing       │
│  ❌ Network communication      │
└─────────────────────────────────┘
```

**Example 2: Driving a Car**
```
User Does:                    Car Internally Does:
✅ Press Accelerator           ❌ Fuel injection
✅ Press Brake                 ❌ Gear shifting
✅ Turn Steering               ❌ ABS activation
✅ Change Gears               ❌ Power steering
```

**Example 3: Sending SMS**
```
User Action:
✅ Type: "Hello"
✅ Press: Send
✅ Result: Message Sent

What's Hidden:
❌ Message network mein convert hota hai
❌ Mobile tower se connected hota hai
❌ Recipient tower se receive hota hai
```

---

## 🎯 Section C: Predict the Output

### Q25. What is the output?

```java
interface A {
    void show();
}

interface B {
    void display();
}

class Demo implements A, B {
    public void show() {
        System.out.println("A's show");
    }
    
    public void display() {
        System.out.println("B's display");
    }
}

public class Test {
    public static void main(String args[]) {
        Demo d = new Demo();
        d.show();
        d.display();
    }
}
```

**Answer:**
```
A's show
B's display
```

---

### Q26. What is the output?

```java
abstract class Parent {
    Parent() {
        System.out.println("Parent Constructor");
    }
    
    abstract void show();
}

class Child extends Parent {
    Child() {
        super();  // Automatically called
        System.out.println("Child Constructor");
    }
    
    void show() {
        System.out.println("Child Show");
    }
}

public class Test {
    public static void main(String args[]) {
        Parent p = new Child();
        p.show();
    }
}
```

**Answer:**
```
Parent Constructor
Child Constructor
Child Show
```

---

### Q27. What is the output?

```java
interface Sample {
    int VALUE = 100;
}

class Test implements Sample {
    public static void main(String args[]) {
        System.out.println(VALUE);
        // VALUE = 200;  // What if uncommented?
    }
}
```

**Answer: 100**

**Explanation:**
// Interface variables are final (constant) by default

---

### Q28. What is the output?

```java
abstract class Base {
    abstract void print();
    void show() {
        System.out.println("Base show");
    }
}

class Derived extends Base {
    void print() {
        System.out.println("Derived print");
    }
}

class Test {
    public static void main(String args[]) {
        Base b = new Derived();
        b.show();
        b.print();
    }
}
```

**Answer:**
```
Base show
Derived print
```

---

### Q29. What is the output?

```java
interface Printable {
    void print();
}

interface Showable extends Printable {
    void show();
}

class Demo implements Showable {
    public void print() {
        System.out.println("Printing");
    }
    
    public void show() {
        System.out.println("Showing");
    }
}

class Test {
    public static void main(String args[]) {
        Demo d = new Demo();
        d.print();
        d.show();
    }
}
```

**Answer:**
```
Printing
Showing
```

---

### Q30. What happens?

```java
abstract class Demo {
    abstract void test();
}

// In main method:
Demo d = new Demo();
```

- A) Prints "Demo"
- B) Compilation Error ✅
- C) Runtime Error
- D) No output

**Answer:** Compilation Error - Cannot instantiate abstract class

---

## 🎯 Section D: Coding Questions

### Q31. Write a complete program demonstrating interface.

```java
// ===== INTERFACE =====
interface Bank {
    double MIN_BALANCE = 500;
    
    void deposit(double amount);
    void withdraw(double amount);
    double getBalance();
}

// ===== IMPLEMENTATION =====
class SavingsAccount implements Bank {
    private double balance;
    
    SavingsAccount() {
        balance = 0;
    }
    
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: " + amount);
        }
    }
    
    public void withdraw(double amount) {
        if (amount > 0 && (balance - amount) >= MIN_BALANCE) {
            balance -= amount;
            System.out.println("Withdrawn: " + amount);
        } else {
            System.out.println("Cannot withdraw!");
        }
    }
    
    public double getBalance() {
        return balance;
    }
}

// ===== MAIN CLASS =====
public class BankDemo {
    public static void main(String args[]) {
        Bank b = new SavingsAccount();
        b.deposit(5000);
        b.withdraw(1000);
        System.out.println("Balance: " + b.getBalance());
    }
}
```

---

### Q32. Write a complete program demonstrating abstract class.

```java
// ===== ABSTRACT CLASS =====
abstract class Shape {
    protected String color;
    
    Shape(String color) {
        this.color = color;
    }
    
    abstract double calculateArea();
    abstract void draw();
}

// ===== CONCRETE CLASS =====
class Circle extends Shape {
    private double radius;
    
    Circle(String color, double r) {
        super(color);
        radius = r;
    }
    
    double calculateArea() {
        return Math.PI * radius * radius;
    }
    
    void draw() {
        System.out.println("Drawing Circle with color: " + color);
    }
}

// ===== MAIN CLASS =====
public class ShapeDemo {
    public static void main(String args[]) {
        Shape circle = new Circle("Red", 5);
        circle.draw();
        System.out.println("Area: " + circle.calculateArea());
    }
}
```

---

### Q33. Write a program to demonstrate multiple interfaces.

```java
// Interface 1
interface Printable {
    void print();
}

// Interface 2
interface Showable {
    void show();
}

// Class implements both interfaces
class Document implements Printable, Showable {
    private String content;
    
    Document(String c) {
        content = c;
    }
    
    public void print() {
        System.out.println("Printing: " + content);
    }
    
    public void show() {
        System.out.println("Showing: " + content);
    }
}

public class MultiInterfaceDemo {
    public static void main(String args[]) {
        Document doc = new Document("Hello World");
        doc.print();  // From Printable
        doc.show();   // From Showable
    }
}
```

---

### Q34. Write a program demonstrating interface inheritance.

```java
// Parent interfaces
interface A {
    void methodA();
}

interface B {
    void methodB();
}

// Child interface - extends multiple interfaces
interface C extends A, B {
    void methodC();
}

// Implementation
class Demo implements C {
    public void methodA() {
        System.out.println("Method A");
    }
    
    public void methodB() {
        System.out.println("Method B");
    }
    
    public void methodC() {
        System.out.println("Method C");
    }
}

public class InterfaceInheritanceDemo {
    public static void main(String args[]) {
        Demo d = new Demo();
        d.methodA();
        d.methodB();
        d.methodC();
    }
}
```

---

### Q35. Write a program to demonstrate abstraction.

```java
// Abstract class demonstrating abstraction
abstract class Vehicle {
    String name;
    
    Vehicle(String n) {
        name = n;
    }
    
    // Abstract methods - subclasses implement karenge
    abstract void start();
    abstract void stop();
    
    // Concrete method - shared implementation
    void display() {
        System.out.println("Vehicle: " + name);
    }
}

class Car extends Vehicle {
    Car(String n) {
        super(n);
    }
    
    void start() {
        System.out.println(name + " car started");
    }
    
    void stop() {
        System.out.println(name + " car stopped");
    }
}

public class AbstractionDemo {
    public static void main(String args[]) {
        Vehicle v = new Car("BMW");
        v.display();
        v.start();
        v.stop();
    }
}
```

---

## 📋 Quick Reference Table - Day 3

| Topic | Key Points |
|-------|-----------|
| **Interface** | 100% abstraction, no constructor, multiple inheritance possible |
| **Abstract Class** | 0-100% abstraction, can have constructor, single inheritance |
| **Abstraction** | Hide complexity, show essentials |
| **Interface Variables** | public static final (automatic) |
| **Interface Methods** | public abstract (automatic) |
| **Implement Keyword** | Used to implement interface |
| **Extends Keyword** | Used to extend interface |

---

## ✅ Day 3 Self-Check

Before moving to Day 4, make sure you can answer:

- [ ] What is the difference between abstract class and interface?
- [ ] How do you achieve 100% abstraction?
- [ ] Can a class implement multiple interfaces?
- [ ] What are the default modifiers for interface variables and methods?
- [ ] When should you use abstract class vs interface?

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

➡️ **[Day 4: Exception Handling](../Day-4/)**

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day3.Questions)
