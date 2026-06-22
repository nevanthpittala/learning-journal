# 1. Browser Rendering Pipeline 🚀

When HTML, CSS, and JavaScript are written, the browser converts them into a visual webpage.

## Complete Flow

```text
HTML
 ↓
Parsing
 ↓
Tokenization
 ↓
DOM Tree

CSS
 ↓
CSSOM Tree

DOM + CSSOM
 ↓
Render Tree
 ↓
Layout
 ↓
Paint
 ↓
Screen
```

---

## Steps Explanation

| Step | Purpose |
|---|---|
| HTML | Raw webpage structure |
| Parsing | Browser reads code |
| Tokenization | Converts code into tokens |
| DOM Tree | Object representation of HTML |
| CSSOM Tree | Object representation of CSS |
| Render Tree | DOM + CSSOM combined |
| Layout | Calculates size and position |
| Paint | Draws pixels on screen |

---

# 2. Parsing 

Parsing means converting code into a structure the browser understands.

Example:

```html
<h1>Hello</h1>
```

Browser understands:

```text
Element → h1
Content → Hello
```

Flow:

```text
HTML Code
    ↓
Parser
    ↓
Tokens
    ↓
DOM Tree
```

Important:

- HTML parsing happens top to bottom
- Browser identifies tags and relationships

---

# 3. Tokenization 

Tokenization means breaking HTML into small pieces called **tokens**.

Example:

```html
<h1>Hello</h1>
```

Tokens:

```text
Start Tag → <h1>
Text → Hello
End Tag → </h1>
```

Types:

| Token | Example |
|---|---|
| Start Tag | `<div>` |
| End Tag | `</div>` |
| Text | Hello |
| Attribute | class="box" |

---

# 4. DOM Tree 

DOM stands for:

```text
Document Object Model
```

The browser converts HTML into a tree structure.

Example:

HTML:

```html
<body>
  <h1>Hello</h1>
  <p>World</p>
</body>
```

DOM:

```text
Document
 └── html
      └── body
           ├── h1
           └── p
```

---

## DOM Relationships

### Parent Node

Element containing another element.

Example:

```text
body → parent of h1
```

### Child Node

Nested element.

Example:

```text
h1 → child of body
```

### Sibling Node

Elements with same parent.

Example:

```text
h1 and p
```

---

## Important

HTML is text.

DOM is an object representation.

Example:

```javascript
{
 tagName:"H1",
 textContent:"Hello"
}
```

---

# 5. CSSOM Tree 

CSSOM:

```text
CSS Object Model
```

Browser converts CSS into a structured tree.

Example:

CSS:

```css
h1 {
 color:red;
}
```

CSSOM:

```javascript
{
 selector:"h1",
 property:"color",
 value:"red"
}
```

---

# 6. Render Tree 🖥️

Render Tree combines:

```text
DOM + CSSOM
```

Example:

DOM:

```text
h1
```

CSSOM:

```text
color:red
```

Render Tree:

```text
h1
 └ color:red
```

Elements with:

```css
display:none;
```

are not added to the Render Tree.

---

# 7. DOM Selection 

JavaScript selects elements before modifying them.

Used for:

- Changing text
- Changing styles
- Events
- Creating elements
- Removing elements

---

## getElementById()

Select element by ID.

HTML:

```html
<h1 id="title">Hello</h1>
```

JS:

```javascript
document.getElementById("title");
```

Returns single element.

---

## getElementsByClassName()

Select by class.

```javascript
document.getElementsByClassName("box");
```

Returns:

```text
HTMLCollection
```

---

## getElementsByTagName()

Select by tag.

```javascript
document.getElementsByTagName("p");
```

---

## querySelector()

Returns first match.

```javascript
document.querySelector(".box");

document.querySelector("#title");

document.querySelector("p");
```

---

## querySelectorAll()

Returns all matches.

```javascript
document.querySelectorAll(".box");
```

Returns:

```text
NodeList
```

---

## Selector Difference

| querySelector | querySelectorAll |
|---|---|
| First match | All matches |
| Single element | NodeList |

---

# 8. innerHTML 

Used to read or write HTML content.

Example:

```html
<div id="box">
<h1>Hello</h1>
</div>
```

JS:

```javascript
box.innerHTML;
```

Output:

```html
<h1>Hello</h1>
```

Updating:

```javascript
box.innerHTML =
"<h2>Welcome</h2>";
```

Supports HTML tags.

⚠️ Avoid inserting user input because it can cause XSS attacks.

---

# 9. textContent 

Reads or updates only text.

Example:

```javascript
box.textContent =
"Hello World";
```

Difference:

innerHTML:

```javascript
box.innerHTML =
"<b>Hello</b>";
```

Output:

**Hello**

textContent:

```javascript
box.textContent =
"<b>Hello</b>";
```

Output:

```text
<b>Hello</b>
```

---

# innerHTML vs textContent

| innerHTML | textContent |
|-|-|
| Handles HTML | Handles Text |
| Parses tags | Ignores tags |
| Less secure | More secure |

---

# 10. classList 

Used to modify CSS classes using JavaScript.

---

## add()

Adds class.

```javascript
element.classList.add("active");
```

---

## remove()

Removes class.

```javascript
element.classList.remove("active");
```

---

## toggle()

Adds if missing, removes if existing.

```javascript
element.classList.toggle("dark");
```

Used in:

- Dark mode
- Menus
- Modals

---

## contains()

Checks if class exists.

```javascript
element.classList.contains("active");
```

Returns:

```javascript
true / false
```

---

# Final Revision Sheet

| Concept | Meaning |
|---|---|
| Parsing | Browser reads HTML |
| Tokenization | HTML → Tokens |
| DOM | HTML object tree |
| CSSOM | CSS object tree |
| Render Tree | DOM + CSSOM |
| Layout | Calculate position |
| Paint | Draw UI |
| querySelector | First element |
| querySelectorAll | Multiple elements |
| innerHTML | Change HTML |
| textContent | Change text |
| classList | Manage CSS classes |

---

# DOM Learning Flow 

```text
HTML
 ↓
DOM Tree
 ↓
Select Elements
 ↓
Modify Content
 ↓
Modify Classes
 ↓
Events
 ↓
Interactive Websites
```

DOM is the foundation of JavaScript frontend development and is heavily used in React and modern frameworks.