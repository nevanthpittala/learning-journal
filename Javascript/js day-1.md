## 1. Introduction to JavaScript

- JavaScript was created by Brendan Eich in 1995.
- It is used to add interactivity to websites.
- Today JavaScript is used for:
  - Frontend development
  - Backend development (Node.js)
  - Mobile apps
  - Desktop apps

JavaScript runs using engines:
- Chrome → V8
- Firefox → SpiderMonkey
- Safari → JavaScriptCore

---

## 2. Running JavaScript

Ways to run JS:

1. Browser Console
2. VS Code `.js` files
3. Node.js

Run a JS file:

```bash
node app.js
```

---

## 3. console.log()

Used to print output to the console.

```javascript
console.log("Hello World");
console.log(42);
console.log(true);
```

Other console methods:

```javascript
console.warn("Warning");
console.error("Error");
console.table([1,2,3]);
```

---

## 4. Comments

Single-line:

```javascript
// comment
```

Multi-line:

```javascript
/*
multi line comment
*/
```

---

# Variables

Variables store values.

Types:

```javascript
var age = 20;
let name = "Aman";
const PI = 3.14;
```

Modern JS:
- Prefer `const`
- Use `let` when value changes
- Avoid `var`

---

## Declaration vs Initialization

Declaration:

```javascript
let city;
```

Initialization:

```javascript
city = "Bhopal";
```

Example:

```javascript
let city;
console.log(city); // undefined

city = "Bhopal";
console.log(city);
```

---

# Data Types

## Primitive Types

| Type | Example |
|---|---|
| string | "Hello" |
| number | 10, 5.5 |
| boolean | true / false |
| null | empty value |
| undefined | no value assigned |
| symbol | unique id |
| bigint | large numbers |

## Non Primitive

- Objects
- Arrays
- Functions

---

# typeof Operator

Checks datatype.

```javascript
typeof "hello"; 
// string

typeof 10;
// number

typeof null;
// object (JS bug)
```

---

# Type Conversion

Manual conversion:

```javascript
Number("42");
String(100);
Boolean("hello");
```

Automatic conversion:

```javascript
"5" + 3 // "53"

"5" - 3 // 2
```

---

# Truthy and Falsy

Falsy values:

```
false
0
""
null
undefined
NaN
```

Everything else is truthy.

---

# Operators

## Arithmetic

```javascript
+
-
*
/
%
**
```

## Comparison

Always prefer:

```javascript
=== 
!==
```

Avoid:

```javascript
==
!=
```

---

# Logical Operators

AND:

```javascript
true && false
```

OR:

```javascript
true || false
```

NOT:

```javascript
!true
```

---

# Strings

Creating strings:

```javascript
let name = "Aman";
```

Template literals:

```javascript
console.log(`Hello ${name}`);
```

Useful methods:

```javascript
toUpperCase()
toLowerCase()
includes()
slice()
replace()
split()
trim()
```

Strings are immutable.

---

# Numbers

JavaScript has one number type.

Useful methods:

```javascript
Number()
parseInt()
parseFloat()
toFixed()
```

Math:

```javascript
Math.round()
Math.floor()
Math.ceil()
Math.random()
Math.max()
Math.min()
```

---

# Conditionals

if else:

```javascript
if(condition){

}else{

}
```

switch:

```javascript
switch(value){
 case 1:
 break;
}
```

---

# Loops

for:

```javascript
for(let i=0;i<5;i++){
 console.log(i);
}
```

while:

```javascript
while(condition){

}
```

do while:

```javascript
do{

}while(condition)
```

---

# Loop Control

Stop loop:

```javascript
break;
```

Skip iteration:

```javascript
continue;
```

---

# User Input

Browser:

```javascript
let name = prompt("Enter name");
```

Convert input:

```javascript
let age = Number(prompt("Age"));
```

---

## Learning Status ✅

Covered:
- JS basics
- Variables
- Data types
- Operators
- Strings
- Numbers
- Conditions
- Loops