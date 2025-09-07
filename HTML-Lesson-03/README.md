# 📄 Lesson 03: Mastering CSS Selectors, Properties & The Cascade

Welcome to Lesson 03! You’ve learned how to create HTML structure and link external stylesheets. Now, it’s time to dive deep into **CSS** — the language that makes your websites beautiful.

In this lesson, you’ll explore different types of CSS selectors, learn about powerful text and layout properties, understand how the **Cascade** and **Specificity** determine which styles win, and see how to use developer comments for organization.

---

## 🎯 Learning Objectives

By the end of this lesson, you will be able to:

*   Use **Class Selectors** (`.classname`) and **ID Selectors** (`#idname`) to target specific elements.
*   Understand CSS **Specificity Hierarchy**: Tag < Class < ID < Inline Style.
*   Apply advanced **Text Styling** properties like `line-height`, `text-align`, `text-indent`, and `font-style`.
*   Manipulate images with properties like `border-radius` and `background-color`.
*   Understand how comments work in CSS and HTML for code organization.
*   Use the `@import` rule to include external fonts or stylesheets (commented example).

---

## 📝 Code Breakdown

This lesson combines your `index.html` and `style.css` files to show a more complex and realistic styling scenario.

### 1. CSS Selectors & Specificity

Your CSS file (`style.css`) demonstrates how different selectors target elements and how specificity works.

```css
/* Class Selector */
.bodystyle {
    font-family: 'Cairo';
    font-size: 20px;
    line-height: 25px; /* Controls spacing between lines of text */
}

/* Tag Selector */
a {
    color: red;
    text-decoration: none;
    word-spacing: 50px; /* Adds space between words */
}

/* Another 'a' rule. The LAST one wins for the same specificity level. */
a {
    color: darkgoldenrod; /* This will override 'red' above */
}

/* ID Selector - Highest Specificity (except inline style) */
#githubImage {
    width: 50px; /* This targets the element with id="githubImage" */
}
```

*   **Specificity Order (Low to High)**:
    1.  **Tag/Element Selector** (e.g., `p`, `h1`, `a`)
    2.  **Class Selector** (e.g., `.bodystyle`, `.imgborder`)
    3.  **ID Selector** (e.g., `#githubImage`, `#upworkImage`)
    4.  **Inline Style** (e.g., `style="width: 200px;"` in HTML) - *Highest Priority*

> **Key Insight:** In your HTML, the GitHub image has `id="githubImage"` (which sets width to 50px in CSS) *and* `style="width: 200px;"`. The **inline style wins** due to higher specificity, so the image will be 200px wide, not 50px.

### 2. Advanced Text Styling

The CSS for the `<p>` tag introduces several properties for fine-tuning text layout:

```css
p {
    font-size: 20px;
    color: rgb(75,131,7);
    line-height: 32px; /* Increased space between lines */
    font-style: oblique; /* Slanted text */
    text-align: justify; /* Stretches text to fill the line width */
    text-indent: 50px; /* Indents the first line of the paragraph */
}
```

### 3. Image Styling & Classes

You can apply multiple classes to a single element for modular styling.

```html
<!-- In HTML -->
<img src="./github.svg" class="imgborder smallimg" id="githubImage" style="width: 200px;">
```

```css
/* In CSS */
.imgborder {
    border-radius: 50% 35%; /* Creates an oval/rounded corner effect */
}

.smallimg {
    width: 150px; /* This will be overridden by the inline style */
    background-color: blueviolet; /* Adds a background behind the image */
}
```

### 4. Comments & Organization

Both files are filled with comments (`<!-- ... -->` in HTML, `/* ... */` in CSS). These are ignored by the browser but are crucial for you and other developers.

```css
/* This is a CSS comment. It explains what the code does. */
/* height: 300px; */ /* This line is commented OUT and won't run. */

<!-- This is an HTML comment -->
<!-- Style order in HTML CSS -->
<!-- TAG Class ID Style -->
```

### 5. HTML Enhancements

Your `index.html` now includes more robust elements:
*   A longer **Lorem Ipsum** paragraph to see text styling in action.
*   An input field with attributes like `placeholder`, `value`, and `id`.
*   An image with an `alt` attribute for accessibility (text shown if image fails to load).
*   A comment explicitly stating the **Specificity Order**.

---

## 🛠 Your Tasks

1.  **Set Up Your Files:**
    *   Ensure you have `index.html` and `style.css` (rename `style.txt` to `style.css`) in the same folder.
    *   Make sure you have `upwork.svg` and `github.svg` images in the folder.

2.  **Observe Specificity:**
    *   Open `index.html` in your browser.
    *   Find the GitHub image. Notice its width is 200px, even though the `#githubImage` rule in CSS sets it to 50px. This proves **inline styles have the highest priority**.
    *   **Experiment:** Remove `style="width: 200px;"` from the GitHub image in your HTML. Refresh the browser. Now the image should be 50px wide, as defined by the ID selector.

3.  **Experiment with Text:**
    *   In `style.css`, change the `text-indent` value for the `p` selector from `50px` to `0`. Refresh and see how the first line of the paragraph changes.
    *   Change `text-align: justify;` to `text-align: center;`.

4.  **Play with Classes:**
    *   Add the class `smallimg` to the Upwork image in your HTML: `<img src="./upwork.svg" class="imgborder smallimg">`.
    *   Refresh. The image should now have a violet background and try to be 150px wide (unless overridden by another rule).

5.  **(Optional) Add a Font:**
    *   Uncomment the Google Fonts `<link>` tag in the HTML `<head>` and the `font-family: "Cookie";` line in the `.bodystyle` class in CSS.
    *   Refresh to see a new, fancy font!

---

## 💡 Key Takeaway: The Cascade

CSS stands for **Cascading** Style Sheets. This means styles "cascade" down, and rules can override each other based on:
1.  **Specificity** (ID beats Class, Class beats Tag).
2.  **Source Order** (Later rules override earlier ones if specificity is equal).
3.  **Importance** (`!important` flag, which you should generally avoid).

Understanding this cascade is fundamental to debugging and mastering CSS.

---

## ➡️ What's Next?

In Lesson 04, we’ll tackle the **CSS Box Model** — understanding `margin`, `padding`, and `border` — and start creating real layouts using `display` properties like `block`, `inline`, and `inline-block`.

You’re building a solid foundation! Keep experimenting.