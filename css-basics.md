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
