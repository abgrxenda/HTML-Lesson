# 📄 Lesson 05: Mastering Layouts with CSS Flexbox & CSS Variables

Welcome to Lesson 05! You’ve built a header and navigated between pages. Now, it’s time to take control of your entire webpage layout using **CSS Flexbox** and learn how to manage your styles efficiently with **CSS Variables (Custom Properties)**.

This lesson transforms your `home.html` from a simple header into a full-page layout with a styled hero section, introducing powerful, modern CSS techniques.

---

## 🎯 Learning Objectives

By the end of this lesson, you will be able to:

*   Use **CSS Flexbox** to create complex, responsive layouts for entire sections (`<main>`, `<div>`).
*   Understand and apply Flexbox properties like `flex-direction`, `justify-content`, and `align-items` on nested containers.
*   Create and use **CSS Variables** (Custom Properties) to define reusable values (colors, fonts, sizes) for consistent theming.
*   Apply advanced background styling using `background-image`, `background-position`, and `background-size`.
*   Use the `calc()` function for dynamic sizing based on viewport units (`vw`, `vh`).
*   Understand the `:before` pseudo-element for adding decorative content.

---

## 📝 Code Breakdown

This lesson focuses on the new content in `home.html` (the `<main>` section) and the sophisticated styling in `style.css`.

### 1. CSS Variables: The Heart of Your Theme

The `:root` selector in your CSS defines global variables. This is a best practice for managing themes.

```css
:root {
    --primary: darkgoldenrod;
    --secondary: #2caa50;
    --theme: rgb(75,131,7);
    --page-color: #343434;
    --font-header: bold 20px 'Cairo';
    --font-paragraph: 'Exo';
}
```

You can then use these variables anywhere in your stylesheet with `var()`:

```css
body {
    background-color: var(--page-color); /* Uses the --page-color variable */
    margin: 0;
}
a {
    color: var(--primary); /* Link color is now darkgoldenrod */
}
h1 {
    color: var(--theme); /* Heading color is now rgb(75,131,7) */
    font-size: 60px;
}
```

**Why it’s great:** If you want to change your primary color site-wide, you only need to update it in *one place* (`--primary` in `:root`).

### 2. The Main Section: A Flexbox Hero

Your `home.html` now includes a `<main>` section with content.

```html
<main>
    <div class="main-div">
        <h1>Welcome to the page</h1>
        <div class="paragraph">
            <p>Lorem ipsum dolor sit amet...</p>
            <p>Lorem ipsum dolor sit amet...</p>
        </div>
    </div>
</main>
```

The CSS for `<main>` uses Flexbox to center its content vertically and applies a stunning dual-background.

```css
main {
    height: calc(100vh - 100px); /* Full viewport height minus header height */
    width: 100vw; /* Full viewport width */
    background-color: var(--primary);
    /* Two background images! */
    background-image: url(child.png), url(RE4wyTK.jpg);
    background-repeat: no-repeat;
    background-position: bottom center, top center; /* Position each image */
    background-size: 25%, cover; /* Size each image */
    display: flex; /* Flexbox container */
    align-items: center; /* Vertically center the child (.main-div) */
}
```

*   **`calc(100vh - 100px)`**: Dynamically calculates the height. `100vh` is 100% of the viewport height, minus `100px` for the header.
*   **Multiple Backgrounds**: You can layer multiple images using `background-image`, controlling each with `background-position` and `background-size`.

### 3. Nested Flexbox for Content

The content inside `<main>` is also controlled by Flexbox for perfect alignment.

```css
/* Centers the heading and paragraph container horizontally */
main div.main-div {
    text-align: center;
    font: var(--font-header);
}

/* Makes the two paragraphs sit side-by-side */
main div div.paragraph {
    display: flex;
    font-family: var(--font-paragraph);
}

/* Adds padding around each paragraph */
div.paragraph p {
    color: whitesmoke;
    padding: 100px;
}
```

### 4. Advanced Navigation Styling

The CSS for the navigation menu (`nav ul`) introduces the `:before` pseudo-element to add an icon before each menu item.

```css
nav ul li:before {
    content: "тнХ "; /* This adds "тнХ " before each <li> */
}
```

*(Note: The "тнХ" appears to be placeholder text or an encoding artifact. You would typically use an icon font like Font Awesome or an emoji here, e.g., `content: "★ ";`)*.

### 5. Dynamic Navigation Width

The `nav` element uses `calc()` with viewport units for a more responsive width.

```css
nav {
    width: calc(100vw - 50%); /* Width is 50% of the viewport */
    left: calc(100vw - 75%); /* Positions it 25% from the left */
    right: calc((100vw - 75%)); /* Positions it 25% from the right */
    position: relative;
}
```

---

## 🛠 Your Tasks

1.  **Set Up Your Files:**
    *   Ensure `home.html` and `style.css` are in your project folder.
    *   **Important:** You need background images! Find or create two images named `child.png` and `RE4wyTK.jpg` and place them in your folder. If you don't have them, you can comment out the `background-image` line in the `main` selector to avoid broken images.

2.  **Observe the Layout:**
    *   Open `home.html` in your browser.
    *   You should see a full-page layout with a header, a large centered heading, and two side-by-side paragraphs, all sitting on a beautiful background.

3.  **Experiment with Variables:**
    *   Open `style.css`.
    *   Change the value of `--primary` in the `:root` from `darkgoldenrod` to `deepskyblue`.
    *   Refresh the browser. Notice how the background of the `<main>` section and the color of the `<h1>` heading both change? That’s the power of variables!

4.  **Play with Flexbox:**
    *   In the `main div div.paragraph` rule, change `display: flex;` to `display: block;`. Refresh. The paragraphs will stack vertically instead of sitting side-by-side.
    *   Change it back to `flex`. Now, add `flex-direction: column;` to the same rule. Refresh. They stack vertically again, but controlled by Flexbox.

5.  **Fix the Nav Icons (Optional):**
    *   Find the `nav ul li:before` rule.
    *   Change the `content` value to something fun, like `content: "★ ";` or `content: "→ ";`.

---

## 💡 Key Takeaway: Flexbox is Your Friend

Flexbox is designed for laying out components in one dimension (a row *or* a column). It’s perfect for:
*   Centering content (horizontally and/or vertically).
*   Creating navigation bars.
*   Building card layouts.
*   Distributing space between items.

Mastering Flexbox is essential for modern web development.

---

## ➡️ What's Next?

In Lesson 06, we’ll explore **CSS Grid**, the two-dimensional counterpart to Flexbox, which allows you to create complex grid-based layouts for your entire page or specific components.

You’re now styling like a pro! Keep up the amazing work.