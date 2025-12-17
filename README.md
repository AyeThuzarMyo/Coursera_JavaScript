# Coursera_JavaScript
# JavaScript Functional Logic & Scoping Lab
This project explores functional programming patterns and the critical differences between variable declarations in JavaScript.
---

The "Var vs Let" Discovery
During the development of this project, a key technical challenge was encountered regarding **Variable Scoping**.
**Initial Approach:** Using var for all variable declarations.
**Result:** Failed the automated test suite.
**Solution:** Refactored the consoleStyler function to use let.
**The "Why":** The lab environment requires let for the style variable because it is being updated dynamically using the += operator within a block. let provides block-scoping, making the code more predictable and compliant with modern ES6 standards.

---

**Final Code Implementation
Task 1: Styled Console Message (Modern let)**
The consoleStyler uses let to allow for the reassignment and building of the CSS string.

```js
function consoleStyler(color, background, fontSize, txt) {
    let message = "%c" + txt;
    let style = `color: ${color};`;
    style += `background: ${background};`; // Updating the variable
    style += `font-size: ${fontSize};`;
    console.log(message, style);
}
```

**Task 2: Celebratory Message (Legacy var)**
The celebrateStyler utilizes var to demonstrate function-scoped declarations for static styles.

```js
function celebrateStyler(reason) {
    var fontStyle = "color: tomato; font-size: 50px";
    
    if (reason === "birthday") {
        console.log(`%cHappy birthday`, fontStyle);
    } else if (reason === "champions") {
        console.log(`%cCongrats on the title!`, fontStyle);
    } else {
        console.log(reason);
    }
}
```

**Task 3 & 4: Composition**
The styleAndCelebrate function combines these two behaviors into a single reusable utility.

---

Comparison: let vs var
Understanding the variables used in this project:

| Feature | let (Used in Task 1) | var (Used in Task 2) |
| **Scope** | Block Scoped (within { }) | Function Scoped |
| **Re-declaration** | Cannot be re-declared in the same scope | Can be re-declared |
| **Hoisting** | Hoisted, but not initialized | Hoisted and initialized as undefined |
| **Modern Usage** | Preferred for modern development | Generally avoided in modern JS |

---

**How to Run the Code**
1. Copy the entire script from functionalprogramming.js.
2. Open your browser's Developer Tools (F12 or Ctrl+Shift+I).
3. Navigate to the Console tab.
4. Paste the code and hit Enter.

**Expected Output**
When you run the final invocation: styleAndCelebrate('ef7c8e', 'fae8e0', '30px', 'You made it!', 'champions');

You will see:
"You made it!" styled with a pinkish text color and a cream background.
"Congrats on the title!" in large, tomato-colored text.
