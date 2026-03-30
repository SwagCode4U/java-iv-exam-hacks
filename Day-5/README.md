# 📚 Day 5: Final Revision & Practice

![Java](https://img.shields.io/badge/Java-Final%20Revision-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%205-success?style=for-the-badge)
![Duration](https://img.shields.io/badge/Duration-3%20Hours-yellow?style=for-the-badge)

> *You've learned everything! Now let's master it with practice!*

---

## 🌟 Welcome to Day 5!

Congratulations on making it to Day 5! This is your final revision day. Today we'll cover everything we've learned and practice with mixed questions.

**Estimated Time:** 3 Hours  
**Prerequisites:** Days 1-4  
**Goal:** Complete revision and exam preparation

---

## 📖 Table of Contents

1. [5-Day Journey Summary](#5-day-journey-summary)
2. [Complete Question Bank](#complete-question-bank)
3. [Predict the Output Practice](#predict-the-output-practice)
4. [Important Programs](#important-programs)
5. [Exam Tips](#exam-tips)
6. [Final Checklist](#final-checklist)

---

## 🗓️ 5-Day Journey Summary

### What We Covered:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    YOUR 5-DAY JAVA OOP JOURNEY                       │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  Day 1: OOP Basics & Java Fundamentals                              │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │ ✅ What is OOP?       ✅ 6 Basic Concepts                  │   │
│  │ ✅ Java Features     ✅ Tokens & Identifiers               │   │
│  │ ✅ Data Types        ✅ Operators                          │   │
│  │ ✅ Control Statements ✅ Type Casting                       │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                              ↓                                      │
│  Day 2: Classes, Objects & Inheritance                             │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │ ✅ Classes & Objects   ✅ Constructors                     │   │
│  │ ✅ Method Overloading  ✅ Inheritance                       │   │
│  │ ✅ Method Overriding   ✅ Access Modifiers                  │   │
│  │ ✅ static & final      ✅ Polymorphism                      │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                              ↓                                      │
│  Day 3: Interface & Abstract Class                                 │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │ ✅ Abstraction         ✅ Abstract Classes                  │   │
│  │ ✅ Interfaces           ✅ Interface vs Abstract              │   │
│  │ ✅ Multiple Inheritance via Interfaces                       │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                              ↓                                      │
│  Day 4: Exception Handling                                         │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │ ✅ Exception Types      ✅ try-catch-finally                │   │
│  │ ✅ throw & throws       ✅ Custom Exceptions                │   │
│  │ ✅ Common Exceptions    ✅ Exception Hierarchy               │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                              ↓                                      │
│  Day 5: Final Revision & Practice                                 │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │ ✅ Complete Summary     ✅ Practice Questions                │   │
│  │ ✅ Exam Tips           ✅ Final Checklist                   │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 📝 Complete Question Bank

### Section 1: OOP Concepts & Java Basics

**Q1. What is OOP? Explain all 6 basic concepts.**

**Answer:**

**Object-Oriented Programming (OOP)** is a programming paradigm that organizes code around objects rather than functions.

**6 Basic Concepts:**

1. **Object & Class** - Objects are instances of classes (blueprints)
2. **Encapsulation** - Wrapping data and code into single unit
3. **Abstraction** - Hiding complexity, showing essentials
4. **Inheritance** - Acquiring properties from parent class
5. **Polymorphism** - One name, multiple forms
6. **Dynamic Binding** - Runtime decision of method call

---

**Q2. What are the features of Java?**

**Answer:**

1. **Compiled & Interpreted** - Two-stage process
2. **Platform Independent** - Bytecode + JVM
3. **Object-Oriented** - Pure OOP language
4. **Robust & Secure** - No pointers, garbage collection
5. **Distributed** - RMI for network apps
6. **Simple & Small** - No pointers, no header files
7. **Multithreaded** - Multiple tasks simultaneously
8. **High Performance** - JIT compilation
9. **Dynamic & Extensible** - Runtime class loading

---

**Q3. What is JVM and how does it achieve platform independence?**

**Answer:**

**JVM (Java Virtual Machine)** is a virtual machine that executes bytecode.

```
Source Code (.java)
        ↓ javac
Bytecode (.class)
        ↓
┌─────────────────┐
│   JVM (Windows) │
└─────────────────┘
        ↓
   Machine Code

Same bytecode runs on:
┌─────────┐  ┌─────────┐  ┌─────────┐
│ Windows │  │  Linux  │  │   Mac   │
│   JVM   │  │   JVM   │  │   JVM   │
└─────────┘  └─────────┘  └─────────┘
```

---

### Section 2: Classes, Objects & Inheritance

**Q4. What is the difference between Method Overloading and Method Overriding?**

**Answer:**

| Aspect | Overloading | Overriding |
|--------|-------------|------------|
| Definition | Same name, different params | Same name, same params |
| Class | Same class | Different classes |
| Type | Compile-time polymorphism | Runtime polymorphism |
| Parameters | Must differ | Must match |
| Return type | Can differ | Same or covariant |

---

**Q5. Explain all types of inheritance in Java.**

**Answer:**

**1. Single:** A → B (one parent, one child)  
**2. Multilevel:** A → B → C (chain)  
**3. Hierarchical:** A → B, A → C (one parent, multiple children)  
**4. Multiple:** NOT ALLOWED with classes! (use interfaces)

---

**Q6. What are access modifiers? Explain each.**

**Answer:**

| Modifier | Same Class | Same Pkg | Subclass (Diff Pkg) | Other (Diff Pkg) |
|----------|------------|----------|--------------------|--------------------|
| public | ✅ | ✅ | ✅ | ✅ |
| protected | ✅ | ✅ | ✅ | ❌ |
| default | ✅ | ✅ | ❌ | ❌ |
| private | ✅ | ❌ | ❌ | ❌ |

---

### Section 3: Interface & Abstract Class

**Q7. What is the difference between Abstract Class and Interface?**

**Answer:**

| Aspect | Abstract Class | Interface |
|--------|----------------|-----------|
| Methods | Abstract + Concrete | Only abstract (Java 7) |
| Variables | Any type | public static final |
| Constructors | ✅ Allowed | ❌ Not allowed |
| Multiple Inheritance | ❌ | ✅ |
| Use for | IS-A relationship | CAN-DO capability |

---

**Q8. What is abstraction? How is it achieved in Java?**

**Answer:**

**Abstraction** = Hiding implementation details, showing only essentials.

**Ways to achieve:**
1. **Abstract Class** (0-100% abstraction)
2. **Interface** (100% abstraction)

---

### Section 4: Exception Handling

**Q9. Explain exception handling keywords.**

**Answer:**

| Keyword | Purpose |
|---------|---------|
| try | Risky code block |
| catch | Handle exception |
| finally | Always execute |
| throw | Throw exception manually |
| throws | Declare in method signature |

---

**Q10. What is the difference between throw and throws?**

**Answer:**

| throw | throws |
|-------|--------|
| Manually throw exception | Declare exception |
| Inside method body | With method signature |
| Single exception | Multiple exceptions |
| `throw new Exception()` | `void m() throws Exception` |

---

## 🧮 Predict the Output Practice

### Set 1: Operators & Loops

**Q1.**
```java
class Test {
    public static void main(String args[]) {
        int a = 10, b = 5;
        System.out.println(a++ + ++b);
    }
}
// Answer: 16
// Explanation: 10 + 6 = 16, a becomes 11, b becomes 6
```

**Q2.**
```java
class Test {
    public static void main(String args[]) {
        for (int i = 1; i <= 3; i++) {
            if (i == 2) continue;
            System.out.print(i + " ");
        }
    }
}
// Answer: 1 3
// Explanation: 2 is skipped, 1 and 3 are printed
```

**Q3.**
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
// Answer: 1 2 3
```

**Q4.**
```java
class Test {
    public static void main(String args[]) {
        int x = 5;
        do {
            System.out.print(x + " ");
            x--;
        } while (x > 5);
    }
}
// Answer: 5
// Explanation: do-while runs at least once
```

### Set 2: Inheritance & Polymorphism

**Q5.**
```java
class Parent {
    Parent() { System.out.print("P "); }
}
class Child extends Parent {
    Child() { System.out.print("C "); }
}
class Test {
    public static void main(String args[]) {
        Child c = new Child();
    }
}
// Answer: P C
// Explanation: super() called automatically
```

**Q6.**
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
// Answer: Child
// Explanation: Runtime polymorphism
```

### Set 3: Exception Handling

**Q7.**
```java
class Test {
    public static void main(String args[]) {
        try {
            System.out.print("A ");
            int x = 10/0;
            System.out.print("B ");
        } catch (Exception e) {
            System.out.print("C ");
        } finally {
            System.out.print("D");
        }
    }
}
// Answer: A C D
```

**Q8.**
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
// Answer: 1 3
// Explanation: finally runs before return
```

---

## 💻 Important Programs

### Program 1: Bank Account with Inheritance
```java
class Account {
    protected double balance;
    protected String accountHolder;
    
    Account(String name, double balance) {
        accountHolder = name;
        this.balance = balance;
    }
    
    void display() {
        System.out.println("Holder: " + accountHolder);
        System.out.println("Balance: " + balance);
    }
}

class SavingsAccount extends Account {
    private double interestRate;
    
    SavingsAccount(String name, double balance, double rate) {
        super(name, balance);
        interestRate = rate;
    }
    
    void addInterest() {
        double interest = balance * interestRate / 100;
        balance += interest;
        System.out.println("Interest added: " + interest);
    }
}

public class BankDemo {
    public static void main(String args[]) {
        SavingsAccount sa = new SavingsAccount("Rahul", 10000, 5);
        sa.display();
        sa.addInterest();
        sa.display();
    }
}
```

### Program 2: Interface Demo
```java
interface Bank {
    void deposit(double amount);
    void withdraw(double amount);
    double getBalance();
}

class SavingsAccount implements Bank {
    private double balance;
    
    SavingsAccount(double initial) {
        balance = initial;
    }
    
    public void deposit(double amount) {
        balance += amount;
    }
    
    public void withdraw(double amount) {
        if (balance >= amount) {
            balance -= amount;
        }
    }
    
    public double getBalance() {
        return balance;
    }
}

public class InterfaceDemo {
    public static void main(String args[]) {
        Bank b = new SavingsAccount(10000);
        b.deposit(5000);
        b.withdraw(3000);
        System.out.println("Balance: " + b.getBalance());
    }
}
```

### Program 3: Custom Exception
```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String msg) {
        super(msg);
    }
}

class User {
    void register(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Must be 18+");
        }
        System.out.println("Registered successfully!");
    }
}

public class CustomExceptionDemo {
    public static void main(String args[]) {
        User u = new User();
        try {
            u.register(15);
        } catch (InvalidAgeException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

---

## 🎯 Exam Tips

### Before Exam:
```
✅ Revise all code examples
✅ Practice at least 20 programs
✅ Solve 50+ MCQs
✅ Make short notes of important points
✅ Sleep well night before
✅ Eat breakfast
```

### During Exam:
```
✅ Read questions carefully
✅ Start with easy questions
✅ Write clean, formatted code
✅ Include comments for explanation
✅ Don't leave questions unanswered
✅ Manage time wisely
```

### What to Write in Answers:

**For Theory Questions:**
```
1. Definition
2. Explanation with example
3. Diagram (if applicable)
4. Code example
5. Output (if applicable)
```

**For Coding Questions:**
```
1. Class declaration
2. Variables (proper access modifiers)
3. Constructors (if needed)
4. Methods (proper return types)
5. Main method with test cases
```

### Common Mistakes to Avoid:
```
❌ Forgetting to make methods public where required
❌ Using wrong access modifiers
❌ Not handling exceptions properly
❌ Confusing overloading with overriding
❌ Forgetting to call super() in constructors
❌ Not using @Override annotation
```

---

## ✅ Final Checklist

### Day 1 Topics:
- [ ] OOP 6 Concepts
- [ ] Java Features
- [ ] JVM & Platform Independence
- [ ] Tokens, Identifiers, Keywords
- [ ] Data Types & Variables
- [ ] Operators & Precedence
- [ ] Control Statements (if, switch, loops)
- [ ] Type Casting

### Day 2 Topics:
- [ ] Classes & Objects
- [ ] Constructors (Default, Parameterized, Overloaded)
- [ ] Method Overloading
- [ ] Inheritance (All Types)
- [ ] Method Overriding
- [ ] Access Modifiers
- [ ] static & final Keywords

### Day 3 Topics:
- [ ] Abstraction Concept
- [ ] Abstract Classes
- [ ] Interfaces
- [ ] Interface vs Abstract Class
- [ ] Multiple Inheritance via Interfaces

### Day 4 Topics:
- [ ] Exception Types
- [ ] try-catch-finally
- [ ] throw & throws
- [ ] Custom Exceptions
- [ ] Common Exceptions

---

## 🏆 You're Ready!

```
┌─────────────────────────────────────────────────────────────────────┐
│                                                                     │
│   🎉 CONGRATULATIONS! 🎉                                          │
│                                                                     │
│   You have successfully completed all 5 days of Java OOP study!      │
│                                                                     │
│   Topics Mastered:                                                  │
│   ✅ OOP Concepts                                                   │
│   ✅ Java Fundamentals                                              │
│   ✅ Classes & Objects                                              │
│   ✅ Inheritance                                                    │
│   ✅ Interface & Abstract Class                                     │
│   ✅ Exception Handling                                             │
│                                                                     │
│   You are now ready to ace your exam! 💪                           │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 💪 Final Message

> *"Education is not the learning of facts, but the training of the mind to think."*
> — Albert Einstein

Remember: Success is not final, failure is not fatal. It's the courage to continue that counts!

**You've got this! Go ace your exam! 🚀**

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Resources

- [Day 1 - OOP Basics](../Day-1/README.md)
- [Day 2 - Classes & Inheritance](../Day-2/README.md)
- [Day 3 - Interface & Abstract](../Day-3/README.md)
- [Day 4 - Exception Handling](../Day-4/README.md)

---

## 🙏 Thank You!

Thank you for following this study guide. We hope it helped you in your journey to master Java OOP!

**Best wishes for your exam! 🍀**

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day5)
