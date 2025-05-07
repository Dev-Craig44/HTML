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

## Inheritance

In CSS, some properties naturally inherit values from their parent elements, while others do not. Understanding inheritance helps you write cleaner and more efficient styles.

### 🔹 Inheritance and Initial Keywords

- **Inheritance**:

  - Certain properties, like `color` and `font-family`, automatically inherit values from their parent elements.
  - To reset a property to its default value, use the `initial` keyword.

- **Force Inheritance**:
  - Use the `inherit` keyword to explicitly inherit a property from the parent, even if it doesn’t naturally inherit.

### Example

```css
/* Parent styles */
p {
  color: dodgerblue;
  border: 1px solid black;
}

/* Child element overrides inheritance */
strong {
  color: initial; /* Resets to default */
  border: inherit; /* Explicitly inherits from parent */
}
```

**HTML Example:**

```html
<p>Lorem ipsum <strong>dolor</strong> sit amet.</p>
```

In this example:

- The `<strong>` element inside the `<p>` tag will inherit the `border` property from the parent.
- The `color` property of `<strong>` is reset to its default value using `initial`.

## Colors

CSS provides various ways to define colors for your elements:

1. **Named Colors**: Predefined color names like `red`, `blue`, `green`, etc.
2. **RGB**: Specify colors using the Red-Green-Blue format, e.g., `rgb(255, 0, 0)` for red.
3. **HSL**: Define colors using Hue-Saturation-Lightness, e.g., `hsl(0, 100%, 50%)` for red.
4. **Hexadecimal**: Use hex codes like `#FF0000` for red.

### Adding Transparency

For both RGB and HSL, you can include an alpha channel to control transparency. This is done using `rgba` and `hsla` formats:

- **RGBA**: Adds an alpha value to RGB, e.g., `rgba(255, 0, 0, 0.5)` for semi-transparent red.
- **HSLA**: Adds an alpha value to HSL, e.g., `hsla(0, 100%, 50%, 0.5)` for semi-transparent red.

The alpha value ranges from `0` (completely transparent) to `1` (completely opaque).

# Gradients

Gradients allow us to create smooth transitions between two or more colors, adding depth and visual interest to our designs.

### Types of Gradients

1. **Linear Gradients**:

- By default, the gradient direction is from top to bottom.
- You can customize the direction (e.g., left to right, diagonal) using angles or keywords.

2. **Radial Gradients**:

- These start from the center and transition outward in a circular or elliptical shape.

### Gradient Tools

Creating gradients manually can be time-consuming. Fortunately, there are online tools like [CSS Gradient](https://cssgradient.io/) that simplify the process by generating the CSS code for you.

### Example

```css
/* Linear Gradient */
background: linear-gradient(to right, #ff7e5f, #feb47b);

/* Radial Gradient */
background: radial-gradient(circle, #ff7e5f, #feb47b);
```

# Borders

The `border` property in CSS allows you to define the appearance of an element's border. It accepts three values:

1. **Thickness**: Specifies the width of the border (e.g., `1px`, `0.5em`).
2. **Style**: Defines the border style (e.g., `solid`, `dashed`, `dotted`).
3. **Color**: Sets the color of the border (e.g., `#000`, `red`).

### Border Sides

Remember the order of sides when specifying borders: **top, right, bottom, left**. This is often abbreviated as **TRBL** (pronounced "trouble").

### Example

```css
/* Single border */
border: 2px solid #000;

/* Individual sides */
border-top: 2px solid #000;
border-right: 2px dashed #555;
border-bottom: 2px dotted #888;
border-left: 2px double #ccc;
```

### Additional Resources

For creative border ideas and advanced techniques, visit [CSS-Tricks](https://css-tricks.com).

# Shadows

Shadows can enhance the visual appeal of your elements by adding depth and dimension. CSS provides two main properties for applying shadows:

1. **Box Shadows**: Use the `box-shadow` property to add shadows to elements like divs, buttons, or containers.
2. **Text Shadows**: Use the `text-shadow` property to apply shadows to text, creating a subtle or dramatic effect.

### Example: Box Shadow

```css
/* Adding a shadow to a box */
box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.3);
```

### Example: Text Shadow

```css
/* Adding a shadow to text */
text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
```

Experiment with these properties to create visually engaging designs.

# Excercises

1. Create a table as shown below. Use pseudo-class selectors to highlight the odd rows.

### Table Structure Breakdown

The following Emmet abbreviation creates a table with a header, body, and footer:

```emmet
table>(thead>tr>th*3)+(tbody>(tr>td*3)*3)+(tfoot>tr>(th[colspan=2])+th)
```

#### Explanation:

1. **`table`**: Creates a `<table>` element.
2. **`>`**: Indicates a direct child relationship.
3. **`thead>tr>th*3`**:

- Creates a `<thead>` element.
- Inside `<thead>`, creates a `<tr>` (table row).
- Inside `<tr>`, creates 3 `<th>` (table header) elements.

4. **`+`**: Adds a sibling element.
5. **`tbody>(tr>td*3)*3`**:

- Creates a `<tbody>` element.
- Inside `<tbody>`, creates 3 `<tr>` (table rows).
- Inside each `<tr>`, creates 3 `<td>` (table data) elements.

6. **`+`**: Adds another sibling element.
7. **`tfoot>tr>(th[colspan=2])+th`**:

- Creates a `<tfoot>` element.
- Inside `<tfoot>`, creates a `<tr>` (table row).
- Inside `<tr>`, creates:
  - A `<th>` with a `colspan` attribute set to `2`.
  - Another `<th>` as a sibling.

#### Resulting HTML:

```html
<table>
  <thead>
    <tr>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th colspan="2"></th>
      <th></th>
    </tr>
  </tfoot>
</table>
```
