# 1. Event Propagation

## What is an Event?

An event is an action that happens in the browser.

Examples:

- `click` → user clicks an element
- `keydown / keyup` → keyboard action
- `mouseover / mouseout` → mouse movement
- `submit` → form submission
- `input` → input value changes
- `load` → resource finished loading

---

## What is Event Propagation?

Event Propagation is the journey of an event through the DOM tree.

When an element is clicked, the event does not stay there.

It travels:

```
window
 ↓
document
 ↓
html
 ↓
body
 ↓
parent elements
 ↓
target element
```

---

# 2. Three Phases of Event Propagation

Every event has 3 phases:

---

## 1. Capturing Phase (Top → Bottom)

Event travels from:

```
window → document → html → body → target
```

- Happens before reaching the clicked element.
- Not enabled by default.

Enable using:

```js
element.addEventListener(
  "click",
  handler,
  true
);
```

or

```js
element.addEventListener(
"click",
handler,
{
 capture:true
});
```

---

## 2. Target Phase

The event reaches the actual clicked element.

Example:

```html
<button>Click</button>
```

If button is clicked:

```
Target = button
```

---

## 3. Bubbling Phase (Bottom → Top)

Default browser behavior.

Event travels:

```
target → parent → body → html → document → window
```

Example:

```js
button.addEventListener("click",()=>{
 console.log("clicked");
});
```

Uses bubbling automatically.

---

# Event Flow Example

HTML:

```html
<div id="parent">
 <button id="child">
 Click
 </button>
</div>
```

Flow:

```
CAPTURE:

window
 ↓
parent
 ↓
child


TARGET:

child


BUBBLE:

child
 ↑
parent
 ↑
window
```

---

# 3. Event Bubbling

## Definition

Event bubbling means:

> Event starts from the clicked element and moves upward through all parents.

Example:

```html
<div id="box">
 <button id="btn">
 Click
 </button>
</div>
```

JS:

```js
box.addEventListener("click",()=>{
 console.log("box");
});

btn.addEventListener("click",()=>{
 console.log("button");
});
```

Output:

```txt
button
box
```

Because:

```
button → div
```

---

# e.target vs e.currentTarget

Very important interview topic.

| Property | Meaning |
|-|-|
| e.target | Original clicked element |
| e.currentTarget | Element whose listener is running |

Example:

```js
parent.addEventListener(
"click",
(e)=>{

console.log(e.target);
console.log(e.currentTarget);

});
```

If button inside parent clicked:

```
target = button

currentTarget = parent
```

---

# Stop Event Bubbling

## stopPropagation()

Stops event moving to parent.

Example:

```js
button.addEventListener(
"click",
(e)=>{

e.stopPropagation();

});
```

---

Example:

Card click opens details.

Delete button deletes card.

Without stopPropagation:

```
Delete clicked
+
Card opened
```

Fix:

```js
deleteBtn.addEventListener(
"click",
(e)=>{

e.stopPropagation();

deleteCard();

});
```

---

# stopPropagation vs stopImmediatePropagation

| Method | Action |
|-|-|
| stopPropagation() | Stops going to parent |
| stopImmediatePropagation() | Stops parent + other same element listeners |

Example:

```js
btn.addEventListener(
"click",
(e)=>{

e.stopImmediatePropagation();

});
```

---

# 4. Event Delegation

## Problem

Bad approach:

```js
buttons.forEach(btn=>{

btn.addEventListener(
"click",
handler
);

});
```

Problems:

- Many listeners
- More memory usage
- New elements don't work

---

## Solution: Event Delegation

Add listener to parent only.

Example:

HTML:

```html
<ul id="list">

<li>
<button class="delete">
Delete
</button>
</li>

</ul>
```

JS:

```js
list.addEventListener(
"click",
(e)=>{

if(
e.target.classList.contains("delete")
){

e.target.parentElement.remove();

}

});
```

Advantages:

✅ One listener  
✅ Better performance  
✅ Works with dynamic elements  
✅ Cleaner code  

---

# Events That Do Not Bubble

| Does Not Bubble | Use Instead |
|-|-|
| focus | focusin |
| blur | focusout |
| mouseenter | mouseover |
| mouseleave | mouseout |
| load | attach directly |
| scroll | attach directly |

---

# 5. Event Capturing

Capturing happens before bubbling.

Direction:

```
window
 ↓
document
 ↓
parent
 ↓
target
```

Enable:

```js
element.addEventListener(
"click",
handler,
true
);
```

Example:

```js
parent.addEventListener(
"click",
()=>{

console.log("capture");

},
true);
```

---

## Complete Order

If button clicked:

```
1. Parent Capture

2. Button Capture

3. Button Bubble

4. Parent Bubble
```

---

# 6. Event Traversal

Moving through DOM from event target.

Common methods:

---

## closest()

Find nearest parent matching selector.

Example:

```js
const card =
e.target.closest(".card");
```

---

## matches()

Checks if element matches selector.

Example:

```js
if(
e.target.matches("button")
){

console.log("button clicked");

}
```

---

# DOM Traversal Methods

| Method | Use |
|-|-|
| parentElement | Get parent |
| children | Get children |
| firstElementChild | First child |
| lastElementChild | Last child |
| nextElementSibling | Next sibling |
| previousElementSibling | Previous sibling |
| querySelector() | Find inside element |
| closest() | Find ancestor |

---

# composedPath()

Shows complete event path.

Example:

```js
document.addEventListener(
"click",
(e)=>{

console.log(
e.composedPath()
);

});
```

Output:

```
button
div
body
html
document
window
```

---

# Final Revision Table

| Topic | Meaning |
|-|-|
| Event Propagation | Full event journey |
| Capturing | Top → Bottom |
| Target Phase | Actual clicked element |
| Bubbling | Bottom → Top |
| e.target | Original element |
| e.currentTarget | Current handler element |
| stopPropagation | Stop event travel |
| stopImmediatePropagation | Stop all listeners |
| Event Delegation | One parent handles children |
| closest() | Search upward |
| matches() | Check selector |

---

# Interview Memory Trick 🧠

```
Capture ↓

Target 🎯

Bubble ↑
```

Event lifecycle:

```
Window
 ↓
Parents
 ↓
TARGET
 ↑
Parents
 ↑
Window
```