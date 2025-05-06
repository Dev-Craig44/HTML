# CSS Basics

here we will learn the essential CSS concept you need to understand to build beautiful web pages.

You'll learn about:

- Various ways to provide CSS
- Normalizing CSS
- CSS Selectors
- Colors
- Gradients
- Borders
- Shadows

# Providing CSS

- Embedded stylsheets
- External stylesheets
- Inline styles

- if you want to comment out a block of html, you can use the following syntax:

````html
<!--
  <div>
    <h1>Title</h1>
    <p>Content</p>
  </div>
-->
- if you want to comment out a block of css, you can use the following syntax:
```css /* body { background-color: #f0f0f0; } */
````

# Normalizing CSS

- every browser has its own default CSS styles, which can lead to inconsistencies in how web pages are displayed across different browsers.
- to handle this there's a very popular CSS library called Normalize.css.
- Normalize.css is a small CSS file that provides better cross-browser consistency in the default styling of HTML elements.
- http://necolas.github.io/normalize.css

- normalizing our CSS is important step in front-end development, and going forward, we will always use Normalize.css in our projects.

# Basic Selectors

- we have a lot of ways to select elements in CSS.

- Type
- Class
- ID
- Attribute

What's the difference between a class and an id?

- A class is a reusable style that can be applied to multiple elements, while an id is a unique identifier that should only be used once per page.

### Selecting Elements by ID and Class

- To create a `section` element with an ID, you can use the following syntax:

  ```html
  <section id="products"></section>
  ```

- To select an element by its ID in CSS, use the `#` symbol:

  ```css
  #products {
    /* styles here */
  }
  ```

- To create an `article` element with a class, use this syntax:

  ```html
  <article class="product"></article>
  ```

- To select an element by its class in CSS, use the `.` symbol:

  ```css
  .product {
    /* styles here */
  }
  ```

- You can also create multiple instances of an element using shorthand syntax in tools like Emmet:
  ```html
  article.product*3
  ```
  This will generate three `article` elements with the class `product`.

# Relational Selectors

you can also select elements based on their relationship to other elements. Here are some common relational selectors:

- `>`: Selects direct children of an element.
- `+`: Selects the next sibling of an element.
- `~`: Selects all siblings of an element.
- `:first-child`: Selects the first child of an element.
- `:last-child`: Selects the last child of an element.
- `:nth-child(n)`: Selects the nth child of an element.
- `:nth-of-type(n)`: Selects the nth child of a specific type within an element.
- `:not(selector)`: Selects elements that do not match the specified selector.
- `:hover`: Selects an element when the mouse hovers over it.
- `:focus`: Selects an element when it is focused (e.g., an input field).
- `:active`: Selects an element when it is being activated (e.g., a button being clicked).
- `:checked`: Selects checkboxes or radio buttons that are checked.
- `:disabled`: Selects disabled form elements.
- `:enabled`: Selects enabled form elements.
- `:valid`: Selects valid form elements.
- `:invalid`: Selects invalid form elements.
- `:required`: Selects required form elements.
- `:optional`: Selects optional form elements.
- `:target`: Selects the target element of a URL fragment (e.g., `#section1`).
- `:lang(language)`: Selects elements based on their language attribute.
- `:before`: Inserts content before an element.
- `:after`: Inserts content after an element.
- `:first-letter`: Selects the first letter of a block-level element.
- `:first-line`: Selects the first line of a block-level element.
- `:placeholder-shown`: Selects input elements that are showing their placeholder text.
- `:read-only`: Selects elements that are read-only.
- `:read-write`: Selects elements that are editable.
- `:empty`: Selects elements that have no children (including text nodes).
- `:nth-last-child(n)`: Selects the nth child of an element, counting from the last child.
- `:nth-last-of-type(n)`: Selects the nth child of a specific type within an element, counting from the last child.
- `:nth-of-type(n)`: Selects the nth child of a specific type within an element.
- `:nth-last-of-type(n)`: Selects the nth child of a specific type within an element, counting from the last child.
- `:nth-child(odd)`: Selects odd-numbered children of an element.
- `:nth-child(even)`: Selects even-numbered children of an element.
- `:nth-of-type(odd)`: Selects odd-numbered children of a specific type within an element.
- `:nth-of-type(even)`: Selects even-numbered children of a specific type within an element.
- `:not(:first-child)`: Selects all children except the first child.
- `:not(:last-child)`: Selects all children except the last child.
- `:not(:nth-child(n))`: Selects all children except the nth child.
- `:not(:nth-of-type(n))`: Selects all children of a specific type except the nth child.
- `:not(:nth-last-child(n))`: Selects all children except the nth child, counting from the last child.

takeaways

- cleaner markup
- can be fregile
- not as fast as basic selectors
