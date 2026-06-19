# 1. Modern ES6+ Features

## 🔹 Destructuring

Destructuring allows extracting values from arrays or objects into variables.

### Array Destructuring

```js
const numbers = [10, 20, 30];

const [a, b, c] = numbers;

console.log(a); // 10
```

### Object Destructuring

```js
const user = {
  name: "Aman",
  age: 22
};

const { name, age } = user;
```

---

## Default Values

Used when value is `undefined`.

```js
const { role = "user" } = {};

console.log(role);
// user
```

> Default values do not work for `null`, `0`, or empty strings.

---

## Rename Variables

```js
const { name: userName } = user;

console.log(userName);
```

---

## Nested Destructuring

```js
const student = {
  info:{
    city:"Delhi"
  }
};

const {
 info:{city}
} = student;
```

---

## Function Parameter Destructuring

```js
function greet({name, age=18}){
 console.log(name, age);
}

greet({name:"Aman"});
```

---

## Swap Variables

```js
let a = 1;
let b = 2;

[a,b] = [b,a];
```

---

# 2. Spread & Rest Operator (...)

Same syntax but different purpose.

---

## Spread Operator

Expands values.

### Arrays

```js
const a=[1,2];
const b=[3,4];

const result=[...a,...b];
```

Output:

```js
[1,2,3,4]
```

---

### Objects

```js
const user={
 name:"Aman"
};

const updated={
 ...user,
 age:22
};
```

Used heavily in React state updates.

---

### Function Arguments

```js
const nums=[1,5,10];

Math.max(...nums);
```

---

# Rest Operator

Collects remaining values.

```js
function sum(...numbers){

 return numbers.reduce(
 (a,b)=>a+b
 );

}
```

---

Rest in destructuring:

```js
const [first,...others]=[1,2,3];

console.log(others);
// [2,3]
```

---

# 3. Template Literals

Use backticks `` ` ` ``.

```js
const name="Aman";

console.log(
`Hello ${name}`
);
```

Benefits:

- Variable interpolation
- Multi-line strings
- Cleaner code

---

# 4. Optional Chaining (?.)

Prevents crashes when accessing missing properties.

Without:

```js
user.address.city
// Error
```

With:

```js
user.address?.city
```

Output:

```js
undefined
```

Works with:

Objects

```js
user?.profile?.name
```

Functions

```js
obj.method?.()
```

Arrays

```js
arr?.[0]
```

---

# 5. Nullish Coalescing (??)

Returns fallback only for:

- null
- undefined

Example:

```js
let age = 0;

console.log(age ?? 18);
```

Output:

```js
0
```

Difference:

| Operator | Checks |
|-|-|
| || | All falsy values |
| ?? | Only null / undefined |

---

# 6. Short Circuit Evaluation

## OR ||

Returns first truthy value.

```js
console.log(
0 || "Guest"
);

// Guest
```

---

## AND &&

Runs only if condition is true.

```js
isLoggedIn &&
console.log("Welcome");
```

React usage:

```jsx
{isLoggedIn && <Dashboard />}
```

---

# 7. Logical Assignment Operators

## ||=

Assign if value is falsy.

```js
username ||= "Guest";
```

---

## ??=

Assign only if null or undefined.

```js
theme ??= "dark";
```

---

## &&=

Assign only if value is truthy.

```js
active &&= false;
```

---

# JavaScript Modules 📦

Used to split code into multiple reusable files.

---

# ES Modules

## Named Export

```js
export function add(a,b){
 return a+b;
}
```

Import:

```js
import {add} from "./math.js";
```

---

## Default Export

Only one per file.

```js
export default User;
```

Import:

```js
import User from "./User.js";
```

---

## Rename Imports

```js
import {add as sum}
from "./math.js";
```

---

## Import Everything

```js
import * as Math
from "./math.js";
```

---

# CommonJS (Node.js)

Older module system.

Export:

```js
module.exports = add;
```

Import:

```js
const add=require("./add");
```

---

# Dynamic Imports

Load files only when needed.

```js
const module =
await import("./chart.js");
```

Benefits:

- Faster loading
- Code splitting
- Better performance

---

# Error Handling ⚠️

Used to prevent app crashes.

---

# try catch finally

```js
try{

 riskyCode();

}
catch(error){

 console.log(error.message);

}
finally{

 console.log("done");

}
```

---

# Throw Custom Errors

```js
throw new Error(
"Something failed"
);
```

---

# Built-in Errors

| Error | Meaning |
|-|-|
| TypeError | Wrong data type |
| ReferenceError | Variable missing |
| SyntaxError | Invalid syntax |
| RangeError | Invalid range |

---

# Custom Error Class

```js
class ValidationError extends Error{

 constructor(msg){
  super(msg);
 }

}
```

Used for professional error handling.

---

# Useful Built-ins

## Date Object

Create date:

```js
const now =
new Date();
```

Get values:

```js
date.getFullYear();

date.getMonth();
```

⚠️ Month starts from 0.

January = 0  
December = 11

---

# Browser Storage 💾

Stores data after page refresh.

---

# localStorage

Permanent until removed.

Save:

```js
localStorage.setItem(
"name",
"Aman"
);
```

Read:

```js
localStorage.getItem(
"name"
);
```

Remove:

```js
localStorage.removeItem(
"name"
);
```

---

## Store Objects

Convert object → string

```js
localStorage.setItem(
"user",
JSON.stringify(user)
);
```

Read:

```js
JSON.parse(
localStorage.getItem("user")
);
```

---

# sessionStorage

Same API but removed when tab closes.

---

# Cookies 🍪

Small browser storage.

Used mainly for:

- Authentication
- Sessions

Difference:

| Feature | Cookie | localStorage |
|-|-|-|
| Size | Small | Larger |
| Sent to server | Yes | No |
| Usage | Auth | Client data |

---

# JavaScript Best Practices ⭐

## 1. Small Functions

One function = one task.

```js
validateUser();

saveUser();
```

---

## 2. Avoid Magic Numbers

Bad:

```js
if(time>86400)
```

Good:

```js
const DAY=86400;
```

---

## 3. Use Early Return

Avoid deep nesting.

```js
if(!user)
 return;

processUser();
```

---

## 4. Naming Rules

| Type | Convention |
|-|-|
| Variables | camelCase |
| Functions | camelCase |
| Classes | PascalCase |
| Constants | UPPER_CASE |

Example:

```js
const isLoggedIn=true;

class UserAccount{}
```

---

# Avoid Common Mistakes

## Use const / let

Avoid:

```js
var name;
```

---

## Use ===

Avoid:

```js
1=="1"
```

Use:

```js
1==="1"
```

---

## Copy Objects Safely

Wrong:

```js
const copy=obj;
```

Correct:

```js
const copy={...obj};
```

---

# Debugging with DevTools 🛠️

Important tools:

- Breakpoints
- Step Over
- Step Into
- Watch Variables
- Call Stack

Better than only using:

```js
console.log()
```

---

# Reading Errors

Example:

```
TypeError:
Cannot read property name
of undefined
```

Understand:

1. Error type  
2. Error message  
3. File and line number  
4. Call stack  

