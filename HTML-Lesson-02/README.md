# 📄 Lesson 02: Structuring Your Page & External CSS

Welcome back! In Lesson 01, you created a webpage using inline styles. Now, in Lesson 02, you'll learn how to properly structure your HTML document and move your styles into separate, reusable CSS files — a fundamental best practice for professional web development.

You'll also learn about important metadata that helps browsers and search engines understand your page.

---

## 🎯 Learning Objectives

By the end of this lesson, you will be able to:

*   Understand and use the `<head>` and `<body>` sections correctly.
*   Add essential metadata to your webpage using `<meta>` tags (description, viewport, author).
*   Link external CSS and JavaScript files to your HTML document.
*   Use internal CSS (inside `<style>` tags) to style elements.
*   Apply CSS classes to HTML elements for reusable styling.
*   Understand the difference between inline, internal, and external CSS.

---

## 📝 Code Breakdown

This lesson introduces a much more complete and professional HTML structure.

### 1. The Document Head (`<head>`)

The `<head>` section contains information *about* the document, not the visible content. It's crucial for SEO, browser behavior, and linking resources.

```html
<head>
    <title>HTML Lesson 02 | By ÖMER KADİR</title>
    <meta charset="UTF8">
    <meta name="description" content="This is the first HTML lesson for begginers">
    <meta name="viewport" content="width=device-width,initial-scale=1.0, maximum-scale=1">
    <meta name="author" content="ÖMER KADİR">
    <link rel="stylesheet" href="style.css">
    <link rel="shortcut icon" href="./favicon.ico">
    <script src="script.js"></script>
    <style>
        a{
            color: darkorange;
        }
    </style>
</head>
```

*   **`<title>`**: Sets the title shown in the browser tab and search engine results.
*   **`<meta charset="UTF8">`**: Defines the character encoding (essential for displaying text correctly).
*   **`<meta name="description" ...>`**: A brief summary of the page for search engines.
*   **`<meta name="viewport" ...>`**: **CRITICAL** for responsive design. Ensures the page scales correctly on mobile devices.
*   **`<meta name="author" ...>`**: Specifies the author of the document.
*   **`<link rel="stylesheet" href="style.css">`**: Links an **external CSS file** (`style.css`) to style the entire page.
*   **`<link rel="shortcut icon" ...>`**: Sets the small icon (favicon) shown in the browser tab.
*   **`<script src="script.js"></script>`**: Links an external JavaScript file (for future interactivity).
*   **`<style>...</style>`**: Contains **internal CSS**. Here, it styles all `<a>` tags (links) to be `darkorange`.

> **Note:** There's also a large block of CSS commented out (`<!-- ... -->`). This is likely the CSS from Lesson 01, now moved to `style.css`. Commenting it out lets you compare or revert easily.

### 2. The Document Body (`<body>`)

The `<body>` contains the visible content. Notice how the styles are now applied differently.

```html
<body class="bodystyle">
    <a href="https://google.com">This is first Selamunalykum</a>
    <h1>AlykumSelam second line</h1>
    <h3>this is H3</h3>
    <p>third line</p>
    <hr>
    <input type="text"><br><br>
    <input type="password"><br><br>
    <!-- Images now use CSS classes -->
    <img src="./upwork.svg" class="imgborder">
    <img src="./github.svg" class="imgborder smallimg" style="width: 200px;">
</body>
```

*   **`class="bodystyle"`**: Applies a CSS class named `bodystyle` to the entire body. This class is defined in your `style.css` file.
*   **`class="imgborder"` and `class="smallimg"`**: These classes are applied to the images. They define reusable styles (like a border or size) in the CSS file.
*   **Inline Style Still Present**: The second image also has `style="width: 200px;"`. This shows you can *combine* methods, but external CSS is preferred for maintainability.

---

## 🛠 Your Tasks

1.  **Create Supporting Files:**
    *   Create a new file named `style.css` in the same folder as your `index.html`.
    *   Create a new file named `script.js` (you can leave it empty for now).
    *   (Optional) Create or find a `favicon.ico` file and place it in the folder.

2.  **Move CSS to `style.css`:**
    *   Copy the CSS rules from the *commented-out* `<style>` block in your HTML.
    *   Paste them into your new `style.css` file.
    *   Your `style.css` should now contain:
        ```css
        a{
            color: red;
            text-decoration: none;
        }
        h1{
            color:rgb(8, 98, 98);
            font-size: 60px;
        }
        h3{
            font-size: small;
        }
        p{
            font-size: 20px;
            color: rgb(75,131,7);
        }
        img{
            width:200px;
        }
        /* Add styles for the new classes */
        .bodystyle {
            /* Add some background or padding, e.g., */
            background-color: #f0f0f0;
            padding: 20px;
        }
        .imgborder {
            border: 2px solid #333;
        }
        .smallimg {
            width: 100px; /* This will be overridden by the inline style on one image */
        }
        ```

3.  **Open in Browser:** Open `index.html` in your browser. The page should now be styled by your external `style.css` file!

4.  **Experiment:**
    *   Change a color in `style.css` and refresh the browser. See how it updates everywhere that style is used.
    *   Add a new CSS rule in `style.css` to style the `<hr>` tag (e.g., `hr { border: 1px dashed blue; }`).
    *   Try removing the `class="imgborder"` from one of the images. What happens?

---

## 💡 Key Takeaway: CSS Specificity

You might notice that the second image has both a class (`.smallimg` which sets `width: 100px;`) and an inline style (`style="width: 200px;"`). The inline style wins! This is due to **CSS Specificity**. Inline styles have the highest priority, followed by IDs, then classes, and finally element selectors. We'll cover this in more detail later.

---

## ➡️ What's Next?

In Lesson 03, we'll dive deeper into CSS selectors, the box model (margin, padding, border), and how to create beautiful layouts for your content.

You're doing great! Keep up the excellent work. 👏