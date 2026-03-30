# 📚 Day 4: Exception Handling - Question Bank

![Java](https://img.shields.io/badge/Java-Exception%20Handling-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%204-success?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-40+-blue?style=for-the-badge)

> *Learning to handle errors gracefully like a pro!*

---

## 🎯 Section A: Multiple Choice Questions (MCQs)

### Q1. What is the parent class of all exceptions in Java?
- A) Exception
- B) Error
- C) Throwable ✅
- D) RuntimeException

> **Hinglish:** Throwable, Exception aur Error dono ka parent hai. Exception user-generated errors ka parent hai.

---

### Q2. Which is a checked exception?
- A) ArithmeticException
- B) NullPointerException
- C) IOException ✅
- D) ArrayIndexOutOfBoundsException

> **Hinglish:** Checked exceptions compile-time pe check hote hain. Compiler enforce karta hai handle karo.
> // IOException, SQLException checked hain

---

### Q3. Which block is ALWAYS executed?
- A) try
- B) catch
- C) finally ✅
- D) throw

> **Hinglish:** **finally** block hamesha execute hota hai, chaahe exception aaye ya nahi, try success ho ya fail.

---

### Q4. What happens if exception is not handled?
- A) Program continues
- B) Program terminates abnormally ✅
- C) Program restarts
- D) No effect

> **Hinglish:** Agar exception handle na ho toh program crash ho jata hai (abnormal termination). Stack trace print hota hai.

---

### Q5. Which keyword is used to explicitly throw an exception?
- A) try
- B) catch
- C) throw ✅
- D) throws

> **Hinglish:** **throw** se manually exception throw karte hain.
> // throw new ArithmeticException("Custom message");

---

### Q6. Which keyword declares that a method may throw exceptions?
- A) throw
- B) throws ✅
- C) try
- D) catch

> **Hinglish:** **throws** method signature mein likhte hain ki yeh method exception throw kar sakta hai.
> // void readFile() throws IOException

---

### Q7. Which exception occurs when dividing by zero?
- A) NumberFormatException
- B) ArithmeticException ✅
- C) NullPointerException
- D) IOException

> **Hinglish:** ArithmeticException divide by zero waqt aata hai.
> // int x = 10/0; → ArithmeticException

---

### Q8. Which exception occurs when accessing null object?
- A) ArithmeticException
- B) NullPointerException ✅
- C) ArrayIndexOutOfBoundsException
- D) IOException

> **Hinglish:** NullPointerException tab aata hai jab aap null object pe method call karte ho.
> // String s = null; s.length(); → NullPointerException

---

### Q9. Which exception occurs when array size exceeded?
- A) ArithmeticException
- B) NullPointerException
- C) ArrayIndexOutOfBoundsException ✅
- D) NumberFormatException

> **Hinglish:** ArrayIndexOutOfBoundsException tab aata hai jab aap array ke bound se bahar access karte ho.
> // int[] arr = new int[5]; arr[10] = 100; → ArrayIndexOutOfBoundsException

---

### Q10. Can we have multiple catch blocks?
- A) No
- B) Yes, in order ✅
- C) Only two
- D) Only with finally

> **Hinglish:** Haa, multiple catch blocks ho sakte hain lekin order important hai - child exception pehle, parent baad mein.

---

### Q11. Is finally block always executed?
- A) No
- B) Yes, always ✅
- C) Only if no exception
- D) Only if exception occurs

> **Hinglish:** finally hamesha execute hota hai, chaahe exception aaye ya nahi, try success ho ya fail.

---

### Q12. Which exception is thrown when format is wrong?
- A) ArithmeticException
- B) NullPointerException
- C) NumberFormatException ✅
- D) IOException

> **Hinglish:** NumberFormatException tab aata hai jab string ko number mein convert karte waqt format galat ho.
> // int i = Integer.parseInt("abc"); → NumberFormatException

---

### Q13. What is the output?

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
- A) A B C D
- B) A C D ✅
- C) A B D
- D) A C

> **Hinglish:** A print hoga, phir exception aayega (division by zero), toh B skip hoga, C print hoga catch mein, finally bhi chalega.

---

### Q14. Which is an unchecked exception?
- A) IOException
- B) SQLException
- C) ArithmeticException ✅
- D) ClassNotFoundException

> **Hinglish:** Unchecked exceptions RuntimeException ke children hain - compile-time pe check nahi hote.
> // ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException unchecked hain

---

### Q15. try block can exist without catch?
- A) No
- B) Yes, if finally is there ✅
- C) Only in Java 7
- D) Only with multiple catches

> **Hinglish:** try-finally allowed hai, catch optional hai (Java 7+).
> // try { } finally { }

---

### Q16. Can we catch multiple exceptions in one catch?
- A) No
- B) Yes, using pipe (|) operator (Java 7+) ✅
- C) Only two
- D) Only checked exceptions

> **Hinglish:** Java 7 se aap ek catch mein multiple exceptions catch kar sakte ho.
> // catch (IOException | SQLException e) { }

---

### Q17. Which is NOT an exception keyword?
- A) try
- B) catch
- C) throw
- D) raises ✅

> **Hinglish:** Java mein **raises** keyword nahi hai. Valid keywords hain: try, catch, finally, throw, throws.

---

### Q18. What is the output?

```java
try {
    throw new ArithmeticException("Custom Error");
} catch (ArithmeticException e) {
    System.out.println("Caught: " + e.getMessage());
}
```
- A) Error
- B) No output
- C) Caught: Custom Error ✅
- D) Exception

> **Hinglish:** ArithmeticException throw kiya aur catch bhi kar liya. getMessage() se custom message print hoga.

---

### Q19. Which is the root class of Exception hierarchy?
- A) Exception
- B) RuntimeException
- C) Throwable ✅
- D) Error

> **Hinglish:** Throwable, Exception aur Error dono ka parent hai. Throwable se Exception aur Error inherit hote hain.

---

### Q20. Can we throw an exception manually?
- A) No
- B) Yes, using throw ✅
- C) Only in catch block
- D) Only in finally block

> **Hinglish:** Haa, **throw** keyword se manually exception throw kar sakte ho.
> // throw new Exception("Custom message");

---

## 🎯 Section B: Long Answer Questions

### Q21. What is Exception Handling? Explain with try-catch-finally.

**Answer:**

**What is Exception?**
Exception ek unwanted event hai jo program ki normal flow ko disrupt karta hai. Yeh error ya abnormal condition hai jo runtime pe aata hai.

**Exception Handling:**
Exception handling ek mechanism hai jisme hum exceptions ko gracefully handle karte hain taaki program crash na ho.

**Exception Handling Keywords:**

| Keyword | Purpose |
|---------|---------|
| **try** | Suspect code yahan likhte hain jo exception de sakta hai |
| **catch** | Exception handle karte hain |
| **finally** | Cleanup code - hamesha execute hota hai |
| **throw** | Manually exception throw karte hain |
| **throws** | Method declare karta hai ki yeh exception throw kar sakta hai |

**try-catch-finally Syntax:**
```java
try {
    // Suspect code - jo exception de sakta hai
    int result = 10 / 0;  // Exception yahan generate hoga
} catch (ExceptionType e) {
    // Exception handle karo
    System.out.println("Error occurred: " + e.getMessage());
} finally {
    // Cleanup code - hamesha execute hoga
    System.out.println("This always runs");
}
```

**Complete Example:**
```java
public class ExceptionDemo {
    public static void main(String args[]) {
        try {
            System.out.println("Inside try block");
            int data = 100 / 0;  // ArithmeticException
            System.out.println("This will not print");
        } catch (ArithmeticException e) {
            System.out.println("Caught ArithmeticException!");
            System.out.println("Message: " + e.getMessage());
        } finally {
            System.out.println("Finally block - always executed");
        }
        System.out.println("Program continues after exception handling");
    }
}
```

**Output:**
```
Inside try block
Caught ArithmeticException!
Message: / by zero
Finally block - always executed
Program continues after exception handling
```

**Multiple Catch Blocks:**
```java
try {
    int[] arr = new int[5];
    arr[10] = 100;  // ArrayIndexOutOfBoundsException
} catch (ArithmeticException e) {
    System.out.println("Arithmetic Exception");
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array Index Exception");
} catch (Exception e) {  // Parent exception - last mein rakhna
    System.out.println("Generic Exception");
}
```

---

### Q22. Explain types of exceptions with examples.

**Answer:**

**Exception Hierarchy:**
```
                    Throwable
                         │
           ┌──────────────┴──────────────┐
           │                              │
         Error                          Exception
    (Irrecoverable)                  (Recoverable)
           │                              │
    ┌──────┴──────┐            ┌─────────┴─────────┐
    │             │            │                   │
 OutOfMemory  StackOverflow  Checked             Unchecked
    │             │            │                   │
  VirtualMachine  Assertion   IOException        ArithmeticException
   Error         Error    SQLException       NullPointerException
                                │          ArrayIndexOutOfBounds
                           ClassNotFound      NumberFormatException
                              Exception
```

**1. Checked Exceptions (Compile-time):**
```java
// Compile-time pe check hote hain
// Compiler enforce karta hai handle karo

// IOException - file handling
import java.io.*;

class CheckedDemo {
    void readFile() throws IOException {
        FileReader f = new FileReader("test.txt");  // Checked
        f.close();
    }
}
```

**2. Unchecked Exceptions (Runtime):**
```java
// Runtime pe aate hain - compiler doesn't force handling

// ArithmeticException - divide by zero
int result = 10 / 0;  // java.lang.ArithmeticException

// NullPointerException - null object pe operation
String s = null;
s.length();  // java.lang.NullPointerException

// ArrayIndexOutOfBoundsException - array bounds se bahar
int[] arr = new int[5];
arr[10] = 100;  // java.lang.ArrayIndexOutOfBoundsException

// NumberFormatException - galat format
String str = "abc";
int num = Integer.parseInt(str);  // java.lang.NumberFormatException
```

**3. Errors (Irrecoverable):**
```java
// Program crash ho jayega, handle nahi kar sakte
// OutOfMemoryError, StackOverflowError, etc.

// Example: Infinite recursion
void recursive() {
    recursive();  // StackOverflowError - system crash
}
```

---

### Q23. Explain throw vs throws with examples.

**Answer:**

**throw (Singular - Throw an exception):**
```java
// Syntax: throw new ExceptionType("message");
// Manually exception throw karna

public class ThrowDemo {
    static void validate(int age) {
        if (age < 18) {
            // Manually throw exception
            throw new ArithmeticException("Not eligible to vote. Age must be 18+");
        } else {
            System.out.println("Eligible to vote. Welcome!");
        }
    }
    
    public static void main(String args[]) {
        validate(15);  // Will throw exception
    }
}
```

**Output:**
```
Exception in thread "main" java.lang.ArithmeticException: Not eligible to vote. Age must be 18+
    at ThrowDemo.validate(ThrowDemo.java:8)
    at ThrowDemo.main(ThrowDemo.java:16)
```

**throws (Plural - Declare exceptions):**
```java
// Syntax: returnType methodName() throws ExceptionType
// Method signature mein declare karna ki yeh exception throw kar sakta hai

import java.io.*;

class ThrowsDemo {
    // Method declare karta hai ki yeh IOException throw kar sakta hai
    void readFile() throws IOException {
        FileReader f = new FileReader("test.txt");
        f.close();
    }
    
    public static void main(String args[]) {
        try {
            ThrowsDemo t = new ThrowsDemo();
            t.readFile();  // Must handle or declare
        } catch (IOException e) {
            System.out.println("File not found: " + e.getMessage());
        }
    }
}
```

**Difference:**

| throw | throws |
|-------|--------|
| Used to **throw** exception explicitly | Used to **declare** exception in method signature |
| Syntax: `throw new Exception()` | Syntax: `method() throws Exception` |
| Inside method body | With method declaration |
| Single exception | Multiple exceptions |
| Used to throw custom exceptions | Used to handle checked exceptions |

**Combined Example:**
```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String msg) {
        super(msg);
    }
}

class User {
    static void register(int age) throws InvalidAgeException {
        if (age < 18) {
            // throw - manually throw
            throw new InvalidAgeException("Age must be 18+");
        }
        System.out.println("Registration successful");
    }
}

public class ThrowThrowsDemo {
    public static void main(String args[]) {
        try {
            // throws - declare that method may throw
            User.register(15);
        } catch (InvalidAgeException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

---

### Q24. Explain common exception scenarios with examples.

**Answer:**

**Scenario 1: ArithmeticException (Divide by Zero)**
```java
public class ArithmeticDemo {
    public static void main(String args[]) {
        try {
            int a = 50;
            int b = 0;
            int c = a / b;  // ArithmeticException
            System.out.println("Result: " + c);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero!");
            System.out.println("Error: " + e);
        }
    }
}
```

**Scenario 2: NullPointerException**
```java
public class NullPointerDemo {
    public static void main(String args[]) {
        try {
            String s = null;
            int length = s.length();  // NullPointerException
            System.out.println("Length: " + length);
        } catch (NullPointerException e) {
            System.out.println("Object is null! Cannot perform operation.");
            System.out.println("Error: " + e);
        }
    }
}
```

**Scenario 3: ArrayIndexOutOfBoundsException**
```java
public class ArrayBoundDemo {
    public static void main(String args[]) {
        try {
            int[] arr = new int[5];  // Size 5, indices 0-4
            arr[10] = 100;  // ArrayIndexOutOfBoundsException
            System.out.println("Value: " + arr[10]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index out of bounds!");
            System.out.println("Valid indices: 0 to " + (arr.length - 1));
        }
    }
}
```

**Scenario 4: NumberFormatException**
```java
public class NumberFormatDemo {
    public static void main(String args[]) {
        try {
            String str = "abc";
            int num = Integer.parseInt(str);  // NumberFormatException
            System.out.println("Number: " + num);
        } catch (NumberFormatException e) {
            System.out.println("Invalid number format!");
            System.out.println("Cannot convert '" + str + "' to number.");
        }
    }
}
```

---

## 🎯 Section C: Predict the Output

### Q25. What is the output?

```java
public class Test {
    static void show() {
        try {
            System.out.print("1 ");
            return;  // try se bahar jaa rahe ho
        } catch (Exception e) {
            System.out.print("2 ");
        } finally {
            System.out.print("3 ");  // Will still execute!
        }
        System.out.print("4 ");
    }
    
    public static void main(String args[]) {
        show();
        System.out.print("5");
    }
}
```

**Answer: 1 3 5**

**Explanation:**
// return statement se turant bahar jaana hai
// lekin finally block hamesha execute hota hai
// 4 kabhi print nahi hoga kyunki return se bahar ho gaye

---

### Q26. What is the output?

```java
public class Test {
    public static void main(String args[]) {
        try {
            System.out.print("A ");
            int x = 10 / 2;  // No exception
            System.out.print("B ");
        } catch (Exception e) {
            System.out.print("C ");
        } finally {
            System.out.print("D ");
        }
        System.out.print("E");
    }
}
```

**Answer: A B D E**

**Explanation:**
// No exception, toh try block complete chalega
// catch skip, finally execute, baaki code continue

---

### Q27. What is the output?

```java
public class Test {
    public static void main(String args[]) {
        try {
            throw new RuntimeException("Error");
        } catch (Exception e) {
            System.out.print("Catch ");
        } finally {
            System.out.print("Finally ");
        }
        System.out.print("End");
    }
}
```

**Answer: Catch Finally End**

---

### Q28. What is the output?

```java
public class Test {
    public static void main(String args[]) {
        try {
            int[] arr = new int[2];
            arr[0] = 10;
            arr[1] = 20;
            System.out.println(arr[2]);  // Exception here
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.print("Array ");
        } catch (RuntimeException e) {
            System.out.print("Runtime ");
        } catch (Exception e) {
            System.out.print("Exception ");
        }
        System.out.print("Done");
    }
}
```

**Answer: Array Done**

**Explanation:**
// ArrayIndexOutOfBoundsException pehle match hoga (child)
// Baaki catches skip honge

---

### Q29. What is the output?

```java
public class Test {
    public static void main(String args[]) {
        try {
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.print("Caught ");
        } finally {
            System.out.print("Finally ");
        }
    }
}
```

**Answer: Caught Finally**

---

### Q30. What happens?

```java
public class Test {
    public static void main(String args[]) {
        try {
            int x = 10 / 0;
        } catch (Exception e) {
            System.out.print("Exception ");
            return;
        } finally {
            System.out.print("Finally ");
        }
    }
}
```

**Answer: Exception Finally**

**Explanation:**
// catch mein return hai, lekin finally turant pehle execute hoga
// Baad mein return hoga

---

## 🎯 Section D: Coding Questions

### Q31. Write a program demonstrating exception handling.

```java
import java.util.Scanner;

class BankAccount {
    private double balance;
    
    BankAccount(double initialBalance) {
        balance = initialBalance;
    }
    
    void deposit(double amount) {
        if (amount <= 0) {
            try {
                throw new ArithmeticException("Invalid deposit amount!");
            } catch (ArithmeticException e) {
                System.out.println("Error: " + e.getMessage());
                return;
            }
        }
        balance += amount;
        System.out.println("Deposited: " + amount);
        System.out.println("New Balance: " + balance);
    }
    
    void withdraw(double amount) {
        if (amount <= 0) {
            try {
                throw new ArithmeticException("Invalid withdrawal amount!");
            } catch (ArithmeticException e) {
                System.out.println("Error: " + e.getMessage());
                return;
            }
        }
        
        if (amount > balance) {
            try {
                throw new ArithmeticException("Insufficient balance!");
            } catch (ArithmeticException e) {
                System.out.println("Error: " + e.getMessage());
                return;
            }
        }
        
        balance -= amount;
        System.out.println("Withdrawn: " + amount);
        System.out.println("Remaining Balance: " + balance);
    }
}

public class BankDemo {
    public static void main(String args[]) {
        BankAccount account = new BankAccount(10000);
        
        try {
            System.out.println("--- Transaction 1: Valid Withdraw ---");
            account.withdraw(3000);
            
            System.out.println("\n--- Transaction 2: Invalid Deposit ---");
            account.deposit(-1000);  // Will throw exception
            
        } catch (Exception e) {
            System.out.println("Unhandled Exception: " + e);
        } finally {
            System.out.println("\n=== Transaction Complete ===");
        }
    }
}
```

---

### Q32. Write a program to handle multiple exceptions.

```java
public class MultiExceptionDemo {
    public static void main(String args[]) {
        int[] numbers = {10, 20, 30, 40, 50};
        
        try {
            System.out.println("Attempting operations...");
            
            System.out.println("Array access: " + numbers[2]);
            System.out.println("Division: " + (10 / 0));  // Exception
            
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Exception: " + e.getMessage());
            
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception: " + e.getMessage());
            
        } catch (Exception e) {
            System.out.println("Generic Exception: " + e.getMessage());
            
        } finally {
            System.out.println("Finally: This always executes");
        }
        
        System.out.println("Program continues after handling exceptions");
    }
}
```

---

### Q33. Write a program to demonstrate custom exception.

```java
// Custom Exception Class
class InvalidScoreException extends Exception {
    InvalidScoreException(String msg) {
        super(msg);
    }
}

// Student Class
class Student {
    String name;
    int score;
    
    Student(String n, int s) {
        name = n;
        score = s;
    }
    
    void validate() throws InvalidScoreException {
        if (score < 0 || score > 100) {
            throw new InvalidScoreException("Score must be between 0 and 100!");
        }
        System.out.println(name + " - Score: " + score + " - VALID");
    }
}

// Main Class
public class CustomExceptionDemo {
    public static void main(String args[]) {
        Student[] students = {
            new Student("Rahul", 85),
            new Student("Priya", 105),   // Invalid
            new Student("Amit", -10)      // Invalid
        };
        
        for (Student s : students) {
            try {
                s.validate();
            } catch (InvalidScoreException e) {
                System.out.println(s.name + " - ERROR: " + e.getMessage());
            }
        }
    }
}
```

---

### Q34. Write a program demonstrating throws keyword.

```java
import java.io.*;

class FileHandler {
    // Declares that this method may throw IOException
    void readFile(String filename) throws IOException {
        FileReader fr = new FileReader(filename);
        BufferedReader br = new BufferedReader(fr);
        
        String line;
        while ((line = br.readLine()) != null) {
            System.out.println(line);
        }
        br.close();
    }
}

public class ThrowsDemo {
    public static void main(String args[]) {
        FileHandler fh = new FileHandler();
        
        try {
            // Must handle or declare - we declared with throws
            fh.readFile("test.txt");
            
        } catch (IOException e) {
            System.out.println("File Error: " + e.getMessage());
            System.out.println("Please check if file exists!");
        }
    }
}
```

---

### Q35. Write a program demonstrating try-with-resources.

```java
import java.io.*;

public class TryWithResourcesDemo {
    public static void main(String args[]) {
        // try-with-resources - automatically closes the resource
        try (FileReader fr = new FileReader("test.txt");
             BufferedReader br = new BufferedReader(fr)) {
            
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            
        } catch (IOException e) {
            System.out.println("Error reading file: " + e.getMessage());
        }
        
        System.out.println("File processed successfully!");
    }
}
```

---

## 📋 Quick Reference Table - Day 4

| Keyword | Purpose | Example |
|---------|---------|---------|
| try | Code that may throw exception | `try { }` |
| catch | Handle the exception | `catch (Exception e) { }` |
| finally | Always execute | `finally { }` |
| throw | Throw exception manually | `throw new Exception();` |
| throws | Declare in method signature | `void m() throws Exception` |

| Exception | When Occurs | Example |
|-----------|------------|---------|
| ArithmeticException | Division by zero | `10/0` |
| NullPointerException | Null object access | `null.length()` |
| ArrayIndexOutOfBoundsException | Invalid array index | `arr[10]` when size=5 |
| NumberFormatException | Invalid number format | `Integer.parseInt("abc")` |

| Type | Checked at | Example |
|------|-----------|---------|
| Checked | Compile-time | IOException, SQLException |
| Unchecked | Runtime | ArithmeticException, NullPointerException |
| Error | Never recoverable | OutOfMemoryError, StackOverflowError |

---

## ✅ Day 4 Self-Check

Before moving to Day 5, make sure you can answer:

- [ ] What is the difference between throw and throws?
- [ ] How do try-catch-finally work together?
- [ ] What is the difference between checked and unchecked exceptions?
- [ ] How do you create a custom exception?
- [ ] What is the exception hierarchy?

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

➡️ **[Day 5: Final Revision & Mixed Questions](../Day-5/)**

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day4.Questions)
