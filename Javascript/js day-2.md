# Day 2 - JavaScript Functions, Arrays & Objects 🚀

## Topics Covered

- Functions
- Arrow Functions
- Callbacks
- Higher Order Functions
- Recursion
- Arrays
- Array Methods
- Objects
- Destructuring
- Spread & Rest
- Mini Projects

---

# Functions

A function is a reusable block of code used to perform a task.

Benefits:
- Reusability
- Readability
- Maintainability

Example:

```javascript
function add(a,b){
 return a+b;
}

console.log(add(5,10));
```

---

# Function Types

## Function Declaration

```javascript
function greet(name){
 console.log("Hello " + name);
}
```

## Function Expression

```javascript
const greet = function(){
 console.log("Hello");
};
```

## Arrow Function

Modern ES6 syntax.

```javascript
const add = (a,b) => a+b;
```

---

# Parameters & Arguments

Parameter → variable in function definition

Argument → actual value passed

```javascript
function greet(name){

}

greet("Aman");
```

---

# Default Parameters

```javascript
function greet(name="Guest"){
 console.log(name);
}
```

---

# Rest Parameters

Collect multiple values.

```javascript
function sum(...nums){

}
```

---

# Return Statement

Returns value from function.

```javascript
function multiply(a,b){
 return a*b;
}
```

No return → `undefined`

---

# First Class Functions

In JavaScript functions can be:

- Stored in variables
- Passed as arguments
- Returned from functions

---

# Callback Function

Function passed into another function.

```javascript
function hello(callback){
 callback();
}
```

Used in:
- Events
- Array methods
- Async JS

---

# Higher Order Functions

A function that:

- Accepts another function
- Returns another function

Example:

```javascript
map()
filter()
reduce()
```

---

# IIFE

Runs immediately.

```javascript
(function(){
 console.log("Run");
})();
```

---

# Pure Function

Same input → same output

```javascript
function add(a,b){
 return a+b;
}
```

---

# Recursion

Function calling itself.

Needs:
- Base case
- Recursive case

```javascript
function fact(n){
 if(n<=1) return 1;

 return n*fact(n-1);
}
```

---

# Arrays

Stores multiple values.

```javascript
let fruits=[
 "apple",
 "banana"
];
```

Index starts from `0`.

---

# Array Methods

## Mutating Methods

Change original array:

```javascript
push()
pop()
shift()
unshift()
splice()
sort()
reverse()
```

---

## Non Mutating Methods

Create new result:

```javascript
slice()
concat()
includes()
indexOf()
join()
```

Remember:

`slice()` → copy  
`splice()` → modify

---

# Important Array Methods

## forEach

Runs for every element.

```javascript
arr.forEach(x=>{
 console.log(x);
})
```

---

## map

Transforms array.

```javascript
let result = arr.map(x=>x*2);
```

---

## filter

Filters values.

```javascript
arr.filter(x=>x>10);
```

---

## reduce

Converts array into single value.

```javascript
arr.reduce((sum,x)=>sum+x,0);
```

---

## find

Find first matching element.

```javascript
arr.find(x=>x.id===1);
```

---

## some / every

```javascript
some()
// at least one true

every()
// all true
```

---

# Array Destructuring

```javascript
let [a,b]=[10,20];
```

---

# Spread Operator

Expands values.

```javascript
let copy=[...arr];
```

---

# Rest Operator

Collects values.

```javascript
function sum(...nums){

}
```

---

# Multi Dimensional Arrays

Array inside array.

```javascript
let matrix=[
 [1,2],
 [3,4]
];

matrix[0][1];
```

---

# Objects

Store key-value pairs.

```javascript
let user={
 name:"Aman",
 age:25
};
```

---

# Access Object Data

Dot:

```javascript
user.name
```

Bracket:

```javascript
user["name"]
```

---

# Modify Objects

Add:

```javascript
user.city="Delhi";
```

Update:

```javascript
user.age=30;
```

Delete:

```javascript
delete user.age;
```

---

# Object Methods

Functions inside objects.

```javascript
let user={
 greet(){
  console.log("Hi");
 }
};
```

---

# this Keyword

Refers to current object.

```javascript
this.name
```

---

# Object Destructuring

```javascript
let {name,age}=user;
```

---

# Object Spread

Copy objects:

```javascript
let copy={...user};
```

---

# Useful Object Methods

```javascript
Object.keys()

Object.values()

Object.entries()
```

---

# Arrays vs Objects

Use Array:
- Ordered list
- Similar items

Use Object:
- Describe one entity
- Named properties

Most common pattern:

```javascript
[
 {name:"A",age:20},
 {name:"B",age:25}
]
```

---

# Mini Projects Completed 🛠️

- Todo List
- Student Grade Tracker
- Shopping Cart
- Word Counter
- Library Management System

---

# Important Concepts ✅

- Functions
- Callbacks
- Higher Order Functions
- Array methods
- Objects
- Destructuring
- Spread/Rest
- Arrays of Objects

JavaScript Phase 2 Completed 🎯