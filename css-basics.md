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

### Pseudo-Class Selectors

Pseudo-class selectors target elements based on their state or position within the DOM. They allow us to apply styles based on user interactions or element relationships without adding additional classes or IDs.

**Key Pseudo-Classes:**

- **Structural Pseudo-Classes:** Target elements based on their position.

  - `:first-of-type` – Targets the first element of a specific type within a parent.
  - `:last-child` – Targets the last child element within a parent.
  - `:nth-child()` – Targets elements based on a pattern or index (e.g., odd, even, or a specific number).

- **Interactive Pseudo-Classes:** Target elements based on user interactions.

  - `:link` and `:visited` – Style links based on whether they've been visited.
  - `:hover` – Applies styles when an element is hovered.
  - `:focus` – Applies styles when an element is focused (e.g., when tabbed to).

**Example:**

```css
/* Styling the first paragraph in an article */
article p:first-of-type {
  font-size: 140%;
  font-style: italic;
}

/* Styling the last child in an article */
article :last-child {
  font-weight: bold;
}

/* Styling every odd list item */
ul li:nth-child(odd) {
  color: deeppink;
}

/* Styling links */
a:visited,
a:link {
  color: dodgerblue;
}

a:hover,
a:focus {
  color: deeppink;
}
```

## Pseudo-Elements

Pseudo-elements are similar to pseudo-classes, but instead of targeting a state of an element, they target a specific part of an element's content. They are created using double colons `::` in modern CSS (though the single colon `:` notation is still widely supported for backward compatibility).

### Common Pseudo-Elements

- `::before` - Inserts content before an element's actual content.
- `::after` - Inserts content after an element's actual content.
- `::first-letter` - Styles the first letter of a block-level element.
- `::first-line` - Styles the first line of a block-level element.
- `::selection` - Styles the part of an element that the user has highlighted (selected).

### Example Usage

```css
/* Adds decorative quotes before and after blockquotes */
blockquote::before {
  content: "“";
  font-size: 2rem;
  color: #ccc;
}

blockquote::after {
  content: "”";
  font-size: 2rem;
  color: #ccc;
}

/* Styles the first letter of a paragraph */
p::first-letter {
  font-size: 2rem;
  font-weight: bold;
  color: #555;
}

/* Highlights selected text */
::selection {
  background-color: #ffe6e6;
  color: #333;
}
```

### Key Differences

- **Pseudo-Classes** target the **state** or **position** of an element.
- **Pseudo-Elements** target **specific parts** of an element's **content**.

## Selector Specificity

When multiple CSS rules target the same element with conflicting styles, the browser determines which rule to apply based on **selector specificity** (or weight). The more specific a selector is, the higher its priority.

### Specificity Hierarchy

If we visualize specificity as a pyramid:

1. **ID Selectors** (`#product`) - Highest specificity, at the top of the pyramid.
2. **Class & Attribute Selectors** (`.products`, `[type="text"]`) - Medium specificity, in the middle of the pyramid.
3. **Element Selectors** (`section`, `p`) - Lowest specificity, at the base of the pyramid.

### Understanding Specificity in VS Code

When hovering over an element in VS Code, you can see the specificity of a selector displayed as a set of numbers in parentheses. These numbers represent:

1. **Number of ID selectors**.
2. **Number of class/attribute selectors**.
3. **Number of element selectors**.

For example, a specificity of `(1, 2, 0)` means:

- 1 ID selector,
- 2 class/attribute selectors,
- 0 element selectors.

By understanding specificity, you can write more predictable and maintainable CSS.
