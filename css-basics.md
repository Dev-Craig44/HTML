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

 <!-- you can create an section element with an id by typing "section#products" -->
  <!-- we can also select an element by its class -->

       <!-- you can create an article element with a class by typing "article.product" -->
        <!-- and alse you can make multiple instances by typing "*3"-->
        /* you use "#" to select an id */
