# ASE_BOOSE_Documentation
# BOOSE Application – Full Documentation

Welcome to the official documentation for the **BOOSE Interpreter Application**.  
This document contains everything required to understand, use, and extend the BOOSE project.

---

## 📌 1. Overview:

**BOOSE** is a graphical interpreter that reads simple text commands and draws shapes on a canvas.  
It is designed for educational purposes to demonstrate:

- Parsing commands  
- Object-oriented programming  
- Canvas rendering  
- Command factories  
- Unit testing  

The system supports drawing shapes, moving the cursor, setting pen colors, and resetting the canvas.

---

## 📌 2. Features:

- Move cursor using `moveto`
- Draw lines using `drawto`
- Change pen color using `pen r,g,b`
- Draw shapes: `circle`, `rect`
- Reset canvas to default state
- Extensible command system via interfaces
- Supports custom command factory (`ICommandFactory`)
- XML code documentation generated from C#

---

## 📌 3. How BOOSE Works (Simple Explanation):

BOOSE reads user input line-by-line:

1. User enters text like:
   moveto 50,100
   pen 255,0,0
   circle 100

2. `AppCommandFactory` converts these into command objects.
3. Each command updates the `AppCanvas` instance.
4. The canvas redraws shapes using `Graphics`.

---

## 📌 4. Command Reference:
Command	Format	Description
moveto	moveto x,y	Moves cursor to (x,y)
drawto	drawto x,y	Draws a line from current position to (x,y)
pen	pen r,g,b	Sets pen color (RGB values 0–255)
circle	circle radius	Draws a circle with given radius
rect	rect width,height	Draws a rectangle
reset	reset	Clears canvas and resets cursor
fill on/off	fill on / fill off	Enables or disables filled shapes

Note: Additional commands can be added using the command interface.

## 📌 5. Input Rules:

Coordinates must be comma-separated

✔ moveto 100,150

❌ moveto 100 150

Pen color format: pen R,G,B

Commands are case-insensitive

Extra spaces are ignored


## 📌 6. Application Structures:

myBOOSEapp/
│
├── AppCanvas.cs            # Drawing logic, pen color, shapes
├── AppCommandFactory.cs    # Converts text into command objects
├── MoveToCommand.cs        # Moves cursor
├── DrawToCommand.cs        # Draws line
├── SetColourCommand.cs     # Sets the pen colour in RGB format
├── CircleCommand.cs        # Draws circle
├── RectCommand.cs          # Draws rectangle
├── WriteCommand.cs         # Writes text on canvas
├── Program.cs              # Windows Form UI



---

## 📌 7. Examples Program:
moveto 100,150
pen 0,0,255
circle 150

pen 255,0,0
moveto 150,50
rect 150,100

moveto 150,200
pen 0,0,255
circle 250

pen 255,0,0
moveto 200,250
rect 200,150


This will draw:

- Blue circle  
- Red rectangle  
- Another blue circle  
- Another red rectangle  

---

## 📌 8. Reset Functionality

`reset` command runs:

public void Reset()
{
    penColor = Color.Black;
    Xpos = 0;
    Ypos = 0;
    Clear();
}

This resets:

Pen color → black

Cursor → (0,0)

Canvas → fully cleared


## 📌 9. Troubleshooting:
Issue	Cause	Solution
Shapes not appearing	Wrong coordinates	Keep values inside canvas size
Color not changing	Invalid RGB values	Use numbers between 0–255
Commands ignored	Wrong syntax	Use comma-separated format
App crashes	Missing command factory mapping	Ensure all commands are registered

## 📌 10. XML Documentation:
👉 Click here to download BOOSE XML Documentation

(Upload your XML file to GitHub Pages folder to activate this link)

## 📌 11. Author:

Name: MD. Mohid Alam
Project: ASE BOOSE Assignment-2025
Documentation Hosted At:
👉 https://mdmohid.github.io/ASE_BOOSE_Documentation/

© 2025 BOOSE Application – All Rights Reserved

