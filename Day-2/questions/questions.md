# 📚 Day 2: Classes, Objects & Inheritance - Question Bank

![Java](https://img.shields.io/badge/Java-Classes%20%26%20Inheritance-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%202-success?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-50+-blue?style=for-the-badge)

> *Building blocks of Java - Master Classes, Objects and Inheritance!*

---

## 🎯 Section A: Multiple Choice Questions (MCQs)

### Q1. What is the default value of instance variable?
- A) null
- B) Depends on data type ✅
- C) 0
- D) false

> **Hinglish:** Instance variables ki default values unke data type pe depend karti hain: int = 0, boolean = false, String = null.

---

### Q2. Which keyword is used to inherit a class?
- A) inherits
- B) extends ✅
- C) implements
- D) super

> **Hinglish:** **extends** keyword se inheritance hoti hai. `class Dog extends Animal {}`

---

### Q3. How many times is default constructor called?
- A) Once
- B) Twice
- C) As many times as objects are created ✅
- D) Never

> **Hinglish:** Har object create karte waqt constructor call hota hai. 5 objects = 5 baar constructor call.

---

### Q4. Which is NOT a type of inheritance in Java?
- A) Single
- B) Multiple ✅
- C) Hierarchical
- D) Multilevel

> **Hinglish:** Java **Multiple Inheritance class-through support nahi karta**. Yeh sirf Interface se possible hai.

---

### Q5. Method Overloading is an example of:
- A) Runtime Polymorphism
- B) Compile Time Polymorphism ✅
- C) Both
- D) None

> **Hinglish:** Method Overloading compile time pe decide hota hai kaunsa method call ho - isliye **Compile Time Polymorphism**.

---

### Q6. Method Overriding is an example of:
- A) Runtime Polymorphism ✅
- B) Compile Time Polymorphism
- C) Both
- D) None

> **Hinglish:** Method Overriding runtime pe decide hota hai - parent reference child object ko point kar raha ho toh child ka method chalega.

---

### Q7. Which access modifier is most restrictive?
- A) protected
- B) default
- C) private ✅
- D) public

> **Hinglish:** **private** sabse restrictive hai - sirf same class se accessible. Hierarchy: public > protected > default > private

---

### Q8. Which cannot be inherited?
- A) protected members
- B) private members ✅
- C) public members
- D) default members

> **Hinglish:** Private members sirf apni class mein accessible hote hain, inheritance se bhi hidden rehte hain.

---

### Q9. What is the output?

```java
class Parent {
    void show() { System.out.println("Parent"); }
}
class Child extends Parent {
    void show() { System.out.println("Child"); }
}
public class Test {
    public static void main(String args[]) {
        Parent p = new Child();
        p.show();
    }
}
```
- A) Parent
- B) Child ✅
- C) Compilation Error
- D) Runtime Error

> **Hinglish:** Parent reference, Child object - runtime pe decide hoga ki Child ka show() call ho (Method Overriding/Runtime Polymorphism).

---

### Q10. Which is NOT true about static methods?
- A) Can be called without object
- B) Can access static variables
- C) Can use 'this' keyword ✅
- D) Belong to class, not object

> **Hinglish:** Static methods mein **'this' aur 'super' use nahi kar sakte** kyunki yeh class se belong karte hain, object se nahi.

---

### Q11. What is the output?

```java
class Demo {
    static int count = 0;
    Demo() { count++; }
    public static void main(String args[]) {
        Demo d1 = new Demo();
        Demo d2 = new Demo();
        Demo d3 = new Demo();
        System.out.println(count);
    }
}
```
- A) 1
- B) 2
- C) 3 ✅
- D) 0

> **Hinglish:** 3 objects create hue, har baar constructor call hua, count++ teeno baar execute hua. count = 3

---

### Q12. Which is true about final variable?
- A) Can be changed
- B) Cannot be changed ✅
- C) Can be overridden
- D) Is always static

> **Hinglish:** final variable ko ek baar value assign karo toh change nahi kar sakte. **final = constant**

---

### Q13. What is the output?

```java
class Test {
    void show(int x) { System.out.println("int"); }
    void show(double x) { System.out.println("double"); }
    public static void main(String args[]) {
        Test t = new Test();
        t.show(5);
    }
}
```
- A) int ✅
- B) double
- C) Both
- D) Error

> **Hinglish:** 5 integer hai, toh int wala method match karega (exact type preference).

---

### Q14. Constructor overloading means:
- A) Inheriting constructors
- B) Multiple constructors with different parameters ✅
- C) Overriding constructors
- D) Static constructors

> **Hinglish:** Constructor Overloading = ek class mein multiple constructors different parameters ke saath.

---

### Q15. Which keyword is used to call parent constructor?
- A) parent
- B) this
- C) super ✅
- D) base

> **Hinglish:** **super()** se parent class ka constructor call hota hai. super() automatically call hota agar explicitly nahi likha toh bhi.

---

### Q16. What is the default constructor?
- A) Constructor with one parameter
- B) Constructor with no parameters ✅
- C) Static constructor
- D) Private constructor

> **Hinglish:** Default constructor = no-arg constructor = koi parameter nahi.

---

### Q17. Which cannot be overridden?
- A) Instance method
- B) Static method
- C) final method ✅
- D) Private method

> **Hinglish:** final methods override nahi kar sakte. Static methods override nahi hote (yeh hiding hai).

---

### Q18. The relationship IS-A refers to:
- A) Aggregation
- B) Composition
- C) Inheritance ✅
- D) Association

> **Hinglish:** IS-A relationship inheritance ko represent karta hai. **Dog IS-A Animal = true**

---

### Q19. What is the output?

```java
class Base {
    Base() { System.out.print("Base "); }
}
class Derived extends Base {
    Derived() { System.out.print("Derived "); }
}
class Test {
    public static void main(String args[]) {
        new Derived();
    }
}
```
- A) Derived
- B) Base
- C) Base Derived ✅
- D) Error

> **Hinglish:** super() automatically call hota parent constructor mein, toh pehle "Base" print hoga, phir "Derived".

---

### Q20. Which is NOT a valid access modifier?
- A) public
- B) protected
- C) friend ✅
- D) private

> **Hinglish:** Java mein "friend" access modifier nahi hai. Valid modifiers hain: public, protected, default, private.

---

## 🎯 Section B: Long Answer Questions

### Q21. What is Inheritance? Explain all types with examples and diagrams.

**Answer:**

**Definition:**
Inheritance ek mechanism hai jahan ek class (child/subclass) doosri class (parent/superclass) ki properties aur behaviors le sakti hai.

**Why Use Inheritance?**
```java
// 1. Code Reusability - ek baar likho, baar baar use karo
// 2. Method Overriding - runtime polymorphism achieve karo
// 3. IS-A Relationship - real world modeling ke liye
```

**Types of Inheritance:**

**1. Single Inheritance:**
```
    A
    │
    B
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

public class Test {
    public static void main(String args[]) {
        Dog d = new Dog();
        d.eat();   // From Animal
        d.bark();  // Its own
    }
}
```

**2. Multilevel Inheritance:**
```
    A
    │
    B
    │
    C
```
```java
class Animal {
    void eat() { System.out.println("Eating..."); }
}

class Dog extends Animal {
    void bark() { System.out.println("Barking..."); }
}

class BabyDog extends Dog {
    void weep() { System.out.println("Weeping..."); }
}

public class Test {
    public static void main(String args[]) {
        BabyDog bd = new BabyDog();
        bd.eat();   // From Animal
        bd.bark();  // From Dog
        bd.weep();  // Its own
    }
}
```

**3. Hierarchical Inheritance:**
```
    A
   ╱ ╲
  B   C
```
```java
class Animal {
    void eat() { System.out.println("Eating..."); }
}

class Dog extends Animal {
    void bark() { System.out.println("Barking..."); }
}

class Cat extends Animal {
    void meow() { System.out.println("Meowing..."); }
}
```

**Important Note:**
```java
// Java Multiple Inheritance (class-through) SUPPORT NAHI KARTA
class A { }
class B { }
class C extends A, B { }  // ❌ ERROR! Multiple inheritance not allowed

// Solution: Use Interfaces
interface A { }
interface B { }
class C implements A, B { }  // ✅ ALLOWED via Interface
```

---

### Q22. Explain Method Overriding with rules and examples.

**Answer:**

**Definition:**
Jab subclass ka method parent class ke method se **same name aur same parameters** rakhta hai, toh woh **Method Overriding** hai.

**Rules for Method Overriding:**
```java
// 1. Method ka naam SAME hona chahiye
// 2. Parameters SAME hone chahiye (number aur type)
// 3. IS-A relationship honi chahiye (inheritance)
// 4. Private methods override nahi ho sakte
// 5. Static methods override nahi hote (yeh hiding hai)
// 6. Return type same ya covariant honi chahiye
```

**Example:**
```java
class Vehicle {
    void run() {
        System.out.println("Vehicle is running");
    }
}

class Bike extends Vehicle {
    @Override  // Annotation - best practice
    void run() {
        System.out.println("Bike is running at 60kmph");
    }
}

public class TestOverriding {
    public static void main(String args[]) {
        Bike obj = new Bike();
        obj.run();  // Output: Bike is running at 60kmph
    }
}
```

**Real-life Scenario:**
```java
// Parent class: Teacher
class Teacher {
    void teach() {
        System.out.println("Teaching subjects");
    }
}

// Child class: Maths Teacher
class MathsTeacher extends Teacher {
    @Override
    void teach() {
        System.out.println("Teaching Mathematics");
    }
}
```

---

### Q23. Difference between Method Overloading and Method Overriding.

**Answer:**

| Aspect | Method Overloading | Method Overriding |
|--------|------------------|------------------|
| **Definition** | Same name, different parameters | Same name, same parameters, different class |
| **Relationship** | Same class | Different classes (inheritance) |
| **Purpose** | Increase readability, flexibility | Provide specific implementation |
| **Polymorphism Type** | Compile Time (Static) | Runtime (Dynamic) |
| **Parameters** | Must be different | Must be same |
| **Return Type** | Can be same or different | Same or covariant |

**Overloading Example:**
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }
    
    int add(int a, int b, int c) {
        return a + b + c;
    }
    
    double add(double a, double b) {
        return a + b;
    }
}
```

**Overriding Example:**
```java
class Parent {
    void display() {
        System.out.println("Parent Display");
    }
}

class Child extends Parent {
    @Override
    void display() {
        System.out.println("Child Display");
    }
}
```

---

### Q24. Explain all Access Modifiers with examples.

**Answer:**

**Access Modifier Hierarchy:**
```
Most Open:     public     ──────────────────> All
               protected  ───────────────> Same Package + Subclasses
               default    ─────────> Same Package Only
Most Restrictive: private  ───> Same Class Only
```

**1. public:**
```java
// EVERYWHERE accessible - sabse open
public class Student {
    public String name;  // Sab jagah se accessible
}
```

**2. protected:**
```java
// Same package mein sab jagah accessible
// Different package mein sirf inheritance ke through
protected String collegeName;
```

**3. default (Friendly):**
```java
// Koi modifier nahi likha toh default
// Sirf same package mein accessible
String batch;  // default - sirf same package
```

**4. private:**
```java
// Sabse restrictive - sirf same class mein
// Inheritance se bhi pass nahi hota
private double balance;  // Sirf is class mein accessible
```

**Complete Access Table:**

| Location | public | protected | default | private |
|----------|--------|-----------|---------|---------|
| Same Class | ✅ | ✅ | ✅ | ✅ |
| Same Package (Subclass) | ✅ | ✅ | ✅ | ❌ |
| Same Package (Non-subclass) | ✅ | ✅ | ✅ | ❌ |
| Different Package (Subclass) | ✅ | ✅ | ❌ | ❌ |
| Different Package (Non-subclass) | ✅ | ❌ | ❌ | ❌ |

---

### Q25. Explain Constructors in detail with types and overloading.

**Answer:**

**What is Constructor?**
Constructor ek special method hai jo object create hote waqt automatically call hota hai. Object ko initialize karta hai.

**Rules for Constructor:**
```java
// 1. Constructor ka naam class ke naam se SAME hona chahiye
// 2. Koi return type NAHI hota (void bhi nahi)
```

**Types of Constructors:**

**1. Default Constructor (No-arg):**
```java
class Bike {
    Bike() {  // Default constructor
        System.out.println("Bike object created!");
    }
}
```

**2. Parameterized Constructor:**
```java
class Student {
    int id;
    String name;
    
    Student(int i, String n) {
        id = i;
        name = n;
    }
    
    void display() {
        System.out.println(id + " " + name);
    }
}
```

**Constructor Overloading:**
```java
class Account {
    int accountNo;
    String name;
    
    Account() { }  // No-arg
    
    Account(int accNo) {
        accountNo = accNo;
    }
    
    Account(int accNo, String n) {
        accountNo = accNo;
        name = n;
    }
}
```

---

### Q26. What is Nesting of Methods? Explain with examples.

**Answer:**

**Definition:**
Nesting of methods means calling one method from another method of the **same class** without using the dot operator or object reference.

**Key Points:**
```java
// 1. Methods of SAME class can call each other directly
// 2. No need for object reference or dot operator
// 3. Only works within the same class
// 4. Useful for code organization and reuse
```

**Example 1: Simple Nesting**
```java
class Calculator {
    int a, b;
    
    void setData(int x, int y) {
        a = x;
        b = y;
    }
    
    int findMax() {
        if (a > b)
            return a;
        else
            return b;
    }
    
    void display() {
        int max = findMax();  // Nesting - calling method directly
        System.out.println("Maximum: " + max);
    }
    
    public static void main(String args[]) {
        Calculator c = new Calculator();
        c.setData(10, 20);
        c.display();  // Output: Maximum: 20
    }
}
```

**Example 2: Complex Nesting**
```java
class Employee {
    String name;
    int salary;
    
    void accept(String n, int s) {
        name = n;
        salary = s;
    }
    
    void calculate() {
        salary = salary + (salary * 10 / 100);  // Add 10% bonus
    }
    
    void display() {
        calculate();  // Nesting
        System.out.println("Name: " + name);
        System.out.println("Salary: " + salary);
    }
    
    public static void main(String args[]) {
        Employee e = new Employee();
        e.accept("Rahul", 50000);
        e.display();
    }
}
```

**Important Note:**
```java
// ✅ Allowed - Calling own class methods
void method1() {
    method2();  // Direct call
}

// ❌ Not nesting - Calling different class method
void method1() {
    obj.method2();  // Object reference needed
}
```

---

## 🎯 Section C: Predict the Output

### Q27. What is the output?

```java
class Parent {
    Parent() { System.out.println("Parent Constructor"); }
    void show() { System.out.println("Parent Show"); }
}

class Child extends Parent {
    Child() { System.out.println("Child Constructor"); }
    void show() { System.out.println("Child Show"); }
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

### Q28. What is the output?

```java
class Demo {
    static int x = 10;
    public static void main(String args[]) {
        System.out.println(x);
    }
}
```

**Answer: 10**

---

### Q29. What is the output?

```java
class Counter {
    static int count = 0;
    Counter() { count++; }
}

class Test {
    public static void main(String args[]) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
        Counter c3 = new Counter();
        System.out.println(Counter.count);
    }
}
```

**Answer: 3**

---

### Q30. What is the output?

```java
class Test {
    void display(int x) { System.out.println("int"); }
    void display(double x) { System.out.println("double"); }
    void display(String x) { System.out.println("String"); }
    
    public static void main(String args[]) {
        Test t = new Test();
        t.display(10.5);
    }
}
```

**Answer: double**

---

### Q31. What is the output?

```java
class Parent {
    final int VALUE = 100;
}

class Child extends Parent {
    void show() {
        VALUE = 200;  // What happens?
    }
}
```

**Answer: Compilation Error - Cannot assign value to final variable**

---

### Q32. What is the output?

```java
class Demo {
    int a = 5;
    
    void method1() {
        int a = 10;
        System.out.println(a);      // Which 'a'?
    }
    
    void method2() {
        System.out.println(this.a);  // Which 'a'?
    }
    
    public static void main(String args[]) {
        Demo d = new Demo();
        d.method1();  // Output: 10 (local variable)
        d.method2();  // Output: 5 (instance variable)
    }
}
```

**Answer: 10, 5**

**Explanation:**
// this.a refers to instance variable
// a without this refers to local variable

---

## 🎯 Section D: Coding Questions

### Q33. Write a program to demonstrate inheritance.

```java
// Parent Class
class Employee {
    float salary = 40000;
    
    void displaySalary() {
        System.out.println("Base Salary: " + salary);
    }
}

// Child Class
class Programmer extends Employee {
    int bonus = 10000;
    
    void totalSalary() {
        float total = salary + bonus;
        System.out.println("Total Salary: " + total);
    }
}

public class InheritanceDemo {
    public static void main(String args[]) {
        Programmer p = new Programmer();
        p.displaySalary();   // From Employee: 40000
        p.totalSalary();     // From Programmer: 50000
    }
}
```

---

### Q34. Write a program demonstrating method overriding.

```java
class Bank {
    double getRateOfInterest() {
        return 0;  // Default
    }
}

class SBI extends Bank {
    @Override
    double getRateOfInterest() {
        return 8.5;
    }
}

class HDFC extends Bank {
    @Override
    double getRateOfInterest() {
        return 9.0;
    }
}

public class PolymorphismDemo {
    public static void main(String args[]) {
        Bank b;
        
        b = new SBI();
        System.out.println("SBI Rate: " + b.getRateOfInterest() + "%");
        
        b = new HDFC();
        System.out.println("HDFC Rate: " + b.getRateOfInterest() + "%");
    }
}
```

---

### Q35. Write a program demonstrating constructor overloading.

```java
class Box {
    double width, height, depth;
    
    // Constructor 1: No argument
    Box() {
        width = height = depth = 0;
    }
    
    // Constructor 2: One argument (cube)
    Box(double side) {
        width = height = depth = side;
    }
    
    // Constructor 3: Three arguments
    Box(double w, double h, double d) {
        width = w;
        height = h;
        depth = d;
    }
    
    double volume() {
        return width * height * depth;
    }
}

public class BoxDemo {
    public static void main(String args[]) {
        Box box1 = new Box();
        Box box2 = new Box(5);       // Cube with side 5
        Box box3 = new Box(3, 4, 5); // Rectangular box
        
        System.out.println("Box1 Volume: " + box1.volume());  // 0
        System.out.println("Box2 Volume: " + box2.volume());  // 125
        System.out.println("Box3 Volume: " + box3.volume());  // 60
    }
}
```

---

### Q36. Write a program demonstrating static variables.

```java
class Counter {
    int count = 0;           // Instance variable - har object ka alag
    static int staticCount = 0;  // Static - sab objects share karenge
    
    Counter() {
        count++;
        staticCount++;
    }
    
    void display() {
        System.out.println("Instance Count: " + count);
        System.out.println("Static Count: " + staticCount);
    }
}

public class StaticVariableDemo {
    public static void main(String args[]) {
        Counter c1 = new Counter();
        c1.display();
        
        Counter c2 = new Counter();
        c2.display();
        
        Counter c3 = new Counter();
        c3.display();
        
        System.out.println("\nFinal Static Count: " + Counter.staticCount);
    }
}
```

---

### Q37. Write a program demonstrating final keyword.

```java
class Constants {
    final double PI = 3.14159;
    
    void display() {
        System.out.println("PI Value: " + PI);
    }
}

public class FinalDemo {
    public static void main(String args[]) {
        Constants c = new Constants();
        c.display();
        // c.PI = 3.14;  // This would cause ERROR!
    }
}
```

---

### Q38. Write a program demonstrating nesting of methods.

```java
class Largest {
    int a, b;
    
    Largest(int x, int y) {
        a = x;
        b = y;
    }
    
    // Nested method - called by display()
    int findLargest() {
        if (a >= b)
            return a;
        else
            return b;
    }
    
    void display() {
        int ans = findLargest();  // Nesting - no object reference needed
        System.out.println("Largest value is: " + ans);
    }
    
    public static void main(String args[]) {
        Largest obj = new Largest(10, 25);
        obj.display();  // Output: Largest value is: 25
    }
}
```

---

## 📋 Quick Reference Table - Day 2

| Topic | Key Points |
|-------|-----------|
| **Inheritance** | extends keyword, single/multilevel/hierarchical |
| **Method Overloading** | Same class, different params, compile time |
| **Method Overriding** | Different class, same params, runtime |
| **Access Modifiers** | public > protected > default > private |
| **Constructors** | Same name as class, no return type |
| **Static** | Class level, shared, no 'this' |
| **Final** | Cannot change/override/extend |
| **Nesting of Method** | Same class methods call each other directly |
| **this keyword** | Refers to current object |

---

## ✅ Day 2 Self-Check

Before moving to Day 3, make sure you can answer:

- [ ] How does inheritance work in Java?
- [ ] What is the difference between overloading and overriding?
- [ ] How do access modifiers control visibility?
- [ ] What is the purpose of constructors?
- [ ] How do static members work?
- [ ] What are the uses of final keyword?
- [ ] What is nesting of methods?

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

➡️ **[Day 3: Interface & Abstract Class](../Day-3/)**

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day2.Questions)
