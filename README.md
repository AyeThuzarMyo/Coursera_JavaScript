# Coursera_Functional_JavaScript
# JavaScript Functional Logic & Scoping Lab   
Failed Test 1: Not logging the consoleStyler() variables   
Passed Test 2: successfully logged celebrateStyler() variables   
Failed Test 3: Not calling consoleStyler() and celebrateStyler()   
Failed Test 4: Not calling styleAndCelebrate()  

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

**Key Takeaways  
Block Scope vs. Function Scope:** let is restricted to the block {} it is defined in, whereas var is available throughout the entire function.  
**The %c Specifier:** Learned how to pass CSS strings into console.log to create custom UI elements in the browser debugger.  
**Template Literals:** Used backticks (`) to cleanly inject variables into strings without complex concatenation.  

---

**How to Run the Code**  
1. filename: functionalprogramming.js  
   Open your browser's Developer Tools (F12)  
2. Paste the code into the Console.  
