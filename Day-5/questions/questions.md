# 📚 Day 5: Final Revision & Mixed Questions - Question Bank

![Java](https://img.shields.io/badge/Java-Final%20Revision-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%205-success?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-60+-blue?style=for-the-badge)

> *Final push! You've got this! Let's ace the exam!*

---

## 🎯 Section A: Comprehensive MCQ Test (All Units)

### Q1. Java was originally called:
- A) Oak ✅
- B) Pine
- C) Java
- D) Coffee

---

### Q2. What is the full form of OOP?
- A) Object Oriented Programming ✅
- B) Object Open Programming
- C) Object Oriented Process
- D) None

---

### Q3. Which keyword is used to inherit a class?
- A) inherits
- B) extends ✅
- C) implements
- D) base

---

### Q4. Which achieves 100% abstraction?
- A) Abstract class
- B) Interface ✅
- C) Both
- D) None

---

### Q5. Which block is ALWAYS executed?
- A) try
- B) catch
- C) finally ✅
- D) throw

---

### Q6. Method Overloading is an example of:
- A) Runtime Polymorphism
- B) Compile Time Polymorphism ✅
- C) Both
- D) None

---

### Q7. Which is the most restrictive access modifier?
- A) protected
- B) default
- C) private ✅
- D) public

---

### Q8. Can we instantiate an interface?
- A) Yes, directly
- B) Yes, using new keyword
- C) No ✅
- D) Only in Java 8+

---

### Q9. Which exception occurs when dividing by zero?
- A) ArithmeticException ✅
- B) NullPointerException
- C) NumberFormatException
- D) IOException

---

### Q10. Method Overriding is an example of:
- A) Runtime Polymorphism ✅
- B) Compile Time Polymorphism
- C) Both
- D) None

---

### Q11. Which is NOT a type of inheritance in Java?
- A) Single
- B) Multiple ✅
- C) Hierarchical
- D) Multilevel

---

### Q12. What is the output of `10 % 3`?
- A) 3
- B) 1 ✅
- C) 0
- D) 3.33

---

### Q13. Which keyword throws an exception manually?
- A) throws
- B) throw ✅
- C) try
- D) catch

---

### Q14. How many interfaces can a class implement?
- A) One
- B) Two
- C) Unlimited ✅
- D) Zero

---

### Q15. Which loop executes at least once?
- A) for
- B) while
- C) do-while ✅
- D) enhanced for

---

### Q16. What is the default value of boolean?
- A) 0
- B) false ✅
- C) null
- D) true

---

### Q17. Which cannot be overridden?
- A) Instance method
- B) Static method
- C) final method ✅
- D) Private method

---

### Q18. What is the parent class of all exceptions?
- A) Exception
- B) Error
- C) Throwable ✅
- D) RuntimeException

---

### Q19. Which keyword is used to implement an interface?
- A) extends
- B) implements ✅
- C) inherit
- D) override

---

### Q20. What is the size of `int` in Java?
- A) 1 byte
- B) 2 bytes
- C) 4 bytes ✅
- D) 8 bytes

---

### Q21. Which is NOT a primitive data type?
- A) int
- B) float
- C) String ✅
- D) boolean

---

### Q22. Which is true about static methods?
- A) Can use 'this'
- B) Can use 'super'
- C) Can be called without object ✅
- D) Must override

---

### Q23. What is bytecode?
- A) Machine code
- B) Source code
- C) Intermediate code ✅
- D) Assembly code

---

### Q24. Which is a checked exception?
- A) ArithmeticException
- B) NullPointerException
- C) IOException ✅
- D) ArrayIndexOutOfBoundsException

---

### Q25. What is the default constructor?
- A) Constructor with one parameter
- B) Constructor with no parameters ✅
- C) Static constructor
- D) Private constructor

---

## 🎯 Section B: Long Answer Questions (Mixed)

### Q26. What is OOP? Explain all 6 basic concepts with real-life examples.

**Answer:**

**OOP (Object Oriented Programming):**
OOP ek software design methodology hai jo real-world entities ko classes aur objects ke form mein model karti hai.

**Six Basic Concepts:**

1. **Object and Class:** Objects are instances, classes are blueprints
2. **Encapsulation:** Wrapping data and code into single unit
3. **Abstraction:** Hiding complexity, showing essentials
4. **Inheritance:** Child acquiring parent properties
5. **Polymorphism:** One name, multiple forms
6. **Dynamic Binding:** Runtime method resolution

---

### Q27. What is the difference between Method Overloading and Method Overriding?

**Answer:**

| Aspect | Overloading | Overriding |
|--------|-------------|-----------|
| Definition | Same name, different params | Same name, same params |
| Class | Same class | Different classes |
| Type | Compile Time Polymorphism | Runtime Polymorphism |
| Parameters | Must differ | Must match |

---

### Q28. Explain all Access Modifiers.

**Answer:**

| Modifier | Same Class | Same Package | Subclass (Diff Pkg) | Other (Diff Pkg) |
|----------|------------|--------------|---------------------|-------------------|
| public | ✅ | ✅ | ✅ | ✅ |
| protected | ✅ | ✅ | ✅ | ❌ |
| default | ✅ | ✅ | ❌ | ❌ |
| private | ✅ | ❌ | ❌ | ❌ |

---

### Q29. What is Interface vs Abstract Class?

**Answer:**

| Aspect | Abstract Class | Interface |
|--------|---------------|-----------|
| Methods | Abstract + Concrete | Only abstract (Java 7) |
| Variables | Any type | public static final |
| Constructor | ✅ Allowed | ❌ Not allowed |
| Multiple Inheritance | ❌ | ✅ Supported |

---

### Q30. Explain Exception Handling keywords.

**Answer:**

| Keyword | Purpose |
|---------|---------|
| try | Suspect code block |
| catch | Handle exception |
| finally | Always execute |
| throw | Manually throw |
| throws | Declare in method signature |

---

### Q31. What is Inheritance? Explain all types.

**Answer:**

**Types:**
1. **Single:** A → B
2. **Multilevel:** A → B → C
3. **Hierarchical:** A → B, A → C
4. **Multiple:** A, B → C (NOT ALLOWED with classes!)

---

### Q32. What is the difference between throw and throws?

**Answer:**

| throw | throws |
|-------|--------|
| Manually throw exception | Declare in method signature |
| Inside method body | With method declaration |
| Single exception | Multiple exceptions |

---

### Q33. What is Abstraction? How is it achieved in Java?

**Answer:**

Abstraction = Hiding implementation, showing essentials.

**Two Ways:**
1. Abstract Class (0-100%)
2. Interface (100%)

---

### Q34. Explain all Java Features.

**Answer:**

1. Compiled & Interpreted
2. Platform Independent (Bytecode + JVM)
3. Object-Oriented
4. Robust & Secure
5. Distributed
6. Simple & Small
7. Multithreaded
8. High Performance
9. Dynamic & Extensible

---

### Q35. What are Constructors? Explain types and overloading.

**Answer:**

**Constructor:** Special method for object initialization.

**Types:**
1. Default (no-arg)
2. Parameterized

**Constructor Overloading:** Multiple constructors with different parameters.

---

## 🎯 Section C: Predict the Output (All Units)

### Q36. What is the output?

```java
class Test {
    public static void main(String args[]) {
        int a = 10, b = 5;
        System.out.println(a++ + ++b);
    }
}
```

**Answer: 16**

**Explanation:**
// a++ = 10, ++b = 6, 10 + 6 = 16

---

### Q37. What is the output?

```java
class Parent {
    void show() { System.out.println("Parent"); }
}
class Child extends Parent {
    void show() { System.out.println("Child"); }
}
class Test {
    public static void main(String args[]) {
        Parent p = new Child();
        p.show();
    }
}
```

**Answer: Child**

---

### Q38. What is the output?

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

---

### Q39. What is the output?

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

**Answer: Base Derived**

---

### Q40. What is the output?

```java
interface A {
    void show();
}
class Demo implements A {
    public void show() {
        System.out.println("Show method");
    }
}
class Test {
    public static void main(String args[]) {
        A a = new Demo();
        a.show();
    }
}
```

**Answer: Show method**

---

### Q41. What is the output?

```java
class Test {
    static int count = 0;
    Test() { count++; }
    public static void main(String args[]) {
        Test t1 = new Test();
        Test t2 = new Test();
        System.out.println(Test.count);
    }
}
```

**Answer: 2**

---

### Q42. What is the output?

```java
for (int i = 1; i <= 3; i++) {
    if (i == 2) continue;
    System.out.print(i + " ");
}
```

**Answer: 1 3**

---

### Q43. What is the output?

```java
class Test {
    static void show() {
        try {
            System.out.print("1 ");
            return;
        } catch (Exception e) {
            System.out.print("2 ");
        } finally {
            System.out.print("3 ");
        }
    }
    public static void main(String args[]) {
        show();
    }
}
```

**Answer: 1 3**

---

### Q44. What is the output?

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

**Answer: int**

---

### Q45. What is the output?

```java
abstract class Shape {
    abstract void draw();
}
class Circle extends Shape {
    void draw() {
        System.out.println("Drawing Circle");
    }
}
class Test {
    public static void main(String args[]) {
        Shape s = new Circle();
        s.draw();
    }
}
```

**Answer: Drawing Circle**

---

## 🎯 Section D: Coding Questions (Mixed)

### Q46. Write a program demonstrating inheritance and method overriding.

```java
class Bank {
    double getRate() { return 0; }
}

class SBI extends Bank {
    @Override
    double getRate() { return 8.5; }
}

class HDFC extends Bank {
    @Override
    double getRate() { return 9.0; }
}

public class BankDemo {
    public static void main(String args[]) {
        Bank b;
        b = new SBI();
        System.out.println("SBI: " + b.getRate() + "%");
        b = new HDFC();
        System.out.println("HDFC: " + b.getRate() + "%");
    }
}
```

---

### Q47. Write a program demonstrating interface.

```java
interface Drawable {
    void draw();
}

class Rectangle implements Drawable {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

class Circle implements Drawable {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

public class InterfaceDemo {
    public static void main(String args[]) {
        Drawable d = new Rectangle();
        d.draw();
        d = new Circle();
        d.draw();
    }
}
```

---

### Q48. Write a program demonstrating exception handling.

```java
public class ExceptionDemo {
    public static void main(String args[]) {
        try {
            int[] arr = new int[3];
            arr[5] = 100;
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array error: " + e.getMessage());
        } finally {
            System.out.println("Finally executed");
        }
    }
}
```

---

### Q49. Write a program demonstrating constructor overloading.

```java
class Student {
    int id;
    String name;
    int age;
    
    Student() {
        id = 0;
        name = "Unknown";
        age = 0;
    }
    
    Student(int i, String n) {
        id = i;
        name = n;
    }
    
    Student(int i, String n, int a) {
        id = i;
        name = n;
        age = a;
    }
    
    void display() {
        System.out.println(id + " " + name + " " + age);
    }
    
    public static void main(String args[]) {
        Student s1 = new Student();
        Student s2 = new Student(101, "Rahul");
        Student s3 = new Student(102, "Priya", 20);
        
        s1.display();
        s2.display();
        s3.display();
    }
}
```

---

### Q50. Write a program demonstrating static members.

```java
class Counter {
    static int count = 0;
    
    Counter() {
        count++;
    }
    
    static void display() {
        System.out.println("Count: " + count);
    }
}

public class StaticDemo {
    public static void main(String args[]) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
        Counter c3 = new Counter();
        
        Counter.display();  // 3
    }
}
```

---

## 🎯 Section E: Complete Programs for Practice

### Q51. Complete Bank Account System with Inheritance & Exception Handling

```java
// Abstract Account class
abstract class Account {
    protected double balance;
    protected String accountHolder;
    
    Account(String name, double balance) {
        accountHolder = name;
        this.balance = balance;
    }
    
    abstract void display();
    
    void showBalance() {
        System.out.println("Balance: " + balance);
    }
}

// Savings Account
class SavingsAccount extends Account {
    private double interestRate = 5.0;
    
    SavingsAccount(String name, double balance) {
        super(name, balance);
    }
    
    void addInterest() {
        double interest = balance * interestRate / 100;
        balance += interest;
        System.out.println("Interest added: " + interest);
    }
    
    void display() {
        System.out.println("Savings Account - " + accountHolder);
        System.out.println("Balance: " + balance);
    }
}

// Custom Exception
class InsufficientFundsException extends Exception {
    InsufficientFundsException(String msg) {
        super(msg);
    }
}

// Main Class
public class BankSystem {
    static void withdraw(Account acc, double amount) throws InsufficientFundsException {
        if (amount > acc.balance) {
            throw new InsufficientFundsException("Not enough funds!");
        }
        acc.balance -= amount;
        System.out.println("Withdrawn: " + amount);
    }
    
    public static void main(String args[]) {
        SavingsAccount sa = new SavingsAccount("Rahul", 10000);
        
        sa.display();
        sa.addInterest();
        sa.showBalance();
        
        try {
            withdraw(sa, 3000);
            sa.showBalance();
            withdraw(sa, 20000);  // Will throw exception
        } catch (InsufficientFundsException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

---

### Q52. Interface-based Shape Calculator

```java
// Interface
interface Shape {
    double calculateArea();
    void display();
}

// Circle implementation
class Circle implements Shape {
    double radius;
    
    Circle(double r) {
        radius = r;
    }
    
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
    
    public void display() {
        System.out.println("Circle - Radius: " + radius);
        System.out.println("Area: " + calculateArea());
    }
}

// Rectangle implementation
class Rectangle implements Shape {
    double width, height;
    
    Rectangle(double w, double h) {
        width = w;
        height = h;
    }
    
    public double calculateArea() {
        return width * height;
    }
    
    public void display() {
        System.out.println("Rectangle - " + width + "x" + height);
        System.out.println("Area: " + calculateArea());
    }
}

// Main class
public class ShapeCalculator {
    public static void main(String args[]) {
        Shape[] shapes = {
            new Circle(5),
            new Rectangle(4, 6),
            new Circle(3),
            new Rectangle(2, 8)
        };
        
        double totalArea = 0;
        for (Shape s : shapes) {
            s.display();
            totalArea += s.calculateArea();
            System.out.println();
        }
        
        System.out.println("Total Area: " + totalArea);
    }
}
```

---

## 📋 Quick Reference Tables

### Data Types

| Type | Size | Range |
|------|------|-------|
| byte | 1 B | -128 to 127 |
| short | 2 B | -32K to 32K |
| int | 4 B | -2B to 2B |
| long | 8 B | Very large |
| float | 4 B | Decimal |
| double | 8 B | Large decimal |
| char | 2 B | Unicode |
| boolean | 1 B | true/false |

### Access Modifiers

| Modifier | Same Class | Same Pkg | Subclass (Diff) | Other (Diff) |
|----------|------------|----------|-----------------|---------------|
| public | ✅ | ✅ | ✅ | ✅ |
| protected | ✅ | ✅ | ✅ | ❌ |
| default | ✅ | ✅ | ❌ | ❌ |
| private | ✅ | ❌ | ❌ | ❌ |

### Exception Hierarchy

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

### OOP Concepts

| Concept | Description |
|--------|-------------|
| Class | Blueprint/Template |
| Object | Instance of class |
| Encapsulation | Data + Methods in one unit |
| Abstraction | Hide complexity |
| Inheritance | Parent-child relationship |
| Polymorphism | One name, many forms |

---

## ✅ Final Checklist

Before the exam:

- [ ] OOP 6 concepts clear?
- [ ] Java Features remembered?
- [ ] Inheritance types understood?
- [ ] Method overloading vs overriding clear?
- [ ] Access modifiers remembered?
- [ ] Interface vs Abstract class differences?
- [ ] Exception handling keywords?
- [ ] throw vs throws difference?

---

## 🎓 Exam Day Tips

```
✅ Sleep well night before
✅ Eat breakfast
✅ Read questions carefully
✅ Start with easy questions
✅ Write clean, formatted code
✅ Include comments
✅ Manage time wisely
✅ Don't panic!
```

---

## 💪 Final Message

> *"You've come a long way! From OOP basics to exception handling, you've learned it all. Trust yourself and your preparation. You are ready to ace this exam!"*

**Best of luck! 🍀**

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day5.Questions)
