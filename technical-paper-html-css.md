# Technical Paper on HTML and CSS

## Introduction

HTML and CSS are the basic technologies used to build and style web pages. HTML provides the structure and meaning of the content, while CSS controls its appearance, layout, and responsiveness.

## 1. CSS Box Model

Every HTML element is treated as a box. The CSS box model consists of four parts:

* Content: The actual text or elements inside the box.
* Padding: Space between the content and border.
* Border: A line around the padding and content.
* Margin: Space outside the border.

```css
.box {
    width: 200px;
    padding: 20px;
    border: 2px solid black;
    margin: 10px;
    box-sizing: border-box;
}
```

Using box-sizing: border-box makes width and height easier to manage because padding and border are included in the declared size.

## 2. Inline and Block Elements

HTML elements are commonly classified as inline or block elements.

* Block elements start on a new line and normally take the available width. Examples: <div>, <p>, <h1>, and <section>.
* Inline elements stay within the same line and normally take only the required width. Examples: <span>, <a>, <strong>, and <em>.

```html
<div>Block element</div>
<span>Inline element</span>
<a href="#">Inline link</a>
```

The display property can change this behavior.

```css
span {
    display: block;
}
```

## 3. Positioning

CSS provides five important position values that control how an element is placed on a webpage.

1. `static`
   - This is the default position of an element.
   - The element follows the normal document flow.
   - top, right, bottom, and left do not affect it.

2. `relative`
   - The element remains in the normal document flow.
   - It can be moved from its original position using top, right, bottom, or left.
   - Its original space is still preserved.

3. `absolute`
   - The element is removed from the normal document flow.
   - It is positioned relative to its nearest positioned ancestor.
   - If no positioned ancestor exists, it is positioned relative to the initial containing block.

4. `fixed`
   - The element is removed from the normal document flow.
   - It is positioned relative to the viewport.
   - It stays in the same position even when the page is scrolled.
   - It is commonly used for fixed navigation bars or floating buttons.

5. `sticky`
   - The element behaves like a relatively positioned element until a specified scroll position is reached.
   - It then behaves like a fixed element within its containing block.
   - It is commonly used for sticky headers and navigation elements.


## 4. Common CSS Structural Classes

Structural classes are used to organize the layout of a page. Common examples include:

* .container for the main content area.
* .header for the top section.
* .nav for navigation.
* .main for primary content.
* .section for separate content sections.
* .footer for the bottom section.
* .row and .column for layout structures.

Using meaningful class names makes HTML and CSS easier to maintain.

## 5. Common CSS Styling Classes

Styling classes are commonly used to apply reusable visual properties.

Examples include:

* .text-center for centered text.
* .btn for buttons.
* .card for content cards.
* .hidden for hiding elements.
* .active for the currently selected element.
* .border for adding borders.

Reusable classes reduce repeated CSS code.

## 6. CSS Specificity

CSS specificity determines which rule is applied when multiple rules target the same element. In general, specificity increases in this order:

1. Element selectors, such as p.
2. Class, attribute, and pseudo-class selectors, such as .card or :hover.
3. ID selectors, such as #header.
4. Inline styles.

For example:

```css
p {
    color: blue;
}

.text {
    color: green;
}
```

If a paragraph has the text class, the class rule has higher specificity and the text becomes green.

## 7. Responsive Queries

Responsive design allows a website to work on different screen sizes. CSS media queries apply styles based on conditions such as screen width.

```css
.container {
    width: 80%;
}

@media (max-width: 600px) {
    .container {
        width: 95%;
    }
}
```

A mobile-first approach is also commonly used, where the basic styles are designed for small screens and larger-screen styles are added with media queries.

## 8. Flexbox and Grid

Flexbox is mainly useful for arranging items in one dimension, either as a row or a column.

```css
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

CSS Grid is useful for two-dimensional layouts involving rows and columns.

```css
.gallery {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Flexbox is often suitable for navigation bars and small component layouts, while Grid is useful for larger page or gallery layouts.

## 9. Common Header Meta Tags

Meta tags provide information about the HTML document and help browsers handle the page correctly.

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="A sample HTML and CSS page">
```

The character set supports common characters, the viewport tag improves responsive behavior on mobile devices, and the description provides a short summary of the page.

## 10. Semantic HTML and Accessibility

Semantic HTML uses elements according to their meaning rather than using <div> for everything. Common semantic elements include <header>, <nav>, <main>, <section>, <article>, and <footer>.

Semantic HTML improves document structure, accessibility, and search engine understanding. Images should also use meaningful alt text when appropriate.

## References

* [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
* [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [MDN Web Docs - CSS Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction)
* [MDN Web Docs - CSS Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* [MDN Web Docs - CSS Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Specificity)
* [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries)
* [MDN Web Docs - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout)
* [MDN Web Docs - CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout)
