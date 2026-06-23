# 1. Attribute vs Property

## Attribute
- Exists in HTML markup
- Represents the initial value
- Does not automatically change after user interaction

## Property
- Exists inside DOM JavaScript object
- Represents the current live value
- Changes dynamically

Example:

```js
// HTML
<input id="name" value="Alice">

const input = document.getElementById("name");

input.getAttribute("value");
// Alice → original HTML value

input.value;
// Alice initially

// user types Bob

input.getAttribute("value");
// Alice

input.value;
// Bob
```

Remember:

```
Attribute = Initial Snapshot
Property  = Live Current State
```

---

# 2. Attribute Methods

## setAttribute()

Adds or updates an attribute.

```js
element.setAttribute("disabled","");
element.setAttribute("data-id","10");
```

---

## removeAttribute()

Removes an attribute.

```js
element.removeAttribute("disabled");
```

---

## hasAttribute()

Checks if attribute exists.

```js
element.hasAttribute("disabled");
// true / false
```

For boolean attributes:

```
disabled
checked
readonly
```

Presence = true  
Absence = false

---

# 3. data-* Attributes & dataset API

Used for storing custom data inside HTML.

HTML:

```html
<div data-user-id="7"></div>
```

JS:

```js
const div = document.querySelector("div");

div.dataset.userId;
// "7"
```

Conversion:

```
data-user-id  → dataset.userId
data-bg-color → dataset.bgColor
```

Important:

- dataset values are always strings
- Convert manually when needed

```js
Number(div.dataset.userId);
```

---

# 4. class Attribute Handling

## getAttribute("class")

Returns raw HTML class string.

```js
element.getAttribute("class");
```

---

## className

Replaces complete class value.

```js
element.className = "box active";
```

⚠️ Removes old classes.

---

## classList (Recommended)

Modern way to modify classes.

```js
element.classList.add("active");

element.classList.remove("hide");

element.classList.toggle("dark");

element.classList.contains("active");

element.classList.replace("old","new");
```

Use:

```
classList → modify classes
className → replace all classes
```

---

# Class 3 — Creating & Manipulating DOM Nodes

---

# 1. createElement()

Creates HTML element in memory.

```js
const div = document.createElement("div");

div.textContent = "Hello";

document.body.appendChild(div);
```

Element appears only after inserting into DOM.

---

# 2. createTextNode()

Creates safe text node.

```js
const text =
document.createTextNode("Hello");

div.appendChild(text);
```

Prefer:

```js
textContent
createTextNode()
```

instead of:

```js
innerHTML
```

for user data because of XSS risk.

---

# 3. DocumentFragment

Temporary memory container.

Used for performance.

Bad:

```js
for(let i=0;i<1000;i++){
 list.appendChild(li);
}
```

Many DOM updates.

Better:

```js
const fragment =
document.createDocumentFragment();

for(let i=0;i<1000;i++){

 const li =
 document.createElement("li");

 fragment.appendChild(li);
}

list.appendChild(fragment);
```

Only one DOM update.

---

# Old DOM APIs

---

# appendChild()

Adds node as last child.

```js
parent.appendChild(child);
```

If element already exists:

```
It moves the element
It does NOT copy it
```

---

# insertBefore()

Insert before another child.

Syntax:

```js
parent.insertBefore(
 newNode,
 referenceNode
);
```

Example:

```js
list.insertBefore(newItem, firstItem);
```

---

# removeChild()

Remove child element.

```js
parent.removeChild(child);
```

Old style:

```js
item.parentNode.removeChild(item);
```

---

# Modern DOM APIs

---

# append()

Better version of appendChild.

Supports:
- Multiple items
- Text + elements

```js
div.append(
 "Hello",
 span,
 "World"
);
```

---

# prepend()

Adds as first child.

```js
parent.prepend(element);
```

---

# before()

Insert before current element.

```js
element.before(newElement);
```

---

# after()

Insert after current element.

```js
element.after(newElement);
```

---

# replaceWith()

Replace element completely.

```js
oldElement.replaceWith(newElement);
```

---

# remove()

Modern delete method.

Old:

```js
element.parentNode.removeChild(element);
```

Modern:

```js
element.remove();
```

---

# Old vs Modern DOM API

| Old | Modern |
|---|---|
| appendChild() | append() |
| insertBefore() | before()/after() |
| removeChild() | remove() |
| replaceChild() | replaceWith() |

---

✅ Attribute = HTML initial value  
✅ Property = live DOM value  
✅ Use classList for classes  
✅ Use dataset for data-* attributes  
✅ Use createElement to build DOM  
✅ Avoid innerHTML with user input  
✅ DocumentFragment improves performance  
✅ Prefer modern DOM APIs  
