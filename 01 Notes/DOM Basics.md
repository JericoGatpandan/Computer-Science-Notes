#javascript #dom #webdev
- The **DOM (or Document Object Model)** is a tree-like representation of the contents of a webpage - a tree of “nodes” with different relationships depending on how they’re arranged in the HTML document. There are many types of nodes, most of which are not commonly used. In this lesson we will be focusing on “element” nodes which are primarily used for manipulating the DOM.
```JavaScript
// selects the #container div (don't worry about the syntax, we'll get there)
const container = document.querySelector("#container");

// selects the first child of #container => .display
const display = container.firstElementChild;
console.log(display);  // <div class="display"></div>
```
```JavaScript
// selects the .controls div
const controls = document.querySelector(".controls");

// selects the prior sibling => .display
const display = controls.previousElementSibling;
console.log(display); // <div class="display"></div>
```

- `document.createElement(tagName, [options])` - creates a new element of tag type tagName. `[options]` in this case means you can add some optional parameters to the function. Don’t worry about these at this point.
- `Array.from()`

- You can place the element into the DOM with one of the following methods.
	- `parentNode.appendChild(childNode)` - appends _childNode_ as the last child of _parentNode_.
	- `parentNode.insertBefore(newNode, referenceNode)` - inserts _newNode_ into _parentNode_ before _referenceNode_.
	- `parentNode.removeChild(child)` - removes _child_ from _parentNode_ on the DOM and returns a reference to _child_.

- When accessing a kebab-cased CSS property like `background-color` with JS, you will need to either use camelCase with dot notation or bracket notation. When using bracket notation, you can use either camelCase or kebab-case, but the property name must be a string.
```javascript
// dot notation with kebab case: doesn't work as it attempts to subtract color from div.style.background
// equivalent to: div.style.background - color
div.style.background-color;

// dot notation with camelCase: works, accesses the div's background-color style
div.style.backgroundColor;

// bracket notation with kebab-case: also works
div.style["background-color"];

// bracket notation with camelCase: also works
div.style["backgroundColor"];
```

```javascript
// if id exists, update it to 'theDiv', else create an id with value "theDiv"
div.setAttribute("id", "theDiv");

// returns value of specified attribute, in this case "theDiv"
div.getAttribute("id");

// removes specified attribute
div.removeAttribute("id");
```

```JavaScript
// adds class "new" to your new div
div.classList.add("new");

// removes "new" class from div
div.classList.remove("new");

// if div doesn't have class "active" then add it, or if it does, then remove it
div.classList.toggle("active");
```

```javascript
// creates a text node containing "Hello World!" and inserts it in div
div.textContent = "Hello World!";
```

```javascript
// renders the HTML inside div
div.innerHTML = "<span>Hello World!</span>";
```
>Note that using textContent is preferred over innerHTML for adding text, as innerHTML should be used sparingly to avoid potential security risks. To understand the dangers of using innerHTML, watch this [video about preventing the most common cross-site scripting attack](https://youtube.com/watch?v=ns1LX6mEvyM).

- You can link the JavaScript file in the `<head>` of your HTML document. Use the `<script>` tag with the `src` attribute containing the path to the JS file, and include the `defer` keyword to load the file _after_ the HTML is parsed, as such:

[[11 DOM Manipulation and Events  The Odin Project]]