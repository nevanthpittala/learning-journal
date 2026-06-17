### 1. `this` Keyword
- Learned how JavaScript decides the value of `this`.
- `this` depends on **how a function is called**, not where it is written.

Key concepts:
- Global `this`
  - Browser → `window`
  - Node module → `module.exports ({})`
- Regular function `this`
  - Non-strict → global object
  - Strict mode → `undefined`
- Object methods
  - `this` refers to the object before the dot (`obj.method()`)
- Arrow functions
  - Do not have their own `this`
  - Use lexical `this` from parent scope
- Event handlers
  - Regular function → clicked element
  - Arrow function → lexical scope

Rule:
> Use regular functions for object methods and arrow functions for callbacks.

---

## 2. call(), apply(), bind()

Studied explicit binding methods used to manually control `this`.

### call()
- Executes function immediately
- Arguments passed separately

```js
fn.call(obj, arg1, arg2);