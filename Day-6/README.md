# 📚 Day 6: Applet & Graphics (AWT)

![Java](https://img.shields.io/badge/Java-Applet%20%26%20Graphics-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%206-success?style=for-the-badge)
![Duration](https://img.shields.io/badge/Duration-4%20Hours-yellow?style=for-the-badge)

> *Learning to create graphical applications and applets in Java!*

---

## 🌟 Welcome to Day 6!

Today we learn about **Applets** and **Graphics** in Java. Applets are small programs that run in web browsers, and Graphics is all about drawing shapes, text, and images. These topics are very important for your practical exams!

**Estimated Time:** 4 Hours  
**Prerequisites:** Days 1-5  
**Goal:** Master Applet lifecycle, Graphics methods, and AWT components

---

## 📖 Table of Contents

1. [What is an Applet?](#what-is-an-applet)
2. [Applet Lifecycle](#applet-lifecycle)
3. [Applet Methods](#applet-methods)
4. [Graphics Class](#graphics-class)
5. [Drawing Shapes](#drawing-shapes)
6. [AWT Components](#awt-components)
7. [Layout Managers](#layout-managers)
8. [Practice Questions](#-practice-questions)
9. [Quick Reference](#-quick-reference)

---

## 🍎 What is an Applet?

### Definition:
An **Applet** is a small program written in Java that can be embedded in a web page and run by any browser that supports Java.

### Applet vs Application:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    APPLET vs APPLICATION                              │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   APPLICATION                      APPLET                            │
│   ───────────                      ──────                            │
│   • Standalone program            • Runs in web browser             │
│   • Needs main() method          • No main() needed                │
│   • Full access to system        • Limited (sandbox security)       │
│   • Runs when you execute        • Runs when page is opened         │
│   • Can read/write files         • Cannot access local files       │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Why Applets?

```java
// ❌ NOT NEEDED in Applet
public static void main(String[] args) {
    System.out.println("This is not how applets work!");
}

// ✅ APPLET EXTENDS Applet class
import java.applet.Applet;
import java.awt.Graphics;

public class MyFirstApplet extends Applet {
    // Yehi sahi tarika hai!
}
```

### Real-Life Example:

```
┌─────────────────────────────────────────────────────────────┐
│                    HOW APPLET WORKS                          │
│                                                             │
│   ┌──────────────┐       ┌──────────────┐                 │
│   │   HTML File   │ ──── │   Browser     │                 │
│   │  with Applet  │       │   ( JVM )     │                 │
│   └──────────────┘       └───────┬──────┘                 │
│                                  │                          │
│                                  │                          │
│                                  ▼                          │
│                          ┌──────────────┐                   │
│                          │   Applet     │                   │
│                          │   Runs!      │                   │
│                          └──────────────┘                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 🔄 Applet Lifecycle

### The 5 Applet Methods:

Java applets have a complete lifecycle with 5 important methods:

```
┌─────────────────────────────────────────────────────────────────────┐
│                      APPLET LIFECYCLE                                │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Browser Opens Page                                                │
│          │                                                          │
│          ▼                                                          │
│   ┌─────────────┐                                                  │
│   │    init()    │  ← Initialization (runs ONCE)                  │
│   │  (First!)    │    • Set up variables                           │
│   └──────┬──────┘    • Load images                                 │
│          │            • Create components                            │
│          ▼                                                          │
│   ┌─────────────┐                                                  │
│   │   start()   │  ← Called when applet becomes visible           │
│   └──────┬──────┘    • Start animations                            │
│          │            • Start threads                                │
│          ▼                                                          │
│   ┌─────────────┐                                                  │
│   │   paint()   │  ← Draws content on screen                       │
│   │  (Graphics) │    • Draw shapes, text, images                    │
│   └──────┬──────┘    • Called repeatedly as needed                 │
│          │                                                            │
│          │  (User scrolls away or switches tabs)                    │
│          │                                                            │
│          ▼                                                            │
│   ┌─────────────┐                                                  │
│   │   stop()    │  ← Called when applet becomes invisible          │
│   └──────┬──────┘    • Stop animations                              │
│          │            • Stop threads                                 │
│          │                                                            │
│          │  (User comes back to page)                               │
│          │                                                            │
│          ▼                                                            │
│   ┌─────────────┐                                                  │
│   │   start()   │  ← Called again!                                 │
│   └──────┬──────┘                                                   │
│          │                                                            │
│          ▼                                                            │
│   ┌─────────────┐                                                  │
│   │   paint()   │  ← Paints again                                  │
│   └──────┬──────┘                                                   │
│          │                                                            │
│   (Browser closes)                                                   │
│          │                                                            │
│          ▼                                                            │
│   ┌─────────────┐                                                  │
│   │  destroy()  │  ← Last call (runs ONCE)                         │
│   └─────────────┘    • Release resources                             │
│                          • Clean up                                  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Lifecycle Explanation in Hinglish:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class AppletLifecycle extends Applet {
    
    // 1. init() - Jab pehli baar applet load hota hai
    // Ye sirf ek baar call hota hai
    public void init() {
        System.out.println("init() called - Applet initialized!");
        // Yahan variables set karo, images load karo
    }
    
    // 2. start() - Jab applet visible hota hai
    // Ye baar baar call ho sakta hai
    public void start() {
        System.out.println("start() called - Applet started!");
        // Yahan animations ya threads start karo
    }
    
    // 3. paint() - Jab screen pe kuch draw karna hai
    // Graphics object automatically milta hai
    public void paint(Graphics g) {
        System.out.println("paint() called - Drawing on screen!");
        // Yahan shapes, text, images draw karo
    }
    
    // 4. stop() - Jab applet invisible hota hai
    // User page se jata hai toh ye call hota hai
    public void stop() {
        System.out.println("stop() called - Applet stopped!");
        // Yahan animations ya threads stop karo
    }
    
    // 5. destroy() - Jab applet memory se hataya jata hai
    // Ye last mein ek baar call hota hai
    public void destroy() {
        System.out.println("destroy() called - Applet destroyed!");
        // Yahan resources release karo
    }
}
```

### Order of Execution:

```
Jab browser page kholta hai:
    init() → start() → paint()

Jab user page se jata hai:
    stop()

Jab user wapas aata hai:
    start() → paint()

Jab browser band hota hai:
    stop() → destroy()
```

---

## 🛠️ Applet Methods

### Method Details:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class AppletMethodsDemo extends Applet {
    
    // init() - Called ONCE when applet first loads
    // Yahan sab initialize karte hain
    public void init() {
        // Variables initialize karo
        // Components add karo
        // Images load karo
        setBackground(Color.white);  // Background color set karo
    }
    
    // start() - Called when applet becomes visible
    // Baar baar call ho sakta hai
    public void start() {
        // Animations start karo
        // Threads start karo
    }
    
    // paint() - Called to draw on screen
    // Graphics object automatically milta hai
    public void paint(Graphics g) {
        // Yeh sabse important method hai drawing ke liye!
        g.drawString("Hello Applet!", 50, 50);
    }
    
    // stop() - Called when applet becomes invisible
    public void stop() {
        // Animations stop karo
    }
    
    // destroy() - Called when applet is being removed
    public void destroy() {
        // Cleanup code
    }
}
```

### How to Run an Applet:

**Step 1:** Create HTML file

```html
<html>
<head>
    <title>My First Applet</title>
</head>
<body>
    <h1>Welcome to Java Applet!</h1>
    
    <applet code="MyApplet.class" width="400" height="300">
        Your browser does not support Java applets.
    </applet>
    
</body>
</html>
```

**Step 2:** Compile Java file

```bash
javac MyApplet.java
```

**Step 3:** Open HTML file in browser or use appletviewer

```bash
# Method 1: Using appletviewer (comes with JDK)
appletviewer MyApplet.html

# Method 2: Open HTML in browser (deprecated in modern browsers)
```

---

## 🎨 Graphics Class

### What is Graphics?

The **Graphics** class is used for drawing shapes, text, and images on a component (like an Applet or JPanel).

```
┌─────────────────────────────────────────────────────────────────────┐
│                    GRAPHICS CLASS METHODS                           │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   SHAPES                    TEXT                     COLORS         │
│   ───────                   ─────                    ──────        │
│   drawLine()               drawString()             setColor()     │
│   drawRect()               drawChars()              getColor()     │
│   fillRect()                                          setBackground()│
│   drawOval()                                           getBackground()│
│   fillOval()                                                   │
│   drawArc()                                                    │
│   drawPolygon()                                                │
│   drawPolyline()                                               │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Drawing Lines:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class LineDemo extends Applet {
    public void paint(Graphics g) {
        // drawLine(x1, y1, x2, y2)
        // (x1, y1) = starting point
        // (x2, y2) = ending point
        
        g.drawLine(50, 50, 200, 50);      // Horizontal line
        
        g.drawLine(50, 50, 50, 200);      // Vertical line
        
        g.drawLine(50, 50, 200, 200);     // Diagonal line
        
        // Lines with different colors
        g.setColor(Color.red);
        g.drawLine(50, 100, 200, 150);
    }
}
```

### Drawing Rectangles:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class RectDemo extends Applet {
    public void paint(Graphics g) {
        // drawRect(x, y, width, height) - outline
        // fillRect(x, y, width, height) - filled
        
        // Rectangle outline
        g.drawRect(50, 50, 100, 80);
        
        // Filled rectangle (red)
        g.setColor(Color.red);
        g.fillRect(200, 50, 100, 80);
        
        // 3D effect rectangle
        g.setColor(Color.gray);
        g.drawRoundRect(50, 150, 100, 80, 20, 20);
        
        // 3D filled rectangle
        g.fill3DRect(200, 150, 100, 80, true);
    }
}
```

### Drawing Ovals (Circles/Ellipses):

```java
import java.applet.Applet;
import java.awt.Graphics;

public class OvalDemo extends Applet {
    public void paint(Graphics g) {
        // drawOval(x, y, width, height) - outline
        // fillOval(x, y, width, height) - filled
        
        // Circle (width = height)
        g.drawOval(50, 50, 100, 100);
        
        // Filled circle (red)
        g.setColor(Color.red);
        g.fillOval(200, 50, 100, 100);
        
        // Ellipse (width ≠ height)
        g.setColor(Color.blue);
        g.drawOval(50, 180, 150, 80);
        
        // Filled ellipse
        g.fillOval(200, 180, 150, 80);
    }
}
```

### Drawing Arcs:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class ArcDemo extends Applet {
    public void paint(Graphics g) {
        // drawArc(x, y, width, height, startAngle, arcAngle)
        // startAngle: 0 = 3 o'clock, 90 = 12 o'clock
        
        // Quarter circle
        g.drawArc(50, 50, 100, 100, 0, 90);
        
        // Half circle
        g.drawArc(200, 50, 100, 100, 0, 180);
        
        // Filled arc
        g.setColor(Color.green);
        g.fillArc(50, 180, 100, 100, 0, 270);
        
        // Arc starting from different angle
        g.setColor(Color.orange);
        g.drawArc(200, 180, 100, 100, 45, 180);
    }
}
```

### Drawing Polygons:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class PolygonDemo extends Applet {
    public void paint(Graphics g) {
        // Method 1: Using arrays
        int xPoints[] = {50, 100, 150, 100};
        int yPoints[] = {50, 20, 50, 80};
        int nPoints = 4;
        
        g.drawPolygon(xPoints, yPoints, nPoints);
        
        // Filled triangle
        int xTri[] = {250, 300, 350};
        int yTri[] = {80, 20, 80};
        g.setColor(Color.red);
        g.fillPolygon(xTri, yTri, 3);
        
        // Method 2: Using Polygon object
        java.awt.Polygon p = new Polygon();
        p.addPoint(50, 150);
        p.addPoint(100, 100);
        p.addPoint(150, 150);
        p.addPoint(100, 200);
        g.setColor(Color.blue);
        g.fillPolygon(p);
    }
}
```

---

## 🖼️ Drawing with Colors

### Color Class Methods:

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class ColorDemo extends Applet {
    public void paint(Graphics g) {
        // Predefined colors
        g.setColor(Color.red);
        g.fillRect(50, 50, 100, 50);
        
        g.setColor(Color.green);
        g.fillRect(160, 50, 100, 50);
        
        g.setColor(Color.blue);
        g.fillRect(270, 50, 100, 50);
        
        // RGB Colors
        // Red: new Color(255, 0, 0)
        // Green: new Color(0, 255, 0)
        // Blue: new Color(0, 0, 255)
        
        // Custom color (purple)
        Color purple = new Color(128, 0, 128);
        g.setColor(purple);
        g.fillRect(50, 120, 100, 50);
        
        // RGB values
        Color myColor = new Color(255, 128, 0);  // Orange
        g.setColor(myColor);
        g.fillRect(160, 120, 100, 50);
        
        // Mixing RGB
        Color mixed = new Color(100, 100, 200);  // Light blue
        g.setColor(mixed);
        g.fillRect(270, 120, 100, 50);
    }
}
```

### Color RGB Chart:

```
┌─────────────────────────────────────────────────────────────────────┐
│                        COLOR RGB VALUES                              │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Color          R    G    B                                        │
│   ──────        ───  ───  ───                                       │
│   Black          0    0    0                                         │
│   White        255  255  255                                        │
│   Red         255    0    0                                         │
│   Green         0  255    0                                          │
│   Blue          0    0  255                                         │
│   Yellow      255  255    0                                         │
│   Cyan          0  255  255                                        │
│   Magenta     255    0  255                                        │
│   Orange      255  165    0                                         │
│   Pink        255  192  203                                        │
│   Gray        128  128  128                                        │
│   Light Gray  192  192  192                                        │
│   Dark Gray    64   64   64                                        │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 📝 Drawing Text

### Text Methods:

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;
import java.awt.Font;

public class TextDemo extends Applet {
    public void paint(Graphics g) {
        // Basic text
        g.drawString("Hello Java!", 50, 50);
        
        // Colored text
        g.setColor(Color.red);
        g.drawString("Red Text", 50, 100);
        
        // Different fonts
        Font font1 = new Font("Arial", Font.PLAIN, 20);
        Font font2 = new Font("Times New Roman", Font.BOLD, 24);
        Font font3 = new Font("Courier New", Font.ITALIC, 20);
        Font font4 = new Font("Arial", Font.BOLD + Font.ITALIC, 28);
        
        g.setFont(font1);
        g.drawString("Arial Plain", 50, 150);
        
        g.setFont(font2);
        g.setColor(Color.blue);
        g.drawString("Times Bold", 50, 200);
        
        g.setFont(font3);
        g.setColor(Color.green);
        g.drawString("Courier Italic", 50, 250);
        
        g.setFont(font4);
        g.setColor(Color.magenta);
        g.drawString("Arial Bold Italic", 50, 300);
    }
}
```

### Font Styles:

```
┌─────────────────────────────────────────────────────────────────────┐
│                        FONT STYLES                                  │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Font.PLAIN       ──────────────    Regular text                   │
│   Font.BOLD        ●─────────────    Bold text                       │
│   Font.ITALIC      ─────●────────    Italic text                     │
│   Font.BOLD + Font.ITALIC           Bold + Italic                   │
│                                                                     │
│   Font("FontName", style, size)                                      │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 🔧 repaint() and update()

### Understanding repaint():

```java
import java.applet.Applet;
import java.awt.Graphics;

public class RepaintDemo extends Applet implements Runnable {
    int x = 50;
    Thread t;
    
    public void init() {
        t = new Thread(this);
    }
    
    public void start() {
        t.start();
    }
    
    public void run() {
        while (true) {
            x += 5;
            if (x > getWidth()) {
                x = 0;
            }
            repaint();  //paint() ko dobara call karo
            
            try {
                Thread.sleep(50);
            } catch (Exception e) { }
        }
    }
    
    public void paint(Graphics g) {
        g.fillRect(x, 100, 50, 50);
    }
    
    public void stop() {
        t = null;
    }
}
```

### repaint() vs update():

```
┌─────────────────────────────────────────────────────────────────────┐
│                    repaint() FLOW                                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   repaint() called                                                   │
│        │                                                            │
│        ▼                                                            │
│   update() called (internally)                                       │
│        │                                                            │
│        ├── Clears screen with background color                      │
│        │                                                            │
│        ▼                                                            │
│   paint() called                                                    │
│        │                                                            │
│        └── Draws everything fresh                                    │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Why use repaint()?

```java
// Jab aap animation ya movement dikhana chahte ho
// toh baar baar paint() call karne ke liye repaint() use karte hain

public void paint(Graphics g) {
    // Yeh sirf ek baar draw hoga
}

// Lekin agar aap continuously draw karna chahte ho
// (like animation), toh repaint() use karo:

public void someMethod() {
    // Update position
    x = x + 5;
    
    // Request repaint
    repaint();  // Yeh internally paint() ko call karega
}
```

---

## 🧩 AWT Components

### What is AWT?

**AWT** stands for **Abstract Window Toolkit**. It's Java's first GUI framework that provides components for creating graphical user interfaces.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    AWT COMPONENTS                                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Button          ──►  Clickable button                             │
│   Label           ──►  Non-editable text                             │
│   TextField       ──►  Single line input                            │
│   TextArea        ──►  Multi-line input                             │
│   Checkbox        ──►  Yes/No option                                │
│   Choice          ──►  Dropdown menu                                │
│   List            ──►  Scrollable list                             │
│   Canvas          ──►  Drawing area                                 │
│   Scrollbar       ──►  Scrollable slider                            │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Adding Components to Applet:

```java
import java.applet.Applet;
import java.awt.*;

public class ComponentDemo extends Applet {
    Button btn;
    Label lbl;
    TextField tf;
    TextArea ta;
    Checkbox cb;
    Choice ch;
    
    public void init() {
        // Set layout
        setLayout(new FlowLayout());
        
        // Button
        btn = new Button("Click Me!");
        add(btn);
        
        // Label
        lbl = new Label("Enter your name:");
        add(lbl);
        
        // TextField
        tf = new TextField(20);
        add(tf);
        
        // TextArea
        ta = new TextArea(5, 20);
        add(ta);
        
        // Checkbox
        cb = new Checkbox("I agree");
        add(cb);
        
        // Choice/Dropdown
        ch = new Choice();
        ch.add("Java");
        ch.add("Python");
        ch.add("C++");
        add(ch);
    }
}
```

---

## 📐 Layout Managers

### Types of Layouts:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    LAYOUT MANAGERS                                  │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   FlowLayout         ──►  Left to right, wrap to next line         │
│   BorderLayout       ──►  North, South, East, West, Center         │
│   GridLayout         ──►  Rows and columns grid                    │
│   GridBagLayout      ──►  Flexible grid (complex)                  │
│   CardLayout         ──►  One card at a time                       │
│   null (absolute)    ──►  No layout, use x,y coordinates          │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### FlowLayout (Default):

```java
import java.applet.Applet;
import java.awt.*;

public class FlowLayoutDemo extends Applet {
    public void init() {
        // FlowLayout is default for Applet
        // Components go left to right, then wrap
        
        add(new Button("Button 1"));
        add(new Button("Button 2"));
        add(new Button("Button 3"));
        add(new Button("Button 4"));
        add(new Button("Button 5"));
    }
}
```

### BorderLayout:

```java
import java.applet.Applet;
import java.awt.*;

public class BorderLayoutDemo extends Applet {
    public void init() {
        setLayout(new BorderLayout());
        
        add(new Button("NORTH"), BorderLayout.NORTH);
        add(new Button("SOUTH"), BorderLayout.SOUTH);
        add(new Button("EAST"), BorderLayout.EAST);
        add(new Button("WEST"), BorderLayout.WEST);
        add(new Button("CENTER"), BorderLayout.CENTER);
    }
}
```

### GridLayout:

```java
import java.applet.Applet;
import java.awt.*;

public class GridLayoutDemo extends Applet {
    public void init() {
        // GridLayout(rows, columns)
        setLayout(new GridLayout(3, 2));
        
        add(new Button("1"));
        add(new Button("2"));
        add(new Button("3"));
        add(new Button("4"));
        add(new Button("5"));
        add(new Button("6"));
    }
}
```

---

## 🎯 Practice Questions

### MCQs:

**Q1. What is an Applet in Java?**
- A) Standalone application
- B) Small program that runs in a web browser ✅
- C) Database connection
- D) Network protocol

> **Hinglish:** Applet ek chhota program hai jo web browser mein ya applet viewer mein run hota hai.

---

**Q2. Which package contains Applet classes?**
- A) java.net
- B) java.applet ✅
- C) java.awt
- D) java.io

> **Hinglish:** Applet classes `java.applet` package mein hote hain.

---

**Q3. What is the correct lifecycle order of Applet methods?**
- A) init() → start() → paint() → stop() → destroy() ✅
- B) start() → init() → paint() → destroy() → stop()
- C) init() → paint() → start() → stop() → destroy()
- D) paint() → init() → start() → stop() → destroy()

> **Hinglish:** Applet lifecycle ka sahi order hai: init() → start() → paint() → stop() → destroy()

---

**Q4. Which method is used to draw shapes in an Applet?**
- A) draw()
- B) display()
- C) paint(Graphics g) ✅
- D) render()

> **Hinglish:** paint(Graphics g) method se applet mein shapes draw karte hain.

---

**Q5. What is the difference between drawRect() and fillRect()?**
- A) drawRect() draws filled, fillRect() draws outline
- B) drawRect() draws outline, fillRect() draws filled ✅
- C) Both are same
- D) None

> **Hinglish:** "draw" prefix means outline, "fill" prefix means filled shape.

---

**Q6. Which method draws a line in Java Graphics?**
- A) drawLine(x1, y1, x2, y2) ✅
- B) line(x1, y1, x2, y2)
- C) drawLine(x, y, width, height)
- D) lineTo(x1, y1, x2, y2)

> **Hinglish:** Graphics class ka drawLine() method line draw karne ke liye use hota hai.

---

**Q7. What is AWT in Java?**
- A) Abstract Window Toolkit ✅
- B) Advanced Window Technology
- C) Applet Window Toolkit
- D) Application Window Tools

> **Hinglish:** AWT = Abstract Window Toolkit. Yeh Java ka GUI package hai.

---

**Q8. Which layout manager arranges components in a single row?**
- A) BorderLayout
- B) GridLayout
- C) FlowLayout ✅
- D) CardLayout

> **Hinglish:** FlowLayout components ko ek line mein arrange karta hai.

---

**Q9. What does repaint() method do?**
- A) Directly repaints the component
- B) Calls update() which clears screen and calls paint() ✅
- C) Stops the applet
- D) Initializes the applet

> **Hinglish:** repaint() internally update() ko call karta hai jo screen clear karta hai aur phir paint() ko call karta hai.

---

**Q10. Which method is called when user leaves the applet page?**
- A) stop() ✅
- B) destroy()
- C) pause()
- D) exit()

> **Hinglish:** Jab user applet page se jata hai toh stop() call hota hai.

---

### Predict the Output:

**Q11. What will be drawn?**

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class TestApplet extends Applet {
    public void paint(Graphics g) {
        g.setColor(Color.red);
        g.drawRect(50, 50, 100, 100);
        
        g.setColor(Color.blue);
        g.fillRect(200, 50, 100, 100);
        
        g.setColor(Color.green);
        g.drawOval(50, 180, 80, 80);
        
        g.fillOval(200, 180, 80, 80);
    }
}
```

**Answer:**
- Red outline rectangle at (50,50) size 100x100
- Blue filled rectangle at (200,50) size 100x100
- Green outline circle at (50,180) size 80x80
- Green filled circle at (200,180) size 80x80

> **Hinglish:** drawRect outline banata hai, fillRect filled. Ovals ke liye same.

---

**Q12. What is the output of this lifecycle sequence?**

```
User opens page with applet:
1. Browser loads HTML
2. JVM initializes applet
3. User scrolls away
4. User comes back
5. User closes browser
```

**Answer:** init() → start() → paint() → stop() → start() → paint() → stop() → destroy()

> **Hinglish:** Browser opens → init,start,paint | User leaves → stop | User returns → start,paint | Browser closes → stop,destroy

---

### Coding Questions:

**Q13. Write a program to draw a house using Graphics methods:**

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class DrawHouse extends Applet {
    public void paint(Graphics g) {
        // Set background
        setBackground(Color.white);
        
        // Draw ground
        g.setColor(Color.green);
        g.fillRect(0, 300, 500, 50);
        
        // Draw house body
        g.setColor(Color.brown);
        g.fillRect(100, 180, 200, 120);
        
        // Draw roof
        g.setColor(Color.red);
        int xPoints[] = {90, 200, 310};
        int yPoints[] = {180, 100, 180};
        g.fillPolygon(xPoints, yPoints, 3);
        
        // Draw door
        g.setColor(Color.darkGray);
        g.fillRect(170, 230, 40, 70);
        
        // Draw windows
        g.setColor(Color.cyan);
        g.fillRect(120, 210, 30, 30);
        g.fillRect(250, 210, 30, 30);
        
        // Draw chimney
        g.setColor(Color.orange);
        g.fillRect(240, 110, 30, 50);
    }
}
```

---

**Q14. Write a program to animate a moving ball:**

```java
import java.applet.Applet;
import java.awt.Graphics;

public class MovingBall extends Applet implements Runnable {
    int x = 50;
    int y = 100;
    int dx = 5;
    int dy = 5;
    Thread t;
    
    public void init() {
        t = new Thread(this);
    }
    
    public void start() {
        t.start();
    }
    
    public void run() {
        while (true) {
            x += dx;
            y += dy;
            
            // Bounce off walls
            if (x < 0 || x > getWidth() - 30) {
                dx = -dx;
            }
            if (y < 0 || y > getHeight() - 30) {
                dy = -dy;
            }
            
            repaint();
            
            try {
                Thread.sleep(30);
            } catch (Exception e) { }
        }
    }
    
    public void paint(Graphics g) {
        g.fillOval(x, y, 30, 30);
    }
    
    public void stop() {
        t = null;
    }
}
```

---

**Q15. Write a program demonstrating different shapes:**

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class AllShapes extends Applet {
    public void paint(Graphics g) {
        // Line
        g.setColor(Color.black);
        g.drawLine(50, 30, 150, 30);
        
        // Rectangle
        g.setColor(Color.red);
        g.drawRect(50, 50, 100, 60);
        
        // Filled Rectangle
        g.setColor(Color.blue);
        g.fillRect(200, 50, 100, 60);
        
        // Rounded Rectangle
        g.setColor(Color.green);
        g.drawRoundRect(350, 50, 100, 60, 20, 20);
        
        // Circle (using oval with equal dimensions)
        g.setColor(Color.magenta);
        g.drawOval(50, 130, 60, 60);
        
        // Filled Circle
        g.setColor(Color.orange);
        g.fillOval(200, 130, 60, 60);
        
        // Ellipse
        g.setColor(Color.cyan);
        g.drawOval(350, 130, 80, 40);
        
        // Arc
        g.setColor(Color.pink);
        g.drawArc(50, 210, 60, 60, 0, 90);
        
        // String
        g.setColor(Color.darkGray);
        g.drawString("Java Graphics Demo!", 50, 300);
    }
}
```

---

## 📋 Quick Reference

### Applet Lifecycle:

```
init()     → Initialization (ONCE)
start()    → Start/Resume (MULTIPLE)
paint()    → Draw on screen (MULTIPLE)
stop()     → Pause (MULTIPLE)
destroy()  → Cleanup (ONCE)
```

### Graphics Methods:

```
DRAWING SHAPES:
drawLine(x1, y1, x2, y2)          Line
drawRect(x, y, w, h)              Rectangle outline
fillRect(x, y, w, h)              Filled rectangle
drawOval(x, y, w, h)             Oval/Circle outline
fillOval(x, y, w, h)              Filled oval
drawArc(x, y, w, h, start, end)  Arc outline
fillArc(x, y, w, h, start, end)  Filled arc
drawPolygon(x[], y[], n)          Polygon outline
fillPolygon(x[], y[], n)          Filled polygon

TEXT:
drawString(text, x, y)            Draw text

COLORS:
setColor(Color.xxx)               Set color
setBackground(Color.xxx)          Set background
```

### Layout Managers:

```
FlowLayout    → Left to right, wraps (DEFAULT)
BorderLayout  → N, S, E, W, Center
GridLayout    → Rows x Columns grid
```

### HTML for Applet:

```html
<applet code="ClassName.class" width="width" height="height">
    Message for unsupported browsers
</applet>
```

---

## 🎓 Day 6 Summary

### What We Learned:

```
✅ What is Applet and why use it
✅ Applet Lifecycle (5 methods)
✅ Graphics Class and its methods
✅ Drawing Lines, Rectangles, Ovals, Arcs, Polygons
✅ Working with Colors
✅ Drawing Text with Fonts
✅ repaint() and update() methods
✅ AWT Components
✅ Layout Managers (Flow, Border, Grid)
✅ Practical Programs
```

### Key Takeaways:

```
🎯 Applet = Small program in web browser
🎯 paint(Graphics g) = Main drawing method
🎯 draw = outline, fill = filled
🎯 init() = once, start() = multiple
🎯 repaint() calls paint() indirectly
🎯 FlowLayout = default layout
🎯 AWT = GUI toolkit
```

---

## 💪 Motivational Quote

> *"The best way to predict the future is to create it."*
> — Peter Drucker

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

## 📚 Continue Learning

⬅️ **[Day 5 - Final Revision](../Day-5/README.md)** | **Bonus Questions** ➡️

➡️ **[Bonus - Extra Practice Questions](../Bonus/BONUS-Questions.md)**

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day6)
