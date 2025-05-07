# CSS Basics

In this guide, we will explore the essential CSS concepts you need to build beautiful and functional web pages.

## Topics Covered

- Various ways to provide CSS
- Normalizing CSS
- CSS Selectors
- Colors
- Gradients
- Borders
- Shadows

---

## Providing CSS

CSS can be provided in three main ways:

1. **Embedded Stylesheets**: CSS is written within a `<style>` tag in the HTML document.
2. **External Stylesheets**: CSS is written in a separate `.css` file and linked to the HTML document using a `<link>` tag.
3. **Inline Styles**: CSS is applied directly to an HTML element using the `style` attribute.

### Commenting in HTML and CSS

- To comment out a block of HTML, use the following syntax:

  ```html
  <!--
    <div>
      <h1>Title</h1>
      <p>Content</p>
    </div>
  -->
  ```

- To comment out a block of CSS, use this syntax:

  ```css
  /* body {
    background-color: #f0f0f0;
  } */
  ```

---

## Normalizing CSS

Every browser has its own default CSS styles, which can lead to inconsistencies in how web pages are displayed. To address this, we use **Normalize.css**.

- **Normalize.css** is a small CSS file that provides better cross-browser consistency in the default styling of HTML elements.
- You can find it here: [Normalize.css](http://necolas.github.io/normalize.css).

Normalizing CSS is an important step in front-end development, and we will always use Normalize.css in our projects.

---

## CSS Selectors

CSS selectors are used to target HTML elements for styling. There are several types of selectors:

### Basic Selectors

1. **Type Selector**: Targets elements by their tag name.
2. **Class Selector**: Targets elements with a specific class.
3. **ID Selector**: Targets elements with a specific ID.
4. **Attribute Selector**: Targets elements based on their attributes.

#### Class vs. ID

- **Class**: Reusable and can be applied to multiple elements.
- **ID**: Unique and should only be used once per page.

#### Examples

- Selecting an element by ID:

  ```html
  <section id="products"></section>
  ```

  ```css
  #products {
    /* styles here */
  }
  ```

- Selecting an element by class:

  ```html
  <article class="product"></article>
  ```

  ```css
  .product {
    /* styles here */
  }
  ```

- Generating multiple elements with Emmet:

  ```html
  article.product*3
  ```

  This creates three `<article>` elements with the class `product`.

---

## Relational Selectors

Relational selectors target elements based on their relationship to other elements.

- `>`: Direct child selector.
- `+`: Adjacent sibling selector.
- `~`: General sibling selector.

### Pseudo-Class Selectors

Pseudo-classes target elements based on their state or position.

#### Examples

```css
/* Highlight the first paragraph in an article */
article p:first-of-type {
  font-size: 140%;
  font-style: italic;
}

/* Style links */
a:visited,
a:link {
  color: dodgerblue;
}

a:hover,
a:focus {
  color: deeppink;
}
```

---

## Pseudo-Elements

Pseudo-elements target specific parts of an element's content.

### Common Pseudo-Elements

- `::before`: Inserts content before an element.
- `::after`: Inserts content after an element.
- `::first-letter`: Styles the first letter of a block-level element.
- `::selection`: Styles the part of an element that the user has highlighted.

#### Example

```css
blockquote::before {
  content: "“";
  font-size: 2rem;
  color: #ccc;
}

p::first-letter {
  font-size: 2rem;
  font-weight: bold;
  color: #555;
}
```

---

## Selector Specificity

When multiple CSS rules target the same element, the browser determines which rule to apply based on **selector specificity**.

### Specificity Hierarchy

1. **ID Selectors** (`#id`) - Highest specificity.
2. **Class Selectors** (`.class`) - Medium specificity.
3. **Element Selectors** (`element`) - Lowest specificity.

---

## Inheritance

Some CSS properties naturally inherit values from their parent elements, such as `color` and `font-family`. Others do not.

### Keywords

- **`inherit`**: Forces inheritance of a property.
- **`initial`**: Resets a property to its default value.

#### Example

```css
p {
  color: dodgerblue;
}

strong {
  color: initial; /* Resets to default */
  border: inherit; /* Inherits from parent */
}
```

---

## Colors

CSS provides multiple ways to define colors:

1. **Named Colors**: e.g., `red`, `blue`.
2. **RGB**: e.g., `rgb(255, 0, 0)`.
3. **HSL**: e.g., `hsl(0, 100%, 50%)`.
4. **Hexadecimal**: e.g., `#FF0000`.

### Adding Transparency

- **RGBA**: e.g., `rgba(255, 0, 0, 0.5)`.
- **HSLA**: e.g., `hsla(0, 100%, 50%, 0.5)`.

---

## Gradients

Gradients create smooth transitions between colors.

### Types of Gradients

1. **Linear Gradients**: Transition in a straight line.
2. **Radial Gradients**: Transition outward in a circular or elliptical shape.

#### Example

```css
background: linear-gradient(to right, #ff7e5f, #feb47b);
background: radial-gradient(circle, #ff7e5f, #feb47b);
```

---

## Borders

The `border` property defines the appearance of an element's border.

### Example

```css
border: 2px solid #000;
border-top: 2px dashed #555;
```

---

## Shadows

Shadows add depth and dimension to elements.

### Box Shadow

```css
box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.3);
```

### Text Shadow

```css
text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
```

---

## Exercises

### 1. Create a Table with Highlighted Odd Rows

#### HTML Structure

```html
<table>
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
      <th>Header 3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row 1, Col 1</td>
      <td>Row 1, Col 2</td>
      <td>Row 1, Col 3</td>
    </tr>
    <tr>
      <td>Row 2, Col 1</td>
      <td>Row 2, Col 2</td>
      <td>Row 2, Col 3</td>
    </tr>
    <tr>
      <td>Row 3, Col 1</td>
      <td>Row 3, Col 2</td>
      <td>Row 3, Col 3</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th colspan="2">Footer 1</th>
      <th>Footer 2</th>
    </tr>
  </tfoot>
</table>
```

#### CSS

```css
tbody tr:nth-child(odd) {
  background-color: #f9f9f9;
}
```

---

### 2. Create a Styled Box

#### HTML

```html
<div class="box"></div>
```

#### CSS

```css
.box {
  width: 300px;
  height: 300px;
  background-color: tomato;
  box-shadow: 4px 4px 10px lightgrey;
}
```

---

This concludes the CSS Basics guide. Happy coding!
