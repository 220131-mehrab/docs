# HTML, CSS, & JavaScript

## QC Topics
- HTML
    - HTML5
    - Forms:
        - Action
        - Inputs
        - Submit
    - Elements:
        - Attributes
        - Id
        - Class
    - Head tags: meta, title, link
    - Body tags: div, a, p, h1-h6
    - Style & Script tags
    - DOM - Document Object Model

- CSS
    - CSS3
    - Cascade priority:
        - external
        - internal
        - in-line
    - Box Model
    - Id vs Class tag

- JavaScript
    - EcmaScript 6
    - Variables: 
        - Scopes
        - var, let, const
        - hoisting
    - Objects, arrays, functions
    - JSON stringify & parse
    - DOM API
    - Prototypical Inheritance
    - Callbacks & closures
    - Events: 
        - Bubbling vs Capturing
        - Listeners
    - Template literals
    - Lambda arrow notation
    - AJAX: Asynchronous JavaScript & XML
    - Promises

# HTML
Hypertext Markup Language, or HTML, provides a structures to hypertext parsed by a browser. HTML documents are organized by element tags with attributes and values which are parsed, styled by CSS, and manipulated by JavaScript to render web sites and web apps.

## Document Object Model (DOM)
When parsing an HTML document, a virtual tree is constructed by a browser known as the DOM. This allows a browser to change and alter the content through stylesheets or scripts without affecting the original document file.

### HTML document
```html
<!doctype html>
<html>
  <head>
    <title>Index</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
  </body>
</html>
```

### DOM
html
  └── head
  |    └── title
  |         └── Index
  └── body
       └── h1
            └── Hello, world!

## Critical Render Path
HTML document -> parsed -> DOM -> CSSOM -> Render Tree -> Layout -> Paint -> Composite
1. Constructing the DOM Tree
2. Constructing the CSSOM Tree
3. Running JavaScript
4. Creating the Render Tree
5. Generating the Layout
6. Painting

CSS is a render blocking resource, holding up the Render Tree, while JavaScript is a parser blocking resource pausing at each `<script>` tag without an `async` attribute. The Render Tree is the combination of the DOM and CSSOM. The Layout is determined by the viewport, default 980px width if not set like below:
`<meta name="viewport" content="width=device-width,initial-scale=1">`

# CSS
Cascading Stylesheets is a declarative language used by a browser to style a web page, overwriting rules for HTML elements in cascading layers of increasing selector specificity and source precedence. CSS rules will be inherited by child nodes of these elements.

## Order of specificity (highest to lowest)
1) Important tag
2) `style` property
3) id selector
4) class selector
5) element selector

## Property
Inline CSS can be added as an HTML element attribute, known as a property.
```html
<div style="border: 1px solid black; font-size: 18px; "> Text </div>
```

## Order of precedence
Within a specificity level, which rules overwrite others is based on the last rule to be parsed, starting from the top of a style sheet or block to the bottom, and which sheet is loaded last.

## Rule
In a `<style>` block or external `.css` file, CSS is defined by a rule made up of a selector and key-value settings.
```css
div {
  border : 1px solid black;
  font-size : 18px;
}
```

Selectors include:
- Universal: *
- Element: html, div, p
- Class: .class-name
- Id: #id-name
- Attribute: [attribute-key]

And can be grouped using `,`:
```css
div, li {
  ...
}
```

Or target child elements of a specific selector:
```css
.class-name > li {
  ...
}
```

Or descendants of a selector:
```css
li a {
  ...
}

# JavaScript
JavaScript is an object-oriented scripting language supported by most web browsers using an engine such as **V8** on Chrome and **SpiderMonkey** on Firefox. Source code is directly translated (and now JIT compiled as well) into instructions to be run by the browser. JavaScript is **loosely-typed** and supports **higher-order functions**.

## Features
* **Loose typing**: 
Variables in JavaScript are dynamically typed, and not constrained to one type. Any variable can be assigned and re-assigned values of any type.

* **Automatic Type Coercion**
JavaScript will attempt to coerce values of different types into a single, compatible type to evaluate expressions.

* **Object-Oriented**:
Objects are maps between keys and values, and the basis of most other complex data types in JavaScript. A *function* is an object which intrinsically returns something. An *array* is an object with a special relationship between enumerated keys and values.

* **Prototypical Inheritance**
Objects in JavaScript inherit properties not through is-a relationships with other object types but through a property that links another object: the prototype.

## JSON
JSON (**JavaScript Object Notation**) is a lightweight data format resembling JavaScript objects for simple exchange of data between different programming languages. It can be saved as a text file or sent through an HTTP payload. A JSON message either represents a key/value collection or an array of key/value collections.
#### exampleSingle.json
```json
{
    "id":7,
    "name":"Example Name"
}
```
#### exampleList.json
```json
[
    {
        "id":7,
        "name":"Example Name"
    },
    {
        "id":8,
        "name":"Another Example"
    }
]
```

## JSON Parse/Stringify
The `JSON` API in JavaScript can parse this into a proper Object using `JSON.parse('example.json')`, while `JSON.stringify(exampleObject)` will turn an object into a JSON string.
```javascript
// From string to object
let jsonString = `{"id":7, "name":"Example Name"}`;
let jsonObject = JSON.parse(jsonString);

// From object to string
let jsonObject = {id:7, name:'Example Name'};
let jsonString = JSON.stringify(jsonObject);
```

## Variables and Scope
Early versions of JavaScript had only one variable type, `var`, which is scoped to either a function or the global context. ES6 introduced `let`, which also has lexical scoping (i.e. block scope), and `const`, which cannot be reassigned.

## Call Stack
JavaScript applications run as a single-threaded process
