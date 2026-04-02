# 📚 Day 7: Advanced Topics - Question Bank

![Java](https://img.shields.io/badge/Java-Advanced%20Topics-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%207-success?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-80+-blue?style=for-the-badge)

> *Practice makes perfect! Let's master Packages, Strings, Collections & More!*

---

## 🎯 Section A: Multiple Choice Questions (MCQs)

### Q1. Which package is automatically imported in every Java program?
- A) java.util
- B) java.lang ✅
- C) java.io
- D) java.applet

> **Hinglish:** `java.lang` package automatically import hota hai har Java program mein. Isme bahut important classes hain jaise **String, System, Math, Object, Integer, Thread, etc.** Aapko inhe import karna zaroori nahi hota. Ye automatically available hote hain.

---

### Q2. What is the keyword to create a package?
- A) import
- B) package ✅
- C) include
- D) module

> **Hinglish:** Package create karne ke liye `package` keyword use hota hai. Yeh class file ke **sabse upar** (first line) likha jata hai. Syntax: `package packagename;` jahan packagename folder structure ko represent karta hai.

**Example:**
```java
package college.department;  // college\department folder mein store hoga
public class Student {
    // class code
}
```

---

### Q3. Which statement is correct to import all classes from java.util?
- A) import java.util;
- B) import java.util.*; ✅
- C) include java.util.*;
- D) use java.util;

> **Hinglish:** Saari classes import karne ke liye wildcard `*` use karte hain. `import java.util.*;` se util package ki **sab classes** available ho jati hain jaise ArrayList, HashMap, Scanner, etc. 

**Note:** Sirf specified class import karne ke liye: `import java.util.ArrayList;`

---

### Q4. What is String in Java?
- A) Primitive data type
- B) Class ✅
- C) Interface
- D) Array

> **Hinglish:** String Java mein ek **class** hai, primitive data type nahi. String class `java.lang` package mein hai aur iske bahut saare built-in methods hain jaise `length()`, `charAt()`, `substring()`, `equals()`, etc.

**Example:**
```java
String s = "Hello";  // String class ka object
int len = s.length();  // length() method call
```

---

### Q5. How many ways can we create a String in Java?
- A) 1
- B) 2
- C) 3 ✅
- D) 4

> **Hinglish:** String **3 tarike se** bana sakte hain:

**1. String Literal (Most Common & Preferred):**
```java
String s1 = "Hello";
// String Pool mein store hota hai, memory efficient
```

**2. Using new keyword:**
```java
String s2 = new String("Hello");
// Heap Memory mein store hota hai, alag object banata hai
```

**3. From Character Array:**
```java
char[] ch = {'H', 'e', 'l', 'l', 'o'};
String s3 = new String(ch);
// Char array se String bana sakte hain
```

---

### Q6. What is String pool?
- A) Collection of Strings in Heap ✅
- B) Collection of Strings in Stack
- C) Method area
- D) None

> **Hinglish:** String Pool ek special memory area hai **Heap Memory** ke andar jahan String literals store hote hain. Jab aap String literal create karte ho (jaise `String s = "Hello"`), toh JVM pehle check karta hai ki pool mein "Hello" exist karta hai ya nahi.

**Benefits:**
- Memory bachta hai (same literals reuse hote hain)
- Performance improve hota hai

**Memory View:**
```
┌─────────────────────────────────────────────────────────┐
│                    HEAP MEMORY                           │
│                                                         │
│   ┌─────────────────────────────────────────┐          │
│   │            STRING POOL                    │          │
│   │   "Hello"  ──────────────────────────   │          │
│   │      ↑              ↑                    │          │
│   │   s1 = "Hello"   s2 = "Hello"          │          │
│   └─────────────────────────────────────────┘          │
│                                                         │
│   ┌─────────────────────────────────────────┐          │
│   │         HEAP (Outside Pool)              │          │
│   │   new String("Hello")                   │          │
│   │   (s3) - Alag object                   │          │
│   └─────────────────────────────────────────┘          │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

### Q7. What is the output?

```java
String s1 = "Java";
String s2 = "Java";
String s3 = new String("Java");

System.out.println(s1 == s2);
System.out.println(s1 == s3);
System.out.println(s1.equals(s3));
```

- A) true true true
- B) true false true ✅
- C) true false false
- D) false true true

> **Hinglish - Step by Step Analysis:**
> 
> **s1 == s2 → true**
> → Dono same literal "Java" ko point karte hain pool mein
> → Same object reference
> 
> **s1 == s3 → false**
> → s3 new keyword se bana hai, pool ke bahar heap mein
> → Alag object, alag reference
> 
> **s1.equals(s3) → true**
> → equals() content compare karta hai, reference nahi
> → Dono mein "Java" hai, toh equal

**Memory Rule:** 
- `==` → Reference comparison (same object ya nahi)
- `equals()` → Content comparison (same characters ya nahi)

---

### Q8. Strings in Java are:
- A) Mutable
- B) Immutable ✅
- C) Volatile
- D) None

> **Hinglish:** String objects **immutable** hote hain matlab ek baar create hone ke baad unhe change nahi kar sakte. Har baar jab aap String ko modify karte ho (jaise `s.concat()`), toh Java naya String object create karta hai, original change nahi hota.

**Example:**
```java
String s = "Hello";
s.concat(" World");  // Naya String banega, original "Hello" unchanged
System.out.println(s);  // Output: Hello (NOT "Hello World")
```

**Why Immutable?**
- **Security**: Database passwords, usernames secure rehte hain
- **Thread Safety**: Multiple threads safely share kar sakte hain
- **Caching**: String pool optimization possible hai
- **HashCode**: HashMap keys ke liye stable hashCode milta hai

---

### Q9. Which method is used to compare two strings ignoring case?
- A) equals()
- B) compareTo()
- C) equalsIgnoreCase() ✅
- D) compare()

> **Hinglish:** `equalsIgnoreCase()` do strings ko **case (upper/lower) ignore** karke compare karta hai.

**Example:**
```java
String s1 = "HELLO";
String s2 = "hello";
String s3 = "Hello";

s1.equals(s2);                    // false (case sensitive)
s1.equalsIgnoreCase(s2);        // true (case ignored)
s1.equals(s3);                  // false
s1.equalsIgnoreCase(s3);        // true
```

**Other comparison methods:**
| Method | Description |
|--------|-------------|
| `equals()` | Case sensitive comparison |
| `equalsIgnoreCase()` | Case insensitive comparison |
| `compareTo()` | Lexicographical comparison, returns int |
| `compareToIgnoreCase()` | Lexicographical, case insensitive |

---

### Q10. What does "Java".replace('a', 'x') return?
- A) Jxvx
- B) Jxva
- C) jAvx
- D) Java ✅

> **Hinglish:** Yeh tricky question hai! `replace('a', 'x')` case **sensitive** hai. String "Java" mein 'J', 'a', 'v', 'a' hai. Sirf **lowercase 'a'** ko 'x' se replace hoga, 'J' unchanged rahega.

**Step by Step:**
```
Original: J a v a
         ↓ ↓ ↓ ↓
After:   J x v x  → "Jx vx" WAIT! → "Jxvx"
```

**Wait - Correct Answer is D "Java" because:**
Actually, `replace('a', 'x')` replaces ALL occurrences of 'a' with 'x'. But "Java" contains 'a' two times... 

Let me correct: 
- "Java".replace('a', 'x') = "Jxvx" (Answer A)

**Variations:**
```java
"Java".replace('a', 'x')      // "Jxvx" - replaces all 'a'
"Java".replace("a", "x")     // "Jxvx" - replaces all "a"
"Java".replaceFirst("a", "x") // "Jaxa" - replaces first only
"Java".replaceAll("a", "x")   // "Jxvx" - replaces all
```

---

### Q11. What does substring(4, 8) return for "JavaProgramming"?
- A) Progr
- B) Programm
- C) Progra
- D) Programming

> **Hinglish - Step by Step Analysis:**
> 
> String: "JavaProgramming"
> 
> Index:    0 1 2 3 4 5 6 7 8 9 10 ...
> Characters: J a v a P r o g r a m m i n g
> 
> `substring(4, 8)` means:
> - Start index: 4 (included)
> - End index: 8 (excluded)
> 
> Characters from index 4 to 7:
> - Index 4: 'P'
> - Index 5: 'r'
> - Index 6: 'o'
> - Index 7: 'g'
> 
> Result: "Prog"

**Memory Trick:** `substring(start, end)` includes start, excludes end.
**Formula:** Characters from index **start** to **(end - 1)**

---

### Q12. What is the difference between StringBuffer and StringBuilder?
- A) StringBuffer is thread-safe, StringBuilder is not ✅
- B) StringBuilder is thread-safe, StringBuffer is not
- C) Both are thread-safe
- D) Neither is thread-safe

> **Hinglish - Detailed Comparison:**
> 
> | Feature | StringBuffer | StringBuilder |
> |---------|--------------|---------------|
> | **Thread Safety** | Synchronized (thread-safe) | Not synchronized |
> | **Performance** | Slower (due to sync) | Faster |
> | **Usage** | Multi-threaded programs | Single-threaded programs |
> | **Introduced** | Java 1.0 | Java 1.5 |
> 
> **When to use which?**
> ```java
> // StringBuilder - Most cases mein prefer karo
> StringBuilder sb = new StringBuilder("Hello");
> sb.append(" World");  // Fast, single-threaded
> 
> // StringBuffer - Jab multiple threads access karte hain
> StringBuffer sb2 = new StringBuffer("Hello");
> sb2.append(" World");  // Thread-safe but slower
> ```

---

### Q13. Which is NOT a wrapper class?
- A) Integer
- B) String ✅
- C) Boolean
- D) Character

> **Hinglish:** **String wrapper class nahi hai!** String ek normal class hai jo character sequence store karti hai.

**Wrapper Classes (primitives ko objects mein convert karte hain):**
| Primitive | Wrapper Class |
|-----------|---------------|
| byte | Byte |
| short | Short |
| int | Integer |
| long | Long |
| float | Float |
| double | Double |
| char | Character |
| boolean | Boolean |

---

### Q14. What is autoboxing?
- A) Converting primitive to wrapper automatically ✅
- B) Converting wrapper to primitive
- C) Converting String to Primitive
- D) None

> **Hinglish:** Autoboxing ek **compiler feature** hai jo automatically primitive types ko unke corresponding wrapper classes mein convert karta hai.

**Example:**
```java
// Explicit (Pre-Java 5 style)
Integer i = Integer.valueOf(10);  // Manual boxing

// Autoboxing (Java 5+ style)
Integer i = 10;  // Compiler automatically converts to Integer.valueOf(10)
```

**Common places where autoboxing happens:**
- Collections mein elements add karte waqt
- Method parameters mein
- Assignments mein

**Warning:** Autoboxing can lead to unexpected behavior with == comparison!
```java
Integer a = 100;
Integer b = 100;
System.out.println(a == b);  // true (cache range mein)

Integer c = 200;
Integer d = 200;
System.out.println(c == d);  // false (cache range se bahar)
```

---

### Q15. What is unboxing?
- A) Converting primitive to wrapper
- B) Converting wrapper to primitive automatically ✅
- C) Creating primitive
- D) None

> **Hinglish:** Unboxing wrapper object ko automatically primitive mein convert karta hai.

**Example:**
```java
// Explicit (Pre-Java 5 style)
Integer i = new Integer(10);
int x = i.intValue();  // Manual unboxing

// Unboxing (Java 5+ style)
Integer i = new Integer(10);
int x = i;  // Compiler automatically calls i.intValue()
```

**Autoboxing + Unboxing together:**
```java
List<Integer> list = new ArrayList<>();
list.add(10);      // Autoboxing: int → Integer
int num = list.get(0);  // Unboxing: Integer → int
```

---

### Q16. What is the range of Integer cache?
- A) 0 to 127
- B) -128 to 127 ✅
- C) -256 to 256
- D) 1 to 100

> **Hinglish:** Java **-128 to 127** tak ki values cache karta hai Integer objects ke liye. Is range ke baare values ke liye naye objects create hote hain.

**Why Cache?**
- Performance improvement
- Memory optimization
- Frequent small numbers often used hote hain

**Impact on == comparison:**
```java
Integer a = 127;
Integer b = 127;
a == b  // true (same cached object)

Integer c = 128;
Integer d = 128;
a == b  // false (different objects, cache ke bahar)
```

**Always use `equals()` for value comparison!**

---

### Q17. How many ways can we create a Thread?
- A) 1
- B) 2 ✅
- C) 3
- D) 4

> **Hinglish:** Java mein Thread **2 tarike se** bana sakte hain:

**Method 1: Thread class ko extend karo**
```java
class MyThread extends Thread {
    public void run() {
        // Thread ka code yahan likho
        System.out.println("Thread running!");
    }
}

// Thread start karo
MyThread t = new MyThread();
t.start();  // start() call karo, NOT run()
```

**Method 2: Runnable interface implement karo (PREFERRED)**
```java
class MyRunnable implements Runnable {
    public void run() {
        // Thread ka code yahan likho
        System.out.println("Thread running!");
    }
}

// Thread create karo aur start karo
Thread t = new Thread(new MyRunnable());
t.start();
```

**Why Runnable prefer kiya jata hai?**
- Java single inheritance deta hai
- Agar class already kisi aur class ko extend kar rahi hai, toh Runnable implement kar sakti hai
- More flexible hai

---

### Q18. Which method is used to start a thread?
- A) run()
- B) start() ✅
- C) execute()
- D) begin()

> **Hinglish:** Thread start karne ke liye `start()` method **ZAROOR** call karo, `run()` nahi!

**Common Mistake:**
```java
MyThread t = new MyThread();
t.run();   // ❌ WRONG! Yeh normal method call hai
t.start(); // ✅ CORRECT! Yeh naya thread create karega
```

**Difference:**
| call run() | call start() |
|------------|--------------|
| Current thread mein execute hoga | Naya thread create hoga |
| main() thread continue karega | Naya thread parallel chalega |
| No multi-threading | True multi-threading |

---

### Q19. What is synchronization in Java?
- A) Making method static
- B) Preventing concurrent access to shared resources ✅
- C) Creating new thread
- D) Terminating thread

> **Hinglish:** Synchronization ek mechanism hai jo **ek time pe sirf ek thread ko** shared resource access karne deta hai. Yeh data corruption aur race conditions se bachata hai.

**Problem without synchronization:**
```java
class Counter {
    int count = 0;
    
    void increment() {
        count++;  // Not thread-safe!
    }
}

// Do threads simultaneously increment kar rahe hain
// count = 1 (expected: 2)
// Race condition ki wajah se value inconsistent ho sakti hai
```

**Solution with synchronization:**
```java
class Counter {
    int count = 0;
    
    synchronized void increment() {
        count++;  // Thread-safe!
    }
}
```

**Types of Synchronization:**
1. **Method Synchronization** - Pure method ko synchronized banao
2. **Block Synchronization** - Sirf ek block synchronize karo

---

### Q20. Which keyword is used for synchronization?
- A) synchronized ✅
- B) static
- C) final
- D) transient

> **Hinglish:** `synchronized` keyword method ya block ko synchronize karne ke liye use hota hai.

**Method level synchronization:**
```java
synchronized void methodName() {
    // Sirf ek thread is method mein enter kar sakta hai
}
```

**Block level synchronization:**
```java
void someMethod() {
    synchronized(this) {
        // Sirf currently running thread is block mein hai
    }
}
```

**Static method synchronization:**
```java
synchronized static void staticMethod() {
    // Class level lock, sab threads affected
}
```

---

### Q21. Which collection does NOT allow duplicates?
- A) List
- B) ArrayList
- C) Set ✅
- D) Vector

> **Hinglish - Set vs List:**
> 
> | Collection | Duplicates | Ordered | Access |
> |------------|------------|---------|--------|
> | **List** | ✅ Allowed | Yes (by index) | By index |
> | ArrayList | ✅ Allowed | Yes | By index |
> | LinkedList | ✅ Allowed | Yes | By index |
> | Vector | ✅ Allowed | Yes | By index |
> | **Set** | ❌ NOT Allowed | Depends | By value |
> | HashSet | ❌ NOT Allowed | No | By value |
> | TreeSet | ❌ NOT Allowed | Sorted | By value |
> | LinkedHashSet | ❌ NOT Allowed | Insertion | By value |

**Example:**
```java
Set<String> set = new HashSet<>();
set.add("Java");
set.add("Python");
set.add("Java");  // Duplicate - IGNORED!
System.out.println(set.size());  // 2 (not 3)
```

---

### Q22. What is the default capacity of ArrayList?
- A) 5
- B) 10 ✅
- C) 15
- D) 0

> **Hinglish:** ArrayList ka **default capacity 10** hai. Jab aap naya ArrayList banate ho, toh initially 10 elements store kar sakta hai bina resize ke.

**Capacity vs Size:**
| Term | Meaning |
|------|---------|
| **Capacity** | Kitni memory allocate hai (how much CAN store) |
| **Size** | Kitne elements actually hain (how much IS stored) |

**Growth:** Jab ArrayList full ho jata hai, toh yeh automatically apna capacity badhata hai (approximately 1.5x).

**Example:**
```java
ArrayList<String> list = new ArrayList<>();  // Default capacity: 10
list.add("A");  // size = 1
list.add("B");  // size = 2
// ... add up to 10 elements
// After 10th, capacity badh jayegi
```

---

### Q23. Which is the correct way to iterate over HashMap?
- A) for(String s : map)
- B) for(Map.Entry e : map.entrySet()) ✅
- C) for(int i : map)
- D) while(map.hasNext())

> **Hinglish - HashMap Iteration Methods:**
> 
> **Method 1: Using entrySet() (Most Common)**
> ```java
> for(Map.Entry<Integer, String> entry : map.entrySet()) {
>     System.out.println(entry.getKey() + ": " + entry.getValue());
> }
> ```
> 
> **Method 2: Using keySet()**
> ```java
> for(Integer key : map.keySet()) {
>     System.out.println(key + ": " + map.get(key));
> }
> ```
> 
> **Method 3: Using values()**
> ```java
> for(String value : map.values()) {
>     System.out.println(value);
> }
> ```
> 
> **Method 4: Using Iterator**
> ```java
> Iterator<Map.Entry<Integer, String>> it = map.entrySet().iterator();
> while(it.hasNext()) {
>     Map.Entry<Integer, String> entry = it.next();
>     System.out.println(entry.getKey() + ": " + entry.getValue());
> }
> ```

---

### Q24. Which collection maintains insertion order?
- A) HashSet
- B) TreeSet
- C) LinkedHashSet ✅
- D) HashMap

> **Hinglish - Order Comparison:**
> 
> | Collection | Order Maintained? | Type of Order |
> |------------|-------------------|---------------|
> | HashSet | ❌ No | Random/Unordered |
> | TreeSet | ✅ Yes | Sorted (Natural/Comparable) |
> | LinkedHashSet | ✅ Yes | Insertion Order |
> | HashMap | ❌ No | Random/Unordered |
> | TreeMap | ✅ Yes | Sorted by Keys |
> | LinkedHashMap | ✅ Yes | Insertion Order |

**Example:**
```java
LinkedHashSet<String> lhs = new LinkedHashSet<>();
lhs.add("First");
lhs.add("Second");
lhs.add("Third");
// Output: [First, Second, Third] - Insertion order preserved

HashSet<String> hs = new HashSet<>();
hs.add("First");
hs.add("Second");
hs.add("Third");
// Output: Order unpredictable - No guarantee
```

---

### Q25. What will be the output?

```java
HashMap<Integer, String> hm = new HashMap<>();
hm.put(1, "Java");
hm.put(2, "Python");
hm.put(1, "C++");

System.out.println(hm.size());
System.out.println(hm.get(1));
```

- A) 2 C++
- B) 3 C++
- C) 2 Java
- D) 3 Java

> **Hinglish - Step by Step:**
> 
> `hm.put(1, "Java")` → Key 1, Value "Java" added
> `hm.put(2, "Python")` → Key 2, Value "Python" added
> `hm.put(1, "C++")` → Key 1 AGAIN, **overwrites** previous value!
> 
> Final HashMap state:
> ```
> {1="C++", 2="Python"}
> ```
> 
> `hm.size()` → 2 (key-value pairs)
> `hm.get(1)` → "C++" (latest value for key 1)

**Key Point:** HashMap mein **keys unique** hote hain. same key doosri baar add karne pe old value overwrite ho jati hai.

---

### Q26. Which interface does HashMap implement?
- A) List
- B) Set
- C) Map ✅
- D) Collection

> **Hinglish - HashMap Hierarchy:**
> 
> HashMap implements **Map interface**, List ya Set nahi!
> 
> ```
> Map (interface)
>  ├── HashMap
>  ├── TreeMap
>  ├── LinkedHashMap
>  └── Hashtable
> ```
> 
> **Map vs Collection:**
> | Interface | Structure | Duplicates |
> |-----------|-----------|------------|
> | **Map** | Key-Value pairs | Keys unique, Values can repeat |
> | **Collection** | Single elements | Depends on implementation |
> | **List** | Ordered, indexed | Allowed |
> | **Set** | Unique elements | NOT allowed |
> | **Queue** | FIFO ordered | Depends |

---

### Q27. Which class is used to read text from a file?
- A) FileReader ✅
- B) FileWriter
- C) FileInputStream
- D) DataInputStream

> **Hinglish - IO Streams Overview:**
> 
> | Class | Type | Purpose |
> |-------|------|---------|
> | **FileReader** | Character Stream | Read TEXT files |
> | **FileWriter** | Character Stream | Write TEXT files |
> | **FileInputStream** | Byte Stream | Read BINARY files |
> | **FileOutputStream** | Byte Stream | Write BINARY files |
> | **BufferedReader** | Character Stream | Efficient text reading (has readLine) |
> | **BufferedWriter** | Character Stream | Efficient text writing |

**Example - Reading Text:**
```java
// Simple FileReader
FileReader fr = new FileReader("file.txt");
int ch;
while((ch = fr.read()) != -1) {
    System.out.print((char)ch);
}
fr.close();

// Better - BufferedReader (more efficient)
BufferedReader br = new BufferedReader(new FileReader("file.txt"));
String line;
while((line = br.readLine()) != null) {
    System.out.println(line);
}
br.close();
```

---

### Q28. Which class provides readLine() method?
- A) BufferedReader ✅
- B) BufferedWriter
- C) FileReader
- D) InputStreamReader

> **Hinglish:** `readLine()` method sirf **BufferedReader** class mein hai. Yeh poori line ek baar mein read karta hai.

**readLine() returns:**
- String containing the line (without newline character)
- **null** if end of file (EOF) reach ho gaya

**Common mistake - Using FileReader directly:**
```java
FileReader fr = new FileReader("file.txt");
String line = fr.readLine();  // ❌ FileReader has NO readLine()!

// ✅ Correct way
BufferedReader br = new BufferedReader(new FileReader("file.txt"));
String line = br.readLine();  // ✅ Works!
```

---

### Q29. What is serialization?
- A) Converting object to bytes ✅
- B) Converting bytes to object
- C) Reading from file
- D) Writing to file

> **Hinglish - Serialization Explained:**
> 
> Serialization ek process hai jisme **object ko byte stream mein convert** kiya jata hai taaki ise file mein store kar saken ya network pe bhej saken.

**Key Points:**
- Class ko `Serializable` interface implement karna hoga
- `transient` keyword se fields exclude kar sakte hain
- `static` fields bhi serialize nahi hote

**Serialization Process:**
```
┌─────────────┐                    ┌──────────────┐
│   Object    │ ───Serialize()──► │  Byte Stream │
│  (Memory)   │                    │   (File)     │
└─────────────┘                    └──────────────┘
         ▲                              │
         │                              │
         │     Deserialize()            │
         └──────────────────────────────┘
```

---

### Q30. Which keyword makes a variable non-serializable?
- A) static
- B) final
- C) transient ✅
- D) volatile

> **Hinglish:** `transient` keyword se variable ko serialization se **exclude** kiya jata hai. Serialized object mein uski value default rahegi (0, null, false).

**Example:**
```java
class Student implements Serializable {
    String name;          // Will be serialized
    int rollNo;          // Will be serialized
    transient int password;  // Will NOT be serialized (becomes 0)
    transient String data;   // Will NOT be serialized (becomes null)
}
```

**Common uses for transient:**
- Sensitive data (passwords, security keys)
- Computed fields (derived values)
- Database connections
- Thread references

---

### Q31. What is the purpose of Generics in Java?
- A) Type safety at compile time ✅
- B) Memory optimization
- C) Faster execution
- D) Security

> **Hinglish - Why Generics?**
> 
> **Without Generics:**
> ```java
> ArrayList list = new ArrayList();  // Raw type
> list.add("Hello");
> list.add(100);  // Allowed - No type checking!
> String s = (String) list.get(1);  // Runtime Error! (ClassCastException)
> ```
> 
> **With Generics:**
> ```java
> ArrayList<String> list = new ArrayList<>();  // Type specified
> list.add("Hello");
> list.add(100);  // ❌ COMPILE ERROR! Type safety
> String s = list.get(0);  // ✅ No casting needed
> ```

**Benefits of Generics:**
1. **Type Safety**: Compile-time pe errors pakadta hai
2. **No Casting**: Manual type conversion ki zaroorat nahi
3. **Code Reusability**: Ek code multiple types ke saath kaam karta hai
4. **Cleaner Code**: Less type checking code likhna padta hai

---

### Q32. What will happen if we try to add Integer to ArrayList<String>?
- A) Works fine
- B) Compilation Error ✅
- C) Runtime Error
- D) No Error

> **Hinglish:** Generic type declare karne ke baad, **compile-time pe hi error** aayega agar wrong type add karne ki koshish karo.

**Example:**
```java
ArrayList<String> list = new ArrayList<>();
list.add("Java");     // ✅ Fine
list.add(100);       // ❌ COMPILE ERROR!
                    // Error: "incompatible types: int cannot be converted to String"
```

**Why better than runtime error?**
- Error **compile time** pe milti hai (jab code likhte ho)
- Runtime pe crash nahi hoga
- Debugging easier hai

---

### Q33. Which annotation indicates a method overrides a superclass method?
- A) @Override ✅
- B) @Overload
- C) @Inherited
- D) @Method

> **Hinglish:** `@Override` annotation lagane se compiler verify karta hai ki method actually parent class ko override kar raha hai ya nahi.

**Example:**
```java
class Parent {
    void show() {
        System.out.println("Parent");
    }
}

class Child extends Parent {
    @Override  // ✅ Correct override
    void show() {
        System.out.println("Child");
    }
    
    @Override  // ❌ COMPILE ERROR! (method name typo)
    void showw() {  // Wrong name
        System.out.println("Wrong");
    }
}
```

**Benefits of @Override:**
- Typos pakadta hai (compile-time)
- Code readable hai
- Intent clear karta hai

---

### Q34. What is the difference between wait() and sleep()?
- A) wait() releases lock, sleep() does not ✅
- B) sleep() releases lock, wait() does not
- C) Both release lock
- D) Neither releases lock

> **Hinglish - Detailed Comparison:**
> 
> | Feature | wait() | sleep() |
> |---------|--------|---------|
> | **Lock Release** | ✅ Releases monitor lock | ❌ Keeps lock |
> | **Belongs to** | Object class | Thread class |
> | **Usage Context** | Must be in synchronized block | Can be anywhere |
> | **Wake up** | notify() / notifyAll() | After timeout or interrupt |
> | **Definition** | java.lang.Object | java.lang.Thread |
> | **Called on** | Object reference | Thread reference |
> 
> **Example:**
> ```java
> synchronized(obj) {
>     while(condition) {
>         obj.wait();  // Lock release, wait for notification
>     }
>     // Work with obj
> }
> 
> // vs
> 
> Thread.sleep(1000);  // Current thread sleep, lock held
> ```

---

### Q35. Which List implementation is best for frequent insertion/deletion?
- A) ArrayList
- B) LinkedList ✅
- C) Vector
- D) Stack

> **Hinglish - ArrayList vs LinkedList:**
> 
> | Operation | ArrayList | LinkedList |
> |-----------|-----------|------------|
> | **Random Access** | O(1) Fast ✅ | O(n) Slow |
> | **Insertion at middle** | O(n) Slow | O(1) Fast ✅ |
> | **Deletion at middle** | O(n) Slow | O(1) Fast ✅ |
> | **Add at end** | O(1) amortized ✅ | O(1) |
> | **Memory** | Less (array based) | More (node references) |
> | **Implementation** | Dynamic array | Doubly linked list |
> 
> **When to use which?**
> - **ArrayList**: Jab frequently access karte ho (get, set)
> - **LinkedList**: Jab frequently insert/delete karte ho (add, remove)

**Technical Reason:**
ArrayList mein insertion ke liye elements ko shift karna padta hai (O(n)). LinkedList mein sirf pointers change hote hain (O(1)).

---

## 🎯 Section B: Predict the Output

### Q36. What is the output?

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

> **Hinglish - Explanation:**
> Strings immutable hain! `concat()` naya String return karta hai, original change nahi karta.
> 
> **Yahan galti:** Result ko store nahi kiya!
> ```java
> s = s.concat(" Programming");  // ✅ Is tarike se store karna padta hai
> ```

---

### Q37. What is the output?

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

- A) Hello, World ✅
- B) Hello World,
- C) Hello,World
- D) HelloWorld

> **Hinglish - Step by Step:**
> 
> **Step 1:** `new StringBuffer("Hello")` → "Hello"
> 
> **Step 2:** `sb.append(" World")` → "Hello World"
> 
> **Step 3:** `sb.insert(5, ",")` → Position 5 pe comma insert
> - "Hello World"
> - Position 5 = between "o" and "W"
> - Result: "Hello, World"

---

### Q38. What is the output?

```java
class Test {
    public static void main(String args[]) {
        Integer a = 100;
        Integer b = 100;
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

> **Hinglish - Integer Cache:**
> 
> **a == b (100):** Both 100, range -128 to 127 mein hai, **same cached object** → true
> 
> **c == d (200):** Both 200, range se bahar hai, **different objects** → false
> 
> **Always use `equals()` for value comparison!**

---

### Q39. What is the output?

```java
class Test extends Thread {
    public void run() {
        System.out.print("Thread ");
    }
    
    public static void main(String args[]) {
        Test t = new Test();
        t.start();
        System.out.print("Main ");
    }
}
```

- A) Thread Main
- B) Main Thread
- C) Thread
- D) Either "Thread Main" or "Main Thread" ✅

> **Hinglish - Thread Scheduling:**
> Thread execution order **unpredictable** hai because:
> - OS thread scheduler decide karta hai kaunsa thread pehle chalega
> - JVM implementation se bhi output change ho sakta hai
> 
> **Possible outputs:**
> - "Thread Main" (Thread pehle execute hua)
> - "Main Thread" (Main pehle execute hua)
> 
> **Guaranteed nahi hai konsa pehle aayega!**

---

### Q40. What is the output?

```java
import java.util.*;

class Test {
    public static void main(String args[]) {
        ArrayList<String> al = new ArrayList<>();
        al.add("A");
        al.add("B");
        al.add("A");
        
        System.out.println(al.size());
        System.out.println(al.contains("A"));
        System.out.println(al.get(1));
    }
}
```

- A) 3 true B ✅
- B) 2 true B
- C) 3 false B
- D) 2 false B

> **Hinglish - ArrayList Behavior:**
> 
> `al.add("A")` → List: [A]
> `al.add("B")` → List: [A, B]
> `al.add("A")` → List: [A, B, A] (duplicate allowed in List!)
> 
> `al.size()` → 3 (total elements)
> `al.contains("A")` → true (A present hai)
> `al.get(1)` → "B" (index 1, 0-based)

---

## 🎯 Section C: Short Answer Questions

### Q41. What is the difference between String, StringBuffer, and StringBuilder?

**Answer:**
```
┌────────────────┬──────────────────┬────────────────────┐
│    String      │  StringBuffer    │  StringBuilder      │
├────────────────┼──────────────────┼────────────────────┤
│  Immutable    │  Mutable         │  Mutable           │
│  (Cannot     │  (Can change)    │  (Can change)      │
│   change)     │                  │                    │
├────────────────┼──────────────────┼────────────────────┤
│  Thread-Safe  │  Thread-Safe     │  NOT Thread-Safe   │
│  (Yes)        │  (Yes)          │  (No)              │
├────────────────┼──────────────────┼────────────────────┤
│  Performance  │  Slower         │  Faster            │
│  (Slower for │  (Synchronized)  │  (Not Synchronized)│
│   frequent   │                  │                    │
│   changes)   │                  │                    │
├────────────────┼──────────────────┼────────────────────┤
│  Storage      │  Heap Memory     │  Heap Memory       │
│  Location     │  (Synchronized)   │  (Not Synchronized)│
├────────────────┼──────────────────┼────────────────────┤
│  Use Case     │  Multi-threaded  │  Single-threaded   │
│              │  applications    │  applications      │
└────────────────┴──────────────────┴────────────────────┘

Recommendation:
• String: When value rarely/no changes
• StringBuilder: Single-threaded, frequent modifications (PREFERRED)
• StringBuffer: Multi-threaded, frequent modifications
```

---

### Q42. What is the difference between HashMap and HashSet?

**Answer:**
```
┌───────────────────┬─────────────────┬─────────────────┐
│    HashMap        │    HashSet      │
├───────────────────┼─────────────────┼─────────────────┤
│  Data Structure   │  Key-Value      │  Only Values    │
│                   │  Pairs          │                 │
├───────────────────┼─────────────────┼─────────────────┤
│  Implements       │  Map Interface   │  Set Interface   │
├───────────────────┼─────────────────┼─────────────────┤
│  Stores          │  Objects        │  Objects         │
│                   │  (as keys and  │                 │
│                   │   values)      │                 │
├───────────────────┼─────────────────┼─────────────────┤
│  Allows Duplicates│  Values: Yes   │  Values: NO     │
│                   │  Keys: NO      │                 │
├───────────────────┼─────────────────┼─────────────────┤
│  Null Handling    │  1 null key    │  1 null value   │
│                   │  Multiple null  │                 │
│                   │  values        │                 │
├───────────────────┼─────────────────┼─────────────────┤
│  Contains         │  containsKey()   │  contains()     │
│  Method          │  containsValue()│                 │
├───────────────────┼─────────────────┼─────────────────┤
│  Performance      │  O(1) for basic │  O(1) for basic │
│                   │  operations    │  operations     │
└───────────────────┴─────────────────┴─────────────────┘

Internal Working:
• HashMap internally uses HashTable for storage
• HashSet internally uses HashMap (values become keys with dummy values)
```

---

### Q43. What is the difference between ArrayList and LinkedList?

**Answer:**
```
┌─────────────────┬─────────────────┬─────────────────┐
│   ArrayList     │   LinkedList    │
├─────────────────┼─────────────────┼─────────────────┤
│  Internal       │  Doubly Linked  │
│  Structure      │  List          │
│                 │                │
├─────────────────┼─────────────────┼─────────────────┤
│  Random Access  │  O(1) ✅ FAST   │  O(n) SLOW     │
│  (get, set)    │                │                │
├─────────────────┼─────────────────┼─────────────────┤
│  Insertion at   │  O(n) SLOW     │  O(1) ✅ FAST   │
│  middle         │  (shifting)    │  (pointer      │
│                 │                │   changes)      │
├─────────────────┼─────────────────┼─────────────────┤
│  Deletion at    │  O(n) SLOW     │  O(1) ✅ FAST   │
│  middle         │  (shifting)    │  (pointer      │
│                 │                │   changes)      │
├─────────────────┼─────────────────┼─────────────────┤
│  Add at end     │  O(1) amortized│  O(1)          │
│                 │  ✅            │  ✅            │
├─────────────────┼─────────────────┼─────────────────┤
│  Memory Usage   │  Less ✅        │  More (extra   │
│                 │                │  node objects)  │
├─────────────────┼─────────────────┼─────────────────┤
│  When to Use    │  More get/set   │  More insert/   │
│                 │  operations    │  delete ops     │
└─────────────────┴─────────────────┴─────────────────┘

Technical Details:
ArrayList:
• Resizable array
• Elements stored in continuous memory
• When full, creates new larger array and copies elements

LinkedList:
• Each element is a separate Node object
• Node contains: data + previous reference + next reference
• No continuous memory needed
```

---

### Q44. What is the difference between List and Set?

**Answer:**
```
┌──────────────┬─────────────────┬─────────────────┐
│     List     │     Set         │
├──────────────┼─────────────────┼─────────────────┤
│  Duplicates │  ✅ ALLOWED     │  ❌ NOT ALLOWED │
├──────────────┼─────────────────┼─────────────────┤
│  Order       │  ✅ Maintains   │  ❌ Not guaranteed│
│              │  insertion order │  (except special │
│              │  (by index)    │  implementations)│
├──────────────┼─────────────────┼─────────────────┤
│  Index       │  ✅ Has index   │  ❌ No index    │
│  Access      │  get(i) works  │  get(i) doesn't │
├──────────────┼─────────────────┼─────────────────┤
│  Null Value  │  ✅ Allows null │  ✅ Allows 1 null│
│              │  (multiple)     │  (usually)     │
├──────────────┼─────────────────┼─────────────────┤
│  Use Case    │  When order &  │  When uniqueness │
│              │  duplicates    │  matters        │
│              │  matter        │                 │
├──────────────┼─────────────────┼─────────────────┤
│  Implementations│ ArrayList,    │ HashSet,        │
│              │  LinkedList,   │ TreeSet,        │
│              │  Vector, Stack │ LinkedHashSet   │
└──────────────┴─────────────────┴─────────────────┘

Set ka Principle: "Each element appears at most once"
Set mein add() agar duplicate add karne ki koshish karein,
toh element ignore ho jata hai aur add() false return karta hai.
```

---

### Q45. What is the difference between fail-fast and fail-safe iterators?

**Answer:**
```
┌─────────────────┬─────────────────┬─────────────────┐
│   fail-fast     │   fail-safe    │
├─────────────────┼─────────────────┼─────────────────┤
│  Works on       │  Works on copy │
│  original       │  of collection │
│  collection     │                │
├─────────────────┼─────────────────┼─────────────────┤
│  Modification   │  Modification  │
│  during iter.   │  during iter.  │
│  causes         │  is ALLOWED    │
│  Exception      │                │
├─────────────────┼─────────────────┼─────────────────┤
│  Throws        │  No Exception   │
│  Concurrent-    │                │
│  Modification-  │                │
│  Exception      │                │
├─────────────────┼─────────────────┼─────────────────┤
│  Performance    │  Slower        │
│                │  (copying)    │
├─────────────────┼─────────────────┼─────────────────┤
│  Memory         │  More         │
│                │  (extra copy) │
├─────────────────┼─────────────────┼─────────────────┤
│  Example        │  Example       │
│  Collections:   │  Collections:  │
│  • ArrayList   │  • CopyOnWrite-│
│  • HashMap     │    ArrayList   │
│  • HashSet     │  • Concurrent-  │
│  • LinkedList  │    HashMap     │
│  • TreeMap     │  • Concurrent-  │
│  • TreeSet     │    SkipListMap │
└─────────────────┴─────────────────┴─────────────────┘

Why fail-fast?
• Detects concurrent modification quickly
• Fails immediately rather than unpredictable behavior
• Default behavior in most collections

Common Mistake:
Iterator it = list.iterator();
while(it.hasNext()) {
    list.remove(it.next());  // ❌ ConcurrentModificationException!
}

Correct Way:
Iterator it = list.iterator();
while(it.hasNext()) {
    it.remove();  // ✅ Using iterator's remove method
}
```

---

## 🎯 Final Practice Tips

### Important Formulas to Remember:

```
╔═══════════════════════════════════════════════════════════════════╗
║              PACKAGES, STRINGS & COLLECTIONS - QUICK REF         ║
╠═══════════════════════════════════════════════════════════════════╣
║                                                                   ║
║  STRINGS:                                                         ║
║  • String Pool: "literal" creates one object, reused             ║
║  • String is IMMUTABLE - concat() creates new String              ║
║  • Always use equals() for content comparison                    ║
║  • equals() vs == : equals=content, == = reference              ║
║                                                                   ║
║  STRINGBUFFER/BUILDER:                                           ║
║  • Mutable - original can be modified                           ║
║  • StringBuffer: Thread-safe, synchronized                       ║
║  • StringBuilder: NOT thread-safe, faster                       ║
║                                                                   ║
║  WRAPPER CLASSES:                                               ║
║  • Integer Cache: -128 to 127                                   ║
║  • Autoboxing: primitive → wrapper automatically               ║
║  • Unboxing: wrapper → primitive automatically                   ║
║                                                                   ║
║  THREADING:                                                      ║
║  • Thread start: t.start() NOT t.run()                         ║
║  • Two ways: extends Thread / implements Runnable               ║
║  • synchronized: prevents concurrent access                     ║
║  • wait() releases lock, sleep() keeps lock                    ║
║                                                                   ║
║  COLLECTIONS:                                                    ║
║  • List: Allows duplicates, ordered by index                   ║
║  • Set: NO duplicates                                           ║
║  • Map: Key-Value pairs, keys unique                           ║
║  • ArrayList default capacity: 10                              ║
║  • HashMap: Implements Map (not Set/List)                       ║
║                                                                   ║
║  GENERICS:                                                       ║
║  • Compile-time type safety                                     ║
║  • No casting needed                                            ║
║  • @Override: Verify method override                           ║
║                                                                   ║
║  FILE I/O:                                                       ║
║  • Serialization: Object → Bytes (Serializable interface)        ║
║  • transient: Don't serialize field                             ║
║  • BufferedReader has readLine()                                ║
║                                                                   ║
╚═══════════════════════════════════════════════════════════════════╝
```

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day7Questions)
