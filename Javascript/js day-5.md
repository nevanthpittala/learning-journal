# JavaScript Async Programming 🚀

Complete notes covering asynchronous JavaScript concepts including callbacks, promises, async/await, event loop, Fetch API, and JSON handling.

---

# 1. Synchronous vs Asynchronous JavaScript

## Synchronous

- JavaScript is single-threaded by default.
- Executes code line by line.
- Next task waits until the current task finishes.
- Long-running tasks can block the application.

Example:

```js
console.log("Start");
console.log("End");
```

---

## Asynchronous

- Allows long-running tasks to execute without blocking.
- Uses Browser APIs / Node.js APIs.
- Keeps applications responsive.

Common async tasks:

- API requests
- Timers
- File operations
- Database queries
- User interactions

---

# 2. Callbacks

A callback is a function passed as an argument to another function and executed later.

Example:

```js
function welcome(callback){
  callback();
}
```

Types:

- Synchronous callbacks
- Asynchronous callbacks

Examples:

- forEach()
- setTimeout()
- Event handlers

---

# 3. Timers

## setTimeout()

Executes a function once after a delay.

```js
setTimeout(()=>{
 console.log("Hello");
},1000);
```

---

## setInterval()

Executes repeatedly after a fixed interval.

```js
setInterval(()=>{
 console.log("Running");
},1000);
```

Stopping timers:

- clearTimeout()
- clearInterval()

---

# 4. Callback Hell

Deep nesting of callbacks.

Problems:

❌ Poor readability  
❌ Difficult debugging  
❌ Complex error handling  

Example:

```js
getUser(()=>{
 getOrders(()=>{
  payment(()=>{
    
  })
 })
})
```

Also called:

**Pyramid of Doom**

Solution:

➡️ Promises

---

# 5. Promises 🤝

A Promise represents the future result of an asynchronous operation.

## Promise States

| State | Meaning |
|---|---|
| Pending | Running |
| Fulfilled | Success |
| Rejected | Failed |

Creating Promise:

```js
const promise = new Promise((resolve,reject)=>{

 resolve("Completed");

});
```

Using Promise:

```js
promise
.then()
.catch()
.finally();
```

---

# Promise Chaining

Used to avoid callback hell.

```js
getUser()
.then(getOrders)
.then(payment)
.catch(error);
```

Advantages:

- Cleaner code
- Better error handling
- Easy maintenance

---

# Promise Methods

## Promise.all()

- Waits for all promises.
- Fails if one promise fails.

Used for:

- Multiple API calls
- Parallel tasks

---

## Promise.race()

Returns the first completed promise.

---

## Promise.allSettled()

Returns all promise results even if some fail.

---

## Promise.any()

Returns the first successful promise.

---

# 6. Async / Await ✨

Cleaner way to work with Promises.

---

## async

Makes a function return a Promise.

```js
async function test(){

 return "Hello";

}
```

---

## await

Waits until a Promise completes.

```js
const data = await fetchData();
```

---

# Error Handling

Use try/catch:

```js
try{

 const data = await api();

}
catch(error){

 console.log(error);

}
```

---

# Sequential vs Parallel Execution

## Sequential

Tasks depend on each other.

```js
await task1();
await task2();
```

Slower because tasks wait.

---

## Parallel

Independent tasks run together.

```js
await Promise.all([
 task1(),
 task2()
]);
```

Faster execution.

---

# Common Async Mistakes

## Forgetting await ❌

Wrong:

```js
const data = fetchData();
```

Returns:

```
Promise
```

Correct:

```js
const data = await fetchData();
```

---

## Using await inside forEach ❌

Wrong:

```js
array.forEach(async()=>{

});
```

Correct:

```js
for(const item of array){

 await task();

}
```

---

# 7. JavaScript Event Loop 🤯

Allows JavaScript to handle asynchronous operations while remaining single-threaded.

Components:

- Call Stack
- Web APIs
- Microtask Queue
- Callback Queue
- Event Loop

---

# Execution Priority

Remember:

```
1. Synchronous Code
        ↓
2. Microtasks
   Promise / await
        ↓
3. Macrotasks
   setTimeout / setInterval
```

Example:

```js
console.log("1");

setTimeout(()=>{
 console.log("2");
},0);

Promise.resolve()
.then(()=>{
 console.log("3");
});

console.log("4");
```

Output:

```
1
4
3
2
```

---

# 8. Fetch API 🌐

Used to communicate with servers.

Examples:

- Login
- Register
- API requests
- CRUD operations

---

# HTTP Methods

| Method | Purpose |
|---|---|
| GET | Read data |
| POST | Create data |
| PUT | Replace data |
| PATCH | Update data |
| DELETE | Remove data |

---

Fetch Example:

```js
const response = await fetch(url);

const data = await response.json();
```

Two awaits:

1. Wait for server response
2. Convert JSON data

---

# Fetch Error Handling

fetch() does not reject on:

- 404
- 500

Check manually:

```js
if(!response.ok){

 throw new Error(response.status);

}
```

---

# 9. JSON 📦

JSON = JavaScript Object Notation

Used for transferring data between frontend and backend.

---

## JSON.stringify()

Converts:

```
Object → JSON String
```

Example:

```js
JSON.stringify(user);
```

Used when sending data.

---

## JSON.parse()

Converts:

```
JSON String → Object
```

Example:

```js
JSON.parse(data);
```

Used when receiving data.

---

# Final Revision Table 🚀

| Concept | Meaning |
|---|---|
| Sync | Executes line by line |
| Async | Non-blocking execution |
| Callback | Function passed as argument |
| Promise | Future async result |
| async | Returns Promise |
| await | Waits for Promise |
| Event Loop | Handles async flow |
| Microtask | Promise / await |
| Macrotask | setTimeout |
| Fetch | HTTP Requests |
| JSON.stringify | Object → JSON |
| JSON.parse | JSON → Object |

---

# Learning Order

1. Synchronous vs Asynchronous
2. Callbacks
3. Timers
4. Callback Hell
5. Promises
6. Promise Methods
7. Async/Await
8. Event Loop
9. Fetch API
10. JSON

---

## Completed Topics ✅

- Async JavaScript
- Callbacks
- Timers
- Promises
- Async/Await
- Event Loop
- Fetch API
- JSON
- Interview Concepts
