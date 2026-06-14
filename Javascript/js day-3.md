## 1. How JavaScript Works

- JavaScript is **single-threaded**
  - Has one Call Stack
  - Executes one task at a time

- JavaScript is **synchronous by default**
  - Runs code line by line from top to bottom

- Modern JS uses **JIT Compilation**
  - Starts by interpreting code
  - Optimizes frequently used code into machine code

> Async does not mean JS is multi-threaded. Async work is handled by Browser/Node environment.

---

## 2. JavaScript Engine

JS needs an engine to run.

Examples:
- V8 → Chrome, Node.js, Edge
- SpiderMonkey → Firefox
- JavaScriptCore → Safari

Execution pipeline:

Code  
↓  
Tokenizing  
↓  
Parsing → AST  
↓  
JIT Compilation  
↓  
Execution

V8:
- Ignition → converts code to bytecode
- TurboFan → optimizes hot code

---

# 3. Execution Context (EC)

Execution Context = environment where JS code runs.

It stores:
- Variables
- Functions
- Value of `this`

Types:

### Global Execution Context (GEC)
- Created when program starts
- Only one exists

### Function Execution Context (FEC)
- Created every time a function is called

---

## Execution Context Phases

### 1. Creation Phase
Before code runs:

- `var` → memory allocated with `undefined`
- Function declarations → stored completely
- `this` value assigned

### 2. Execution Phase

- Code runs line by line
- Values are assigned
- Functions execute

This is the reason behind **hoisting**.

---

# 4. Call Stack

Call Stack tracks function execution.

Rule:
LIFO → Last In First Out

Function called:
⬇️ pushed into stack

Function finished:
⬆️ removed from stack

Example:

one()
 → two()
   → three()

Stack removal:

three finishes
two finishes
one finishes

Output:
three
two
one

---

## Stack Overflow

Happens when stack keeps growing without stopping.

Example:

Infinite recursion

```js
function loop(){
 loop();
}