The "engine" that runs JavaScript in your browser is a piece of software inside the browser. Chrome uses V8, Firefox uses SpiderMonkey, Safari uses JavaScriptCore. Node.js also uses V8 — that's how JS runs outside a browser.

You have three places to write and run JavaScript.
### a) Browser Console (fastest): 
 1. Open any webpage.
 2. Press `F12` (or right-click → Inspect).
 3. Click the **Console** tab.
 4. Type: `2 + 2` and press Enter. You'll see `4`.
This is perfect for trying out small snippets.

### b) VS Code + a `.js` file:
 1. Download **VS Code** (free) from code.visualstudio.com.
 2. Create a folder, open it in VS Code, create a file called `app.js`.
 3. Write your code inside it.

### c) Node.js (to run `.js` files outside the browser):
 1. Install **Node.js** from nodejs.org.
 2. Open terminal in your folder.
 3. Run: `node app.js`
You'll see the output in the terminal.

console.log() prints something to the console. It is the most-used tool in a JS developer's life.
```javascript
console.log("Hello, World!");
console.log(42);
console.log("My name is", "Aman", "and I am", 25, "years old");
```
You can pass **multiple values** separated by commas, and `console.log` will print them with spaces between.

**Other useful console methods:**

```javascript
console.log("Normal message");
console.warn("This is a warning");      // shown in yellow in browsers
console.error("This is an error");      // shown in red
console.table([1, 2, 3]);               // prints data as a table
```

## 4. Comments

Comments are notes for humans. JavaScript ignores them.

```jsx
// This is a single-line comment

/*
   This is a
   multi-line comment
*/

console.log("Hello"); // You can also comment at the end of a line
```

**Why comment?**

- To remind yourself what code does.
- To temporarily disable code while testing.
- To explain *why* something is done a certain way.

## 5. Variables — The Heart of Programming

A **variable** is a named box where you store a value. Later, you can use the name to get the value back, or change it.

JavaScript has **three keywords** to declare variables: `var`, `let`, and `const`.

```jsx
var age = 25;
let name = "Aman";
const PI = 3.14159;
```

### Declaration vs Initialization

- **Declaration:** creating the variable. → `let x;`
- **Initialization:** giving it a value. → `x = 10;`
- You can combine both. → `let x = 10;`

let city;              // declared, value is undefined
console.log(city);     // undefined
city = "Bhopal";       // initialized now
console.log(city);     // Bhopal


### Basic Differences Between var, let, const

| Feature | `var` | `let` | `const` |
| --- | --- | --- | --- |
| Can re-assign? | Yes | Yes | **No** |
| Can re-declare in same scope? | Yes | No | No |
| Scope | Function | Block | Block |
| Hoisted? | Yes (as `undefined`) | Yes (TDZ) | Yes (TDZ) |