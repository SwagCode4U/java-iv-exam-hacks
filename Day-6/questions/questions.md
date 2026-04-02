# 📚 Day 6: Applet & Graphics - Question Bank

![Java](https://img.shields.io/badge/Java-Applet%20%26%20Graphics-orange?style=for-the-badge&logo=java)
![Day](https://img.shields.io/badge/Day-Day%206-success?style=for-the-badge)
![Questions](https://img.shields.io/badge/Questions-60+-blue?style=for-the-badge)

> *Practice makes perfect! Let's master Applet & Graphics!*

---

## 🎯 Section A: Multiple Choice Questions (MCQs)

### Q1. What is an Applet in Java?
- A) Standalone application
- B) Small program that runs in a web browser ✅
- C) Database connection
- D) Network protocol

> **Hinglish:** Applet ek chhota program hai jo web browser mein ya applet viewer mein run hota hai. Ise HTML page mein `<applet>` tag ke through embed kiya jata hai. Yeh standalone application nahi hai kyunki ise browser ke bina run nahi kar sakte. Java applets ko primarily academic aur educational purposes ke liye use kiya jata tha.

---

### Q2. Which package contains Applet classes?
- A) java.net
- B) java.applet ✅
- C) java.awt
- D) java.io

> **Hinglish:** Applet classes `java.applet` package mein hote hain. Is package mein mainly do classes hain - `Applet` aur `AppletContext`. `java.awt` GUI components ke liye hai, `java.net` networking ke liye, aur `java.io` input/output operations ke liye use hota hai.

---

### Q3. Which keyword is used to create an Applet?
- A) extends Applet ✅
- B) implements Applet
- C) import Applet
- D) new Applet

> **Hinglish:** Applet create karne ke liye `extends Applet` use karte hain. Yeh inheritance ka example hai jahan apni class `Applet` class se inherit karti hai. Ise implements nahi kar sakte kyunki Applet ek class hai, interface nahi. `import` sirf package ko include karne ke liye hota hai, class create nahi karta.

**Example:**
```java
public class MyApplet extends Applet {
    // Yeh sahi tarika hai Applet banana
}
```

---

### Q4. What is the correct lifecycle order of Applet methods?
- A) init() → start() → paint() → stop() → destroy() ✅
- B) start() → init() → paint() → destroy() → stop()
- C) init() → paint() → start() → stop() → destroy()
- D) paint() → init() → start() → stop() → destroy()

> **Hinglish:** Applet lifecycle ka sahi order bahut important hai exam ke liye:
> - **init()** - Sabse pehle ek baar call hota hai jab applet load hota hai
> - **start()** - init() ke baad aur jab user page pe wapas aata hai
> - **paint()** - Screen pe kuch draw karna ho toh
> - **stop()** - Jab user page se jata hai
> - **destroy()** - Last mein jab applet memory se hataya jata hai

**Memory Aid:** "I Spy Pigs Dying" = Init, Start, Paint, Stop, Destroy

---

### Q5. Which method is called first when an applet starts?
- A) init() ✅
- B) start()
- C) paint()
- D) main()

> **Hinglish:** Browser page kholne pe sabse pehle **init()** call hota hai. Yeh method sirf ek baar call hota hai applet ke poore lifecycle mein. **Bahut important:** Applets mein `main()` method nahi hota! Yeh application programs aur applets ka sabse bada farak hai. main() sirf standalone Java applications mein hota hai.

---

### Q6. Which method is used to draw shapes in an Applet?
- A) draw()
- B) display()
- C) paint(Graphics g) ✅
- D) render()

> **Hinglish:** Shapes draw karne ke liye `paint(Graphics g)` method use hota hai. Yeh method automatically call hota hai jab applet ko draw karna hota hai. Graphics object (g) jo isme aata hai, yeh hi hume drawing methods provide karta hai jaise `drawLine()`, `drawRect()`, `fillOval()`, etc.

**Syntax:**
```java
public void paint(Graphics g) {
    // yahan saare drawing commands likhte hain
    g.drawLine(50, 50, 150, 150);
}
```

---

### Q7. Which method draws a line in Java Graphics?
- A) drawLine(x1, y1, x2, y2) ✅
- B) line(x1, y1, x2, y2)
- C) drawLine(x, y, width, height)
- D) lineTo(x1, y1, x2, y2)

> **Hinglish:** Graphics class ka `drawLine(x1, y1, x2, y2)` method line draw karne ke liye use hota hai. Yeh 4 parameters letа hai:
> - **(x1, y1)** = Starting point (x = horizontal, y = vertical)
> - **(x2, y2)** = Ending point
> 
> **Common Mistake:** Line draw karne ke liye width aur height nahi dete, balki end coordinates dete hain!

---

### Q8. What is the difference between drawRect() and fillRect()?
- A) drawRect() draws filled, fillRect() draws outline
- B) drawRect() draws outline, fillRect() draws filled ✅
- C) Both are same
- D) None

> **Hinglish:** Yeh frequently puchna jata hai exam mein:
> - **drawRect(x, y, w, h)** = Sirf outline/border banata hai (khali rectangle)
> - **fillRect(x, y, w, h)** = Andar se colored bhara hua rectangle banata hai
> 
> **Memory Trick:** "DRAW = Drawn outline, FILL = Filled inside"

**Example:**
```java
g.drawRect(50, 50, 100, 50);    // Khali rectangle
g.fillRect(200, 50, 100, 50);   // Bhara hua rectangle
```

---

### Q9. Which of these is NOT a method of Graphics class?
- A) drawRect()
- B) fillRect()
- C) drawCircle() ✅
- D) drawArc()

> **Hinglish:** Graphics class mein `drawCircle()` naam ka koi method nahi hai! Yeh ek common confuse wali baat hai students ke beech.
> 
> **Circle draw karne ke liye:** `drawOval(x, y, diameter, diameter)` use karte hain jahan width aur height equal hoga.
> 
> **Sahi methods:**
> - drawOval(), fillOval() - Circle ya Ellipse
> - drawCircle() ❌ - Aisa koi method nahi hai!
> - drawRect(), fillRect() ✅
> - drawArc(), fillArc() ✅

---

### Q10. What does repaint() method do?
- A) Directly repaints the component
- B) Calls update() which clears screen and calls paint() ✅
- C) Stops the applet
- D) Initializes the applet

> **Hinglish:** `repaint()` kaafi important method hai animations ke liye. Iska actual flow yeh hai:
> 
> **repaint() → update() → paint()**
> 
> 1. `repaint()` ko call karo
> 2. `repaint()` internally `update()` ko call karta hai
> 3. `update()` pehle screen ko background color se clear karta hai
> 4. Phir `paint()` ko call karta hai jo naya content draw karta hai
> 
> **Kab use karte hain:** Jab aapko baar baar screen update karna ho (jaise animation mein), tab `repaint()` use karte hain ek thread ke andar.

---

### Q11. What is AWT in Java?
- A) Abstract Window Toolkit ✅
- B) Advanced Window Technology
- C) Applet Window Toolkit
- D) Application Window Tools

> **Hinglish:** AWT ka full form hai **"Abstract Window Toolkit"**. Yeh Java ka pehla GUI (Graphical User Interface) package tha jo platform-independent window applications ke liye use hota tha. AWT components platform-specific hote hain, isliye baad mein Swing ko introduce kiya gaya jo pure Java-based tha.
> 
> **Components provided by AWT:** Button, Label, TextField, TextArea, Checkbox, Choice, List, Menu, Canvas, Scrollbar, etc.

---

### Q12. Which layout manager arranges components in a single row?
- A) BorderLayout
- B) GridLayout
- C) FlowLayout ✅
- D) CardLayout

> **Hinglish:** `FlowLayout` components ko ek line mein arrange karta hai, left se right, aur jab ek line full ho jati hai toh next line mein wrap kar deta hai. Yeh Applet ka default layout manager hai.
> 
> **Characteristics:**
> - Components ki original size maintain karta hai
> - Center alignment by default
> - Left, right, ya center alignment set kar sakte hain

---

### Q13. What is the default layout manager for Applet?
- A) BorderLayout
- B) GridLayout
- C) FlowLayout ✅
- D) null (absolute)

> **Hinglish:** Applet ka default layout manager **FlowLayout** hai. Jab aap koi layout explicitly set nahi karte, toh Java automatically FlowLayout use karta hai.
> 
> **Yeh yaad rakhne ka tarika:** "APPLET = FLOW" (Alphabetically A comes before B, so FlowLayout)

---

### Q14. Which method is called when user leaves the applet page?
- A) stop() ✅
- B) destroy()
- C) pause()
- D) exit()

> **Hinglish:** Jab user browser mein se applet wale page se jata hai (tab change karta hai ya browser minimize karta hai), toh `stop()` method automatically call hota hai.
> 
> **Lifecycle samjho:**
> ```
> Page Open → init() → start() → paint()
> User Leaves → stop()
> User Returns → start() → paint()
> Browser Close → stop() → destroy()
> ```
> 
> **Important:** `destroy()` sirf browser band karte waqt call hota hai, user sirf leave kare toh nahi.

---

### Q15. What is the purpose of init() method in Applet?
- A) To start the applet
- B) To initialize resources, load images ✅
- C) To draw on screen
- D) To close the applet

> **Hinglish:** `init()` method applet ka sabse pehla method hai jo browser page load hone pe call hota hai. Isme aap:
> - Variables ko initialize karte ho
> - Images ya media load karte ho
> - Components add karte ho (buttons, text fields, etc.)
> - Settings configure karte ho
> 
> **Important:** Yeh method SIRF EK BAAR call hota hai applet ke poore lifecycle mein. Start() baar baar call ho sakta hai, init() nahi.

---

### Q16. Which of these is used to draw a circle?
- A) drawCircle(x, y, radius)
- B) circle(x, y, radius)
- C) drawOval(x, y, diameter, diameter) ✅
- D) fillOval(x, y, diameter, diameter)

> **Hinglish:** Java Graphics mein circle draw karne ka koi direct method nahi hai. Aapko `drawOval()` ya `fillOval()` use karna hota hai jisme width aur height (diameter) equal diya jata hai.
> 
> **Formula:** `drawOval(x, y, diameter, diameter)` jahan x,y top-left corner hai aur diameter circle ka size hai.
> 
> **Example:**
> ```java
> g.drawOval(50, 50, 100, 100);  // Center (50,50) pe 100x100 ka circle
> g.fillOval(200, 50, 100, 100); // Filled circle
> ```

---

### Q17. What is the output of drawArc(50, 50, 100, 100, 0, 90)?
- A) Full circle
- B) Quarter circle (top-right) ✅
- C) Half circle
- D) Three-quarter circle

> **Hinglish:** `drawArc(x, y, width, height, startAngle, arcAngle)` method ke parameters:
> 
> - **x, y, width, height** = bounding rectangle (jisme arc and.fit hoga)
> - **startAngle** = Jahan se arc shuru hoga (degrees mein)
> - **arcAngle** = Kitni degree tak arc jayega
> 
> **Angle directions samjho:**
> ```
> 0°   = 3 o'clock position (right side)
> 90°  = 12 o'clock position (top)
> 180° = 9 o'clock position (left)
> 270° = 6 o'clock position (bottom)
> ```
> 
> **Is question mein:** 0° se 90° tak = Clockwise direction mein top-right quarter (90° ka ek quadrant)

---

### Q18. Which of these draws text on the screen?
- A) print()
- B) drawText()
- C) drawString() ✅
- D) write()

> **Hinglish:** Graphics class mein text draw karne ke liye `drawString(text, x, y)` method use hota hai.
> 
> **Syntax:** `g.drawString("Hello", 50, 100);`
> - Pehla parameter = Text string
> - Dusra = x coordinate (horizontal position)
> - Teesra = y coordinate (vertical position - BASELINE of text!)
> 
> **Common Mistake:** Student aksar x,y ko center samajh kar text place karte hain. Actually y coordinate text ki baseline hai, top nahi!

---

### Q19. How do you create a Color object with RGB values?
- A) new Color(red, green, blue) ✅
- B) new Color("red", "green", "blue")
- C) Color.RGB(red, green, blue)
- D) Color.create(red, green, blue)

> **Hinglish:** Custom color banana ke liye `new Color(int r, int g, int b)` constructor use karte hain jahan:
> - **r** = Red color ka value (0-255)
> - **g** = Green color ka value (0-255)
> - **b** = Blue color ka value (0-255)
> 
> **Common RGB Values:**
> | Color | RGB |
> |-------|-----|
> | Red | (255, 0, 0) |
> | Green | (0, 255, 0) |
> | Blue | (0, 0, 255) |
> | Yellow | (255, 255, 0) |
> | White | (255, 255, 255) |
> | Black | (0, 0, 0) |
> | Orange | (255, 165, 0) |
> | Purple | (128, 0, 128) |

---

### Q20. Which keyword is used to inherit Applet class?
- A) import
- B) extends ✅
- C) implements
- D) this

> **Hinglish:** Applet class ko inherit karne ke liye `extends` keyword use hota hai. Yeh inheritance ka concept hai OOP ka.
> 
> **Why extends?** Kyunki Applet ek class hai, interface nahi. Interfaces ko implement karte hain (implements keyword), classes ko extend karte hain (extends keyword).
> 
> **Example:**
> ```java
> public class MyFirstApplet extends Applet {
>     // Applet class se properties aur methods inherit hote hain
> }
> ```

---

### Q21. What does BorderLayout.NORTH do?
- A) Centers at top
- B) Places at top ✅
- C) Places at left
- D) Places at center

> **Hinglish:** BorderLayout screen ko 5 regions mein divide karta hai:
> 
> | Region | Position |
> |--------|----------|
> | NORTH | Top of screen (header) |
> | SOUTH | Bottom of screen (footer) |
> | EAST | Right side |
> | WEST | Left side |
> | CENTER | Middle (jo baaki space hai) |
> 
> **Important:** CENTER region sabse important hai kyunki agar koi component nahi dalte toh CENTER automatically fill hota hai.

---

### Q22. Which method is called last when applet is being destroyed?
- A) stop()
- B) destroy() ✅
- C) exit()
- D) close()

> **Hinglish:** `destroy()` applet lifecycle mein sabse last method hai jo tab call hota hai jab browser completely band ho raha hai ya applet page se permanently remove ho raha hai.
> 
> **Yeh kab call hota hai:**
> - Jab user browser band karta hai
> - Jab applet ko programmatically remove kiya jata hai
> 
> **Yeh kya karta hai:**
> - Resources release karta hai (memory free karna)
> - Threads stop karta hai
> - Cleanup operations perform karta hai

---

### Q23. What is the difference between update() and paint()?
- A) update() draws, paint() clears
- B) update() clears and calls paint() ✅
- C) Both are same
- D) paint() clears and calls update()

> **Hinglish:** Yeh ek tricky question hai jo frequently pucha jata hai!
> 
> | Method | Kaam |
> |--------|------|
> | paint() | Screen pe content draw karta hai |
> | update() | Screen clear karta hai (background color se) PHIR paint() ko call karta hai |
> 
> **Flow:** `repaint()` → `update()` → `paint()`
> 
> **Kab override karna chahiye?**
> - Agar aap chahte ho ki purana content na clear ho (flickering avoid karne ke liye), toh `update()` ko override kar sakte ho
> - Normal case mein `paint()` override karna enough hai

---

### Q24. Which is NOT part of the Graphics class drawing methods?
- A) drawPolygon()
- B) drawPolyline()
- C) drawPath() ✅
- D) drawRoundRect()

> **Hinglish:** Graphics class mein `drawPath()` naam ka koi method nahi hai. Yeh ek common mistake hai.
> 
> **Sahi Drawing Methods:**
> - Lines: `drawLine()`
> - Rectangles: `drawRect()`, `fillRect()`, `drawRoundRect()`, `fillRoundRect()`, `draw3DRect()`, `fill3DRect()`
> - Ovals: `drawOval()`, `fillOval()`
> - Arcs: `drawArc()`, `fillArc()`
> - Polygons: `drawPolygon()`, `fillPolygon()`
> - Text: `drawString()`
> - Images: `drawImage()`

---

### Q25. What is the correct HTML to embed an applet?

```html
<applet code="MyApplet.class" width="300" height="200">
</applet>
```

- A) Only this is correct
- B) Should use `<object>` tag instead
- C) Needs archive attribute
- D) Both A and B are correct ✅

> **Hinglish:** Dono tarike sahi hain:
> 
> **`<applet>` tag (Traditional):**
> ```html
> <applet code="MyApplet.class" width="300" height="200">
>     Your browser does not support Java applets.
> </applet>
> ```
> 
> **`<object>` tag (Modern):**
> ```html
> <object classid="java:MyApplet.class" width="300" height="200">
> </object>
> ```
> 
> **Important Attributes:**
> - `code` = Class file ka naam (.class extension ke saath)
> - `width` aur `height` = Applet ki size pixels mein

---

### Q26. Which method is used to set font in Graphics?
- A) setFont()
- B) Font()
- C) drawFont()
- D) font()

> **Hinglish:** Font set karne ke liye `setFont(Font f)` method use hota hai Graphics object pe.
> 
> **Font class ka use:**
> ```java
> Font font = new Font("Arial", Font.BOLD, 24);
> g.setFont(font);
> g.drawString("Hello!", 50, 50);
> ```
> 
> **Font constructor:** `Font(String name, int style, int size)`
> - name = "Arial", "Times New Roman", "Courier", etc.
> - style = Font.PLAIN, Font.BOLD, Font.ITALIC, ya Font.BOLD + Font.ITALIC
> - size = Points mein font size

---

### Q27. What is the difference between Canvas and Applet?
- A) Canvas is for drawing, Applet is a container
- B) Canvas is a lightweight component, Applet is heavyweight
- C) Canvas needs Container to be displayed
- D) All of the above ✅

> **Hinglish:** Canvas aur Applet dono drawing ke liye use hote hain lekin bahut important differences hain:
> 
> | Canvas | Applet |
> |--------|--------|
> | Lightweight component | Heavyweight component |
> | Drawing ke liye specialized | Full application container |
> | Kisi aur container mein add hota hai | Standalone run hota hai |
> | No lifecycle methods | Has init(), start(), stop(), destroy() |
> 
> **Kaun use karein?**
> - Simple drawing ke liye Canvas best hai
> - Complex application ke liye Applet better hai

---

### Q28. What is the coordinate system used in Java Graphics?
- A) Cartesian (bottom-left origin)
- B) Screen (top-left origin) ✅
- C) Mathematical (center origin)
- D) Custom origin

> **Hinglish:** Java Graphics mein coordinate system ka origin (0,0) **top-left corner** mein hota hai, Cartesian system se ulta!
> 
> ```
> (0,0) ──────────────→ X axis
>   │
>   │     (100, 100) yahan hoga
>   │
>   ▼
>   Y axis
> ```
> 
> - X axis left se right jaata hai
> - Y axis top se bottom jaata hai
> - Jaise jaise Y badhta hai, neeche jate hain

---

### Q29. What happens when you don't override paint() method?
- A) Compilation error
- B) Applet will be blank/white ✅
- C) Default shapes appear
- D) Runtime error

> **Hinglish:** Agar aap paint() method override nahi karte, toh applet blank/white rahega kyunki koi content draw nahi hoga. Java ka default paint() method sirf background color set karta hai aur kuch nahi draw karta.
> 
> **Always remember:** Agar aapko kuch draw karna hai applet mein, toh paint() method override karna zaroori hai!
> 
> ```java
> public class MyApplet extends Applet {
>     public void paint(Graphics g) {
>         // Yahan saare drawing commands likho
>         g.drawString("Hello!", 50, 50);
>     }
> }
> ```

---

### Q30. Which is the correct way to draw a filled triangle?
- A) drawTriangle(x1, y1, x2, y2, x3, y3)
- B) fillTriangle(x1, y1, x2, y2, x3, y3)
- C) drawPolygon(x[], y[], 3) ✅
- D) fillPolygon(3 points)

> **Hinglish:** Java Graphics mein triangle draw karne ka direct method nahi hai. Aapko `drawPolygon()` ya `fillPolygon()` use karna padta hai.
> 
> **Triangle draw karne ka tarika:**
> ```java
> int xPoints[] = {100, 150, 200};  // 3 points ke x coordinates
> int yPoints[] = {50, 100, 50};     // 3 points ke y coordinates
> int nPoints = 3;  // Triangle ke 3 corners hain
> 
> g.drawPolygon(xPoints, yPoints, nPoints);  // Outline
> g.fillPolygon(xPoints, yPoints, nPoints);  // Filled
> ```
> 
> **Important:** Polygon ke points clockwise ya counter-clockwise order mein hone chahiye.

---

## 🎯 Section B: Predict the Output

### Q31. What will be drawn?

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class TestApplet1 extends Applet {
    public void paint(Graphics g) {
        g.setColor(Color.red);
        g.drawRect(50, 50, 100, 100);
        
        g.setColor(Color.blue);
        g.fillRect(200, 50, 100, 100);
        
        g.setColor(Color.green);
        g.drawOval(50, 180, 80, 80);
        
        g.fillOval(200, 180, 80, 80);
        
        g.setColor(Color.black);
        g.drawLine(50, 300, 350, 300);
    }
}
```

**Options:**
- A) Two red squares, two green circles, black line
- B) One red outline square, one blue filled square, one green outline circle, one green filled circle, black horizontal line ✅
- C) Two red squares, two blue circles, black line
- D) Two rectangles, two circles, no line

> **Hinglish - Step by Step Analysis:**
> 
> **Line 1:** `drawRect(50, 50, 100, 100)` 
> → Red outline square at position (50,50) with size 100x100
> 
> **Line 2:** `fillRect(200, 50, 100, 100)`
> → Blue filled square at (200,50) - Different position so separate
> 
> **Line 3:** `drawOval(50, 180, 80, 80)`
> → Green outline circle (width=height) at (50,180)
> 
> **Line 4:** `fillOval(200, 180, 80, 80)`
> → Green filled circle at (200,180) - Same color but different position
> 
> **Line 5:** `drawLine(50, 300, 350, 300)`
> → Black horizontal line from (50,300) to (350,300)

---

### Q32. What will be drawn?

```java
import java.applet.Applet;
import java.awt.Graphics;

public class TestApplet2 extends Applet {
    public void paint(Graphics g) {
        g.drawArc(50, 50, 100, 100, 0, 180);
        g.drawArc(200, 50, 100, 100, 0, -180);
        g.drawArc(350, 50, 100, 100, 0, 90);
    }
}
```

**Options:**
- A) Half circle, other half circle, quarter circle
- B) Bottom half, top half, quarter circle ✅
- C) Full circle, full circle, full circle
- D) Quarter circle, half circle, half circle

> **Hinglish - Arc Analysis:**
> 
> **Arc 1:** `drawArc(50, 50, 100, 100, 0, 180)`
> → Bounding box: 100x100 at (50,50)
> → Start: 0° (3 o'clock), Arc: 180° clockwise
> → **Result:** Bottom half of circle (semicircle facing down)
> 
> **Arc 2:** `drawArc(200, 50, 100, 100, 0, -180)`
> → Same bounding box at different position
> → Start: 0°, Arc: -180° (anticlockwise)
> → **Result:** Top half of circle (semicircle facing up)
> 
> **Arc 3:** `drawArc(350, 50, 100, 100, 0, 90)`
> → Start: 0°, Arc: 90° clockwise
> → **Result:** Quarter circle (top-right quadrant)

---

### Q33. What is the output of this lifecycle sequence?

```
User opens page with applet
→ User minimizes browser
→ User restores browser
→ User closes browser
```

**Options:**
- A) init, start, paint, stop, start, paint, stop, destroy ✅
- B) init, start, paint, stop, start, paint, destroy
- C) init, start, paint, start, paint, destroy
- D) init, paint, start, stop, destroy

> **Hinglish - Lifecycle Step by Step:**
> 
> **1. Browser page opens:**
> → init() [First time initialization]
> → start() [Applet start hua]
> → paint() [Screen draw hua]
> 
> **2. User minimizes browser:**
> → stop() [Applet band hua, visible nahi]
> 
> **3. User restores browser:**
> → start() [Wapas start]
> → paint() [Wapas draw]
> 
> **4. User closes browser:**
> → stop() [Final stop]
> → destroy() [Cleanup aur remove]

---

### Q34. What will be the result of these statements?

```java
g.setColor(Color.red);
g.fillRect(50, 50, 100, 50);

g.setColor(Color.blue);
g.fillRect(60, 60, 100, 50);
```

**Options:**
- A) Two separate rectangles
- B) Two overlapping rectangles (blue partially covers red) ✅
- C) Only blue rectangle visible
- D) Only red rectangle visible

> **Hinglish - Overlapping Analysis:**
> 
> **Rectangle 1:** Red at (50,50), size 100x50
> → Occupies: x=50 to 150, y=50 to 100
> 
> **Rectangle 2:** Blue at (60,60), size 100x50
> → Occupies: x=60 to 160, y=60 to 110
> 
> **Overlap Area:** x=60 to 150, y=60 to 100
> → Is area mein blue rectangle red ke upar aayega
> → Jo portion blue rectangle ka hai wohi dikhega
> 
> **Rule:** Jo baad mein draw hota hai woh upar rehta hai (Z-order)

---

### Q35. What will this code draw?

```java
g.drawLine(50, 50, 150, 50);   // Statement 1
g.drawLine(150, 50, 150, 150); // Statement 2
g.drawLine(150, 150, 50, 150); // Statement 3
g.drawLine(50, 150, 50, 50);   // Statement 4
```

**Options:**
- A) Circle
- B) Triangle
- C) Rectangle ✅
- D) Pentagon

> **Hinglish - Step by Step Drawing:**
> 
> **Statement 1:** `(50,50)` to `(150,50)` 
> → Top horizontal line (left to right)
> 
> **Statement 2:** `(150,50)` to `(150,150)`
> → Right vertical line (top to bottom)
> 
> **Statement 3:** `(150,150)` to `(50,150)`
> → Bottom horizontal line (right to left)
> 
> **Statement 4:** `(50,150)` to `(50,50)`
> → Left vertical line (bottom to top)
> 
> **Result:** Ek complete rectangle ban gayi 100x100 size ki

---

### Q36. What color will be visible?

```java
g.setColor(Color.red);
g.fillRect(50, 50, 100, 100);

g.setColor(new Color(0, 0, 0, 0));  // Transparent?
g.fillRect(70, 70, 60, 60);
```

**Options:**
- A) Red rectangle only
- B) Black rectangle only
- C) Red rectangle with black overlay (where they overlap)
- D) White background only

> **Hinglish - Transparency Analysis:**
> 
> **Point to Note:** Java AWT Graphics mein transparency ka support limited hai. `new Color(r, g, b, a)` constructor supported hai but Alpha value (a) ka effect varying hai.
> 
> **Rectangle 1:** Red filled at (50,50)
> → Pure red rectangle dikhegi
> 
> **Rectangle 2:** Black with transparency at (70,70)
> → Overlapping portion mein effect depends karta hai on alpha value
> 
> **Note:** Agar aap chahte ho ki transparency work kare, toh Swing's Graphics2D better hai

---

### Q37. What will be drawn by this code?

```java
g.drawRoundRect(50, 50, 100, 80, 20, 20);
```

**Options:**
- A) Rectangle with sharp corners
- B) Rectangle with rounded corners (arc radius 20) ✅
- C) Ellipse
- D) Circle

> **Hinglish - RoundRect Explanation:**
> 
> **Parameters:** `drawRoundRect(x, y, width, height, arcWidth, arcHeight)`
> 
> | Parameter | Value | Meaning |
> |-----------|-------|---------|
> | x, y | 50, 50 | Position |
> | width, height | 100, 80 | Rectangle size |
> | arcWidth | 20 | Horizontal corner radius |
> | arcHeight | 20 | Vertical corner radius |
> 
> **Result:** Rectangle jisme corners curved hain (20 pixel radius ke)
> 
> **Note:** Agar arcWidth = arcHeight = width/height, toh bahut rounded lagegi

---

## 🎯 Section C: Coding Questions

### Q38. Write a program to draw a smiley face in Applet.

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class SmileyFace extends Applet {
    public void paint(Graphics g) {
        // Step 1: Face draw karo (yellow filled circle)
        g.setColor(Color.yellow);
        g.fillOval(100, 100, 200, 200);
        
        // Step 2: Face ka outline draw karo (black)
        g.setColor(Color.black);
        g.drawOval(100, 100, 200, 200);
        
        // Step 3: Left eye draw karo (black filled small circles)
        g.fillOval(150, 150, 30, 30);
        
        // Step 4: Right eye draw karo (black filled small circles)
        g.fillOval(220, 150, 30, 30);
        
        // Step 5: Smile draw karo (arc - smile shape)
        // drawArc(x, y, w, h, startAngle, arcAngle)
        g.drawArc(140, 180, 120, 80, 0, 180);
        
        // Step 6: Optional nose draw karo (small triangle ya lines)
        g.drawLine(200, 180, 190, 220);
        g.drawLine(200, 180, 210, 220);
    }
}
```

**Output Explanation:**
```
        👁️👁️         ← Eyes (filled black circles)
        _____
       /     \
      /  👃   \      ← Nose (two lines)
      \       /
       \_____/
         ^^^         ← Smile (arc - bottom half of oval)
```

---

### Q39. Write a program to draw Indian flag using Graphics.

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class IndianFlag extends Applet {
    public void paint(Graphics g) {
        // Flag dimensions define karo
        int flagX = 50;
        int flagY = 50;
        int flagWidth = 300;
        int stripHeight = flagWidth / 3;  // Har strip 100 height ki
        
        // Flag pole draw karo (brown color)
        g.setColor(Color.brown);
        g.fillRect(30, 30, 15, 400);
        
        // Saffron strip (top) - Color RGB(255, 153, 51)
        g.setColor(new Color(255, 153, 51));
        g.fillRect(flagX, flagY, flagWidth, stripHeight);
        
        // White strip (middle)
        g.setColor(Color.white);
        g.fillRect(flagX, flagY + stripHeight, flagWidth, stripHeight);
        
        // Green strip (bottom) - Color RGB(19, 136, 8)
        g.setColor(new Color(19, 136, 8));
        g.fillRect(flagX, flagY + (stripHeight * 2), flagWidth, stripHeight);
        
        // Ashoka Chakra draw karo (blue circle with 24 spokes)
        int centerX = flagX + flagWidth / 2;
        int centerY = flagY + stripHeight + (stripHeight / 2);
        int radius = stripHeight / 2 - 10;
        
        // Chakra ki outer circle
        g.setColor(Color.blue);
        g.drawOval(centerX - radius, centerY - radius, radius * 2, radius * 2);
        
        // Center mein chhoti circle
        g.fillOval(centerX - 5, centerY - 5, 10, 10);
        
        // 24 spokes draw karo (har spoke 15 degree pe)
        for (int i = 0; i < 24; i++) {
            // Trigonometry use karke spoke endpoints calculate karo
            double angle = i * 15 * Math.PI / 180;
            int x2 = centerX + (int)(radius * Math.cos(angle));
            int y2 = centerY - (int)(radius * Math.sin(angle));
            g.drawLine(centerX, centerY, x2, y2);
        }
    }
}
```

---

### Q40. Write a program to animate a bouncing ball.

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class BouncingBall extends Applet implements Runnable {
    int x = 50;        // Ball ki horizontal position
    int y = 50;        // Ball ki vertical position
    int dx = 5;        // Horizontal speed (pixels per frame)
    int dy = 5;        // Vertical speed (pixels per frame)
    Thread animator;   // Animation ke liye thread
    
    public void init() {
        setBackground(Color.black);  // Background color set karo
        animator = new Thread(this);  // Thread create karo
    }
    
    public void start() {
        animator.start();  // Animation thread shuru karo
    }
    
    public void run() {
        while (true) {  // Infinite loop animation ke liye
            // Position update karo
            x += dx;
            y += dy;
            
            // Horizontal boundary check (left/right walls se bounce)
            if (x <= 0 || x >= getWidth() - 40) {
                dx = -dx;  // Direction reverse karo
            }
            
            // Vertical boundary check (top/bottom se bounce)
            if (y <= 0 || y >= getHeight() - 40) {
                dy = -dy;  // Direction reverse karo
            }
            
            // Screen refresh karo (animation ke liye zaroori)
            repaint();
            
            // Thread ko 30 milliseconds ke liye roko
            try {
                Thread.sleep(30);
            } catch (InterruptedException e) {
                break;  // Thread interrupt hua toh loop se bahar nikal
            }
        }
    }
    
    public void paint(Graphics g) {
        // Ball draw karo (gradient effect ke saath)
        // Main ball (blue)
        g.setColor(Color.blue);
        g.fillOval(x, y, 40, 40);
        
        // Highlight (white small circle - light effect)
        g.setColor(Color.white);
        g.fillOval(x + 5, y + 5, 12, 12);
        
        // Ball ki outline (dark blue)
        g.setColor(Color.darkGray);
        g.drawOval(x, y, 40, 40);
    }
    
    public void stop() {
        animator = null;  // Thread ko stop karo
    }
}
```

---

### Q41. Write a program demonstrating various Graphics methods.

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;
import java.awt.Font;

public class GraphicsDemo extends Applet {
    public void paint(Graphics g) {
        // ============================================
        // LINES
        // ============================================
        g.setColor(Color.black);
        g.drawLine(50, 30, 200, 30);  // Simple horizontal line
        
        // ============================================
        // RECTANGLES
        // ============================================
        
        // Rectangle outline (red)
        g.setColor(Color.red);
        g.drawRect(50, 50, 100, 60);
        
        // Filled rectangle (blue)
        g.setColor(Color.blue);
        g.fillRect(170, 50, 100, 60);
        
        // 3D Rectangle (gray)
        g.setColor(Color.gray);
        g.draw3DRect(290, 50, 100, 60, true);
        
        // Rounded Rectangle outline (orange)
        g.setColor(Color.orange);
        g.drawRoundRect(50, 130, 100, 60, 20, 20);
        
        // ============================================
        // OVALS / CIRCLES
        // ============================================
        
        // Circle outline (magenta)
        g.setColor(Color.magenta);
        g.drawOval(50, 210, 60, 60);  // width=height = circle
        
        // Filled circle (cyan)
        g.setColor(Color.cyan);
        g.fillOval(130, 210, 60, 60);
        
        // Ellipse (purple) - width ≠ height
        g.setColor(Color.pink);
        g.drawOval(210, 215, 80, 50);
        
        // ============================================
        // ARCS
        // ============================================
        
        // Arc outline (dark gray)
        g.setColor(Color.darkGray);
        g.drawArc(50, 300, 80, 80, 0, 90);  // Quarter arc
        
        // Filled arc (green)
        g.setColor(Color.green);
        g.fillArc(150, 300, 80, 80, 45, 180);  // 180 degree arc from 45
        
        // ============================================
        // TEXT
        // ============================================
        
        g.setColor(Color.black);
        Font f1 = new Font("Arial", Font.PLAIN, 14);
        Font f2 = new Font("Times New Roman", Font.BOLD, 16);
        Font f3 = new Font("Courier New", Font.ITALIC, 14);
        
        g.setFont(f1);
        g.drawString("Arial Plain", 300, 240);
        
        g.setFont(f2);
        g.drawString("Times Bold", 300, 270);
        
        g.setFont(f3);
        g.drawString("Courier Italic", 300, 300);
    }
}
```

---

### Q42. Write a program to draw a calculator.

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;
import java.awt.Font;

public class CalculatorDraw extends Applet {
    public void paint(Graphics g) {
        // Calculator ka body (gray background)
        g.setColor(Color.gray);
        g.fillRoundRect(50, 50, 220, 320, 15, 15);
        
        // Body ka border (dark gray)
        g.setColor(Color.darkGray);
        g.drawRoundRect(50, 50, 220, 320, 15, 15);
        
        // Display area (white rectangle)
        g.setColor(Color.white);
        g.fillRect(65, 70, 190, 50);
        
        // Display pe text
        g.setColor(Color.black);
        Font displayFont = new Font("Arial", Font.BOLD, 28);
        g.setFont(displayFont);
        g.drawString("1234", 170, 105);
        
        // Button colors define karo
        Color numberBtn = new Color(200, 200, 200);  // Light gray
        Color operatorBtn = new Color(255, 150, 50);  // Orange
        Color clearBtn = new Color(255, 80, 80);  // Red
        
        // Button positions
        int btnX = 65;
        int btnY = 140;
        int btnW = 40;
        int btnH = 40;
        int gap = 10;
        
        // Row 1: C, %, Backspace, ÷
        drawButton(g, btnX, btnY, btnW, btnH, "C", clearBtn);
        drawButton(g, btnX + btnW + gap, btnY, btnW, btnH, "%", operatorBtn);
        drawButton(g, btnX + 2*(btnW + gap), btnY, btnW, btnH, "⌫", operatorBtn);
        drawButton(g, btnX + 3*(btnW + gap), btnY, btnW, btnH, "÷", operatorBtn);
        
        // Row 2: 7, 8, 9, ×
        btnY += btnH + gap;
        drawButton(g, btnX, btnY, btnW, btnH, "7", numberBtn);
        drawButton(g, btnX + btnW + gap, btnY, btnW, btnH, "8", numberBtn);
        drawButton(g, btnX + 2*(btnW + gap), btnY, btnW, btnH, "9", numberBtn);
        drawButton(g, btnX + 3*(btnW + gap), btnY, btnW, btnH, "×", operatorBtn);
        
        // Row 3: 4, 5, 6, -
        btnY += btnH + gap;
        drawButton(g, btnX, btnY, btnW, btnH, "4", numberBtn);
        drawButton(g, btnX + btnW + gap, btnY, btnW, btnH, "5", numberBtn);
        drawButton(g, btnX + 2*(btnW + gap), btnY, btnW, btnH, "6", numberBtn);
        drawButton(g, btnX + 3*(btnW + gap), btnY, btnW, btnH, "-", operatorBtn);
        
        // Row 4: 1, 2, 3, +
        btnY += btnH + gap;
        drawButton(g, btnX, btnY, btnW, btnH, "1", numberBtn);
        drawButton(g, btnX + btnW + gap, btnY, btnW, btnH, "2", numberBtn);
        drawButton(g, btnX + 2*(btnW + gap), btnY, btnW, btnH, "3", numberBtn);
        drawButton(g, btnX + 3*(btnW + gap), btnY, btnW, btnH, "+", operatorBtn);
        
        // Row 5: 0 (wider), ., =
        btnY += btnH + gap;
        // 0 button (double width)
        g.setColor(numberBtn);
        g.fillRoundRect(btnX, btnY, btnW*2 + gap, btnH, 5, 5);
        g.setColor(Color.black);
        g.drawRoundRect(btnX, btnY, btnW*2 + gap, btnH, 5, 5);
        g.setFont(new Font("Arial", Font.BOLD, 20));
        g.drawString("0", btnX + 15, btnY + 27);
        
        drawButton(g, btnX + 2*(btnW + gap), btnY, btnW, btnH, ".", numberBtn);
        drawButton(g, btnX + 3*(btnW + gap), btnY, btnW, btnH, "=", operatorBtn);
    }
    
    void drawButton(Graphics g, int x, int y, int w, int h, String label, Color bg) {
        g.setColor(bg);
        g.fillRoundRect(x, y, w, h, 5, 5);  // Button fill
        g.setColor(Color.black);
        g.drawRoundRect(x, y, w, h, 5, 5);  // Button border
        g.setFont(new Font("Arial", Font.BOLD, 20));
        g.drawString(label, x + 12, y + 27);  // Text center mein
    }
}
```

---

### Q43. Write a program to create a simple animation of a car moving.

```java
import java.applet.Applet;
import java.awt.Graphics;
import java.awt.Color;

public class MovingCar extends Applet implements Runnable {
    int carX = 0;  // Car ki horizontal position
    Thread animator;
    
    public void init() {
        setBackground(Color.white);
        animator = new Thread(this);
    }
    
    public void start() {
        animator.start();
    }
    
    public void run() {
        while (carX < getWidth()) {
            carX += 5;  // Har frame mein 5 pixels aage
            repaint();
            try {
                Thread.sleep(50);  // Speed control
            } catch (Exception e) { }
        }
    }
    
    public void paint(Graphics g) {
        // Ground draw karo
        g.setColor(Color.green);
        g.fillRect(0, 280, getWidth(), 50);
        
        // Road draw karo
        g.setColor(Color.gray);
        g.fillRect(0, 250, getWidth(), 35);
        
        // Road pe white lines
        g.setColor(Color.white);
        for (int i = 0; i < getWidth(); i += 40) {
            g.fillRect(i, 265, 20, 5);
        }
        
        // Car body
        g.setColor(Color.red);
        g.fillRect(carX + 30, 190, 140, 50);  // Main body
        
        // Car roof
        g.fillRect(carX + 60, 160, 80, 35);
        
        // Windows
        g.setColor(Color.cyan);
        g.fillRect(carX + 65, 165, 30, 25);  // Left window
        g.fillRect(carX + 105, 165, 30, 25);  // Right window
        
        // Headlight
        g.setColor(Color.yellow);
        g.fillOval(carX + 160, 200, 15, 15);
        
        // Taillight
        g.setColor(Color.red);
        g.fillOval(carX + 30, 200, 12, 12);
        
        // Wheels
        g.setColor(Color.black);
        g.fillOval(carX + 45, 235, 35, 35);  // Back wheel
        g.fillOval(carX + 120, 235, 35, 35);  // Front wheel
        
        // Wheel centers (hubcaps)
        g.setColor(Color.gray);
        g.fillOval(carX + 52, 242, 20, 20);
        g.fillOval(carX + 127, 242, 20, 20);
    }
    
    public void stop() {
        animator = null;
    }
}
```

---

## 🎯 Section D: Short Answer Questions

### Q44. What is the difference between an Applet and an Application?

**Answer:**
```
┌────────────────────────────────────────────────────────────────────┐
│                        APPLET vs APPLICATION                         │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   APPLET                            APPLICATION                     │
│   ──────                            ───────────                     │
│                                                                     │
│   • Runs in web browser             • Standalone program           │
│   • No main() method               • Requires main() method        │
│   • Extends Applet class           • Any class can be entry point  │
│   • HTML file needed to run        • Direct execution              │
│   • Security sandbox (limited)     • Full system access             │
│   • Automatic lifecycle            • Manual control                 │
│     (init, start, stop, destroy)   •                                │
│   • Browser controls execution      • JVM controls execution        │
│   • Can read/write files? NO       • Can read/write files? YES     │
│   • Network access limited          • Full network access           │
│                                                                     │
│   Example:                           Example:                       │
│   <applet code="Demo.class"        java Demo (direct run)         │
│           width="300" height="200">                                │
│   </applet>                                                         │
│                                                                     │
└────────────────────────────────────────────────────────────────────┘
```

---

### Q45. Explain the Applet lifecycle methods with their purposes.

**Answer:**
```
┌────────────────────────────────────────────────────────────────────┐
│                    APPLET LIFECYCLE - DETAILED                       │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   1. init()                                                        │
│      ─────────                                                      │
│      • Called ONCE when applet first loads                          │
│      • Best place for:                                              │
│        - Variable initialization                                    │
│        - Loading images                                             │
│        - Creating components (buttons, text fields)                 │
│        - Setting initial state                                      │
│      • NOT called again during lifecycle                            │
│                                                                     │
│   2. start()                                                       │
│      ───────                                                        │
│      • Called after init() and when applet becomes visible          │
│      • Called MULTIPLE times (every time user returns to page)       │
│      • Best place for:                                              │
│        - Starting animations                                        │
│        - Starting threads                                           │
│        - Resuming activities                                        │
│                                                                     │
│   3. paint(Graphics g)                                             │
│      ─────────────────                                             │
│      • Called to render content on screen                           │
│      • Called MULTIPLE times                                       │
│        - After init()                                              │
│        - After start()                                             │
│        - After repaint()                                            │
│      • Graphics object automatically provided                       │
│                                                                     │
│   4. stop()                                                        │
│      ─────                                                         │
│      • Called when applet becomes invisible                         │
│      • User leaves page, minimizes browser                          │
│      • Best place for:                                              │
│        - Stopping animations                                        │
│        - Stopping threads                                           │
│        - Pausing activities                                         │
│      • Called MULTIPLE times                                       │
│                                                                     │
│   5. destroy()                                                     │
│      ─────────                                                     │
│      • Called ONCE when applet is being removed                     │
│      • Browser closing or navigating away                           │
│      • Best place for:                                              │
│        - Releasing resources                                        │
│        - Cleaning up                                                │
│        - Final cleanup                                              │
│                                                                     │
└────────────────────────────────────────────────────────────────────┘
```

---

### Q46. What is the difference between draw and fill methods?

**Answer:**
```
┌────────────────────────────────────────────────────────────────────┐
│                    DRAW vs FILL METHODS                              │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Every Graphics shape method has TWO versions:                     │
│                                                                     │
│   ┌─────────────────┐  ┌─────────────────┐                        │
│   │  drawRect()     │  │  fillRect()     │                        │
│   │  Outline trace  │  │  Solid fill     │                        │
│   │  ┌─────────┐    │  │  ┌███████████┐  │                        │
│   │  │         │    │  │  │████████████│  │                        │
│   │  │         │    │  │  │████████████│  │                        │
│   │  └─────────┘    │  │  └███████████┘  │                        │
│   └─────────────────┘  └─────────────────┘                        │
│                                                                     │
│   Complete List:                                                    │
│   ─────────────                                                     │
│   drawRect()     vs fillRect()     → Rectangle                     │
│   drawOval()     vs fillOval()     → Oval/Circle                   │
│   drawArc()      vs fillArc()      → Arc                           │
│   drawPolygon()  vs fillPolygon()  → Polygon                       │
│   drawRoundRect()                  → Rounded rectangle (only draw) │
│   draw3DRect()    vs fill3DRect()  → 3D effect rectangle           │
│                                                                     │
│   Note: For filled shapes, fill color = current setColor            │
│                                                                     │
└────────────────────────────────────────────────────────────────────┘
```

---

### Q47. What are the different Layout Managers in AWT?

**Answer:**
```
┌────────────────────────────────────────────────────────────────────┐
│                    AWT LAYOUT MANAGERS                               │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   1. FlowLayout (DEFAULT for Applet)                              │
│      ─────────────────────────────────                             │
│      Components arranged left-to-right, then wrap                  │
│      ┌────┐┌────┐┌────┐                                           │
│      │ A  ││ B  ││ C  │                                           │
│      └────┘└────┘└────┘                                           │
│                                                                     │
│   2. BorderLayout (DEFAULT for Frame)                              │
│      ──────────────────────────────                                  │
│      ┌──────────────┐                                              │
│      │    NORTH     │                                              │
│      ├────┬───┬────┤                                              │
│      │WEST│Cen│EAST│                                              │
│      ├────┴───┴────┤                                              │
│      │    SOUTH    │                                              │
│      └──────────────┘                                              │
│                                                                     │
│   3. GridLayout                                                    │
│      ──────────                                                    │
│      Equal-sized cells in rows and columns                          │
│      ┌────┬────┬────┐                                              │
│      │ 1  │ 2  │ 3  │                                              │
│      ├────┼────┼────┤                                              │
│      │ 4  │ 5  │ 6  │                                              │
│      └────┴────┴────┘                                              │
│                                                                     │
│   4. GridBagLayout                                                 │
│      ─────────────                                                  │
│      Complex grid with flexible cell sizes                          │
│      Most powerful but complex                                     │
│                                                                     │
│   5. CardLayout                                                    │
│      ───────────                                                   │
│      Shows one component at a time (like playing cards)             │
│                                                                     │
│   6. null (Absolute Positioning)                                    │
│      ──────────────────────────                                     │
│      No layout management, use exact x,y coordinates               │
│                                                                     │
└────────────────────────────────────────────────────────────────────┘
```

---

### Q48. What is the purpose of repaint() and when should we use it?

**Answer:**
```
┌────────────────────────────────────────────────────────────────────┐
│                    REPAINT() METHOD                                  │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Flow Diagram:                                                     │
│   ────────────                                                      │
│                                                                     │
│   repaint() ──→ update() ──→ paint(Graphics g)                     │
│                                                                     │
│   What each step does:                                              │
│   ───────────────────                                               │
│                                                                     │
│   repaint():                                                        │
│   • Public method jo aap call karte ho                              │
│   • Asks JVM to repaint the component ASAP                          │
│   • Thread-safe way to request repaint                              │
│                                                                     │
│   update():                                                         │
│   • Protected method (usually don't call directly)                   │
│   • Clears the component with background color                      │
│   • Calls paint()                                                   │
│                                                                     │
│   paint(Graphics g):                                               │
│   • Protected method jo aap override karte ho                       │
│   • Actually draws the content                                      │
│   • Graphics object milta hai parameter mein                       │
│                                                                     │
│   When to use repaint()?                                            │
│   ─────────────────────                                             │
│                                                                     │
│   ✅ Animation (moving objects)                                      │
│   ✅ Game development                                               │
│   ✅ Real-time updates                                              │
│   ✅ User interaction effects                                       │
│   ✅ Clock/Time display                                             │
│   ✅ Following mouse movement                                       │
│                                                                     │
│   Example - Moving Ball Animation:                                  │
│   ────────────────────────────────                                  │
│                                                                     │
│   public void run() {                                               │
│       while (running) {                                            │
│           x += dx;    // Update position                           │
│           y += dy;                                                 │
│           repaint();  // Request redraw                            │
│           Thread.sleep(30);                                        │
│       }                                                            │
│   }                                                                │
│                                                                     │
└────────────────────────────────────────────────────────────────────┘
```

---

### Q49. What are the commonly used Colors in Java AWT?

**Answer:**
```
┌────────────────────────────────────────────────────────────────────┐
│                    COMMON COLORS IN JAVA                            │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Predefined Colors (Color.class constants):                        │
│   ──────────────────────────────────────────                       │
│                                                                     │
│   Color.black      → RGB(0, 0, 0)         │ Dark colors:          │
│   Color.white      → RGB(255, 255, 255)  │                       │
│   Color.red        → RGB(255, 0, 0)       │ Color.darkGray       │
│   Color.green      → RGB(0, 255, 0)       │ Color.gray           │
│   Color.blue       → RGB(0, 0, 255)       │ Color.lightGray      │
│   Color.yellow     → RGB(255, 255, 0)       │                      │
│   Color.orange      → RGB(255, 165, 0)       │                      │
│   Color.pink        → RGB(255, 175, 175)    │                      │
│   Color.cyan        → RGB(0, 255, 255)       │                      │
│   Color.magenta     → RGB(255, 0, 255)       │                      │
│   Color.gray       → RGB(128, 128, 128)     │                      │
│                                                                     │
│   Custom Colors (Using RGB values):                                 │
│   ───────────────────────────────────                              │
│                                                                     │
│   new Color(int r, int g, int b)                                  │
│                                                                     │
│   Where r, g, b are from 0 to 255                                  │
│                                                                     │
│   Examples:                                                         │
│   • Saffron: new Color(255, 153, 51)                               │
│   • Indian Green: new Color(19, 136, 8)                             │
│   • Sky Blue: new Color(135, 206, 235)                              │
│   • Navy Blue: new Color(0, 0, 128)                                │
│   • Maroon: new Color(128, 0, 0)                                   │
│   • Olive: new Color(128, 128, 0)                                  │
│   • Purple: new Color(128, 0, 128)                                 │
│   • Teal: new Color(0, 128, 128)                                   │
│                                                                     │
│   Note: RGB(255, 255, 255) = White (all light)                     │
│         RGB(0, 0, 0) = Black (no light)                            │
│                                                                     │
└────────────────────────────────────────────────────────────────────┘
```

---

### Q50. What is the coordinate system in Java Graphics?

**Answer:**
```
┌────────────────────────────────────────────────────────────────────┐
│                JAVA GRAPHICS COORDINATE SYSTEM                      │
├────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   Origin (0, 0) is at TOP-LEFT corner of component!                 │
│                                                                     │
│   Y                                                                    │
│   │                                                                 │
│   0 ──────── X                                                     │
│   │                    Point P = (x, y)                             │
│   │  (0,0)              - x = horizontal distance from left        │
│   │   ┌───┐            - y = vertical distance from top           │
│   │   │ P │                                                        │
│   │   └───┘                                                        │
│   │                                                                 │
│   │     (150, 100)                                                 │
│   │        ┌───┐                                                  │
│   └────────│   │─────────────────────────────────────────────────►
│            └───┘                                                   │
│                                                                     │
│   X increases → Right (positive)                                   │
│   Y increases → Down (positive)                                     │
│                                                                     │
│   This is DIFFERENT from Cartesian coordinates where:               │
│   • Y increases upward                                             │
│   • Origin is at bottom-left                                       │
│                                                                     │
│   Example Points:                                                  │
│   ───────────────                                                  │
│   (0, 0)    → Top-left corner                                      │
│   (100, 0)  → 100 pixels from left, at top                        │
│   (0, 100)  → 100 pixels from top, at left                        │
│   (50, 50)  → Center of 100x100 area starting at top-left          │
│                                                                     │
│   Width and Height:                                                │
│   ─────────────────                                                │
│   getWidth()  → Component ki total width                           │
│   getHeight() → Component ki total height                          │
│   (getWidth()-1, getHeight()-1) → Bottom-right corner              │
│                                                                     │
└────────────────────────────────────────────────────────────────────┘
```

---

## 🎯 Section E: Common Mistakes & Tricky Questions

### Q51. Common Mistake: Using width/height instead of end coordinates for drawLine

**Question:** Why doesn't `g.drawLine(50, 50, 100, 100)` draw a 100x100 square?

> **Hinglish - Explanation:**
> 
> `drawLine(x1, y1, x2, y2)` mein aap end coordinates dete ho, NOT width aur height!
> 
> - Start: (50, 50)
> - End: (100, 100)
> - **Actual length:** √((100-50)² + (100-50)²) = 70.7 pixels (diagonal!)
> 
> **Square draw karne ka sahi tarika:**
> ```java
> g.drawRect(50, 50, 100, 100);  // Rectangle with 100x100 size
> // OR 4 lines likho
> g.drawLine(50, 50, 150, 50);   // Top: x from 50 to 150 = 100 pixels
> g.drawLine(150, 50, 150, 150); // Right: y from 50 to 150 = 100 pixels
> g.drawLine(150, 150, 50, 150); // Bottom
> g.drawLine(50, 150, 50, 50);   // Left
> ```

---

### Q52. Common Mistake: Forgetting that Strings are drawn from baseline

**Question:** Why does text appear cut off at the top?

> **Hinglish - Explanation:**
> 
> `drawString(text, x, y)` mein y parameter text ki **baseline** hai, NOT top edge!
> 
> ```
>       ↓ y coordinate (baseline)
>       │
>   ┌───┴──────┐
>   │  Text    │  ← Text top edge (ascent above baseline)
>   │──────────│  ← Baseline (where text sits)
>   │          │  ← Descent below baseline
>   └──────────┘
> ```
> 
> **Sahi tarika:**
> ```java
> // Text ko center mein align karne ke liye
> FontMetrics fm = g.getFontMetrics();
> int stringWidth = fm.stringWidth("Hello");
> int stringHeight = fm.getHeight();
> int x = (getWidth() - stringWidth) / 2;  // Center X
> int y = (getHeight() + stringHeight) / 2; // Center Y (baseline adjust)
> g.drawString("Hello", x, y);
> ```

---

### Q53. Tricky Question: What is the output?

```java
public void paint(Graphics g) {
    g.setColor(Color.red);
    g.fillRect(50, 50, 100, 100);
    
    g.setColor(Color.blue);
    g.drawRect(50, 50, 100, 100);
}
```

> **Answer:** Blue outline rectangle, RED filled rectangle (red dikhai dega kyunki drawRect baad mein aata hai lekin woh sirf outline hai)

---

### Q54. Tricky Question: What is the output?

```java
public void paint(Graphics g) {
    for(int i = 0; i < 5; i++) {
        g.drawOval(100, 100, 50, 50);
    }
}
```

> **Answer:** Sirf ek circle dikhegi! Saare circles same position (100,100) pe hain, toh overlapping hain.

---

### Q55. Tricky Question: What is drawn?

```java
g.drawOval(50, 50, 100, 100);
g.setColor(Color.red);
g.fillOval(50, 50, 100, 100);
```

> **Answer:** Red filled circle (second command fill karta hai, outline background color ki reh jati hai)

---

## 🎯 Final Practice Tips

### Key Points to Remember:

```
╔═══════════════════════════════════════════════════════════════════╗
║                    APPLET & GRAPHICS - KEY POINTS                  ║
╠═══════════════════════════════════════════════════════════════════╣
║                                                                   ║
║  1. APPLET LIFECYCLE:                                            ║
║     init() → start() → paint() → stop() → destroy()             ║
║                                                                   ║
║  2. DRAWING METHODS:                                             ║
║     draw = outline, fill = filled                                 ║
║     drawOval() = circle (when w==h)                              ║
║     drawLine(x1,y1,x2,y2) = end coordinates, NOT width/height    ║
║                                                                   ║
║  3. COORDINATE SYSTEM:                                          ║
║     Origin at top-left (0,0)                                     ║
║     X increases → right                                          ║
║     Y increases → down                                           ║
║                                                                   ║
║  4. REPAINT FLOW:                                               ║
║     repaint() → update() → paint(Graphics g)                      ║
║                                                                   ║
║  5. LAYOUT MANAGERS:                                            ║
║     Applet default = FlowLayout                                   ║
║     Frame default = BorderLayout                                  ║
║                                                                   ║
║  6. COLORS:                                                     ║
║     Predefined: Color.red, Color.blue, etc.                      ║
║     Custom: new Color(r, g, b) where 0-255                      ║
║                                                                   ║
║  7. TEXT:                                                        ║
║     drawString(text, x, y) - y is BASELINE                       ║
║                                                                   ║
║  8. APPLET vs APPLICATION:                                      ║
║     Applet has NO main() method                                  ║
║     Application has main() method                                ║
║                                                                   ║
╚═══════════════════════════════════════════════════════════════════╝
```

### Common Programs to Practice:

1. ✅ Smiley Face
2. ✅ Indian Flag with Chakra
3. ✅ Traffic Light
4. ✅ House with Sun
5. ✅ Calculator (buttons)
6. ✅ Bouncing Ball Animation
7. ✅ Car Moving Animation
8. ✅ Digital Clock
9. ✅ Moving Car
10. ✅ Simple Game (Paddle/Ball)

---

## ❤️ Made with Love

**CodersJaunt** | *Where every coder takes the leap!*

Made with ❤️ by [@mit](https://github.com/SwagCode4U/java-iv-exam-hacks)

---

![Visitor Count](https://visitor-badge.glitch.me/badge?page_id=CodersJaunt.Day6Questions)
