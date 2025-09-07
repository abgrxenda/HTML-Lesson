# 📄 Lesson 01: Your First HTML Page & Inline Styling

Welcome to Lesson 01! In this lesson, you'll create your very first HTML webpage and learn how to apply basic styles directly within your HTML elements using the `style` attribute.

This is your "Hello World" moment for web development. Let's dive in!

---

## 🎯 Learning Objectives

By the end of this lesson, you will be able to:

*   Understand the basic structure of an HTML document.
*   Create and use common HTML elements like headings (`<h1>`, `<h3>`), paragraphs (`<p>`), links (`<a>`), horizontal rules (`<hr>`), and images (`<img>`).
*   Add interactive elements like text and password input fields (`<input>`).
*   Apply basic CSS styles directly to elements using the `style` attribute to change color, font size, width, and remove default link styling.

---

## 📝 Code Breakdown

Let's walk through the code in your `index.txt` (which should be saved as `index.html`):

```html
<!DOCTYPE html>
<html>
    <title>
    </title>
    <body>
        <!-- A red link without underline -->
        <a href="https://google.com" style="color: red; text-decoration: none;">
            This is first Selamunalykum
        </a>

        <!-- A large, aqua-colored heading -->
        <h1 style=" color:aqua">
            AlykumSelam second line
        </h1>

        <!-- A smaller heading -->
        <h3 style="font-size: small;">
            this is H3
        </h3>

        <!-- A paragraph with green-yellow text -->
        <p style="font-size: 20px; color: greenyellow;">
            third line
        </p>

        <!-- A horizontal line to separate content -->
        <hr>

        <!-- A text input field -->
        <input type="text">
        <br> <!-- Line break -->
        <br> <!-- Another line break -->

        <!-- A password input field (characters are hidden) -->
        <input type="password">
        <br>
        <br>

        <!-- An image with a fixed width -->
        <img src="./upwork.svg" style="width:200px">
    </body>
</html>
```

### Key Concepts Introduced

1.  **Document Structure:**
    *   `<!DOCTYPE html>`: Declares this is an HTML5 document.
    *   `<html>`: The root element of the page.
    *   `<title>`: (Currently empty) This is where the title of your webpage (shown in the browser tab) goes.
    *   `<body>`: Contains all the content you see in the browser window.

2.  **Common Elements:**
    *   `<a href="...">`: Creates a hyperlink. The `href` attribute specifies the destination URL.
    *   `<h1>`, `<h3>`: Heading elements. `<h1>` is the most important, `<h3>` is less important.
    *   `<p>`: Defines a paragraph of text.
    *   `<hr>`: Creates a thematic break (horizontal line).
    *   `<input>`: Creates an interactive control. `type="text"` for regular text, `type="password"` for masked input.
    *   `<br>`: Inserts a single line break.
    *   `<img src="...">`: Embeds an image. The `src` attribute specifies the image file path.

3.  **Inline CSS Styling:**
    *   The `style` attribute allows you to add CSS rules directly to an HTML element.
    *   Examples used:
        *   `color: red;` / `color: aqua;` / `color: greenyellow;`: Changes the text color.
        *   `font-size: small;` / `font-size: 20px;`: Changes the size of the text.
        *   `text-decoration: none;`: Removes the underline from the link.
        *   `width: 200px;`: Sets the width of the image to 200 pixels.

---

## 🛠 Your Tasks

1.  **Open in Browser:** Double-click the `index.html` file to open it in your default web browser. You should see your styled content!
2.  **Experiment:** Try changing the values in the `style` attributes. For example:
    *   Change `color: red;` to `color: blue;` on the link.
    *   Change `width:200px` to `width:100px` on the image.
    *   Add `background-color: black;` to the `<body>` tag.
    *   Refresh the browser to see your changes.
3.  **Add a Title:** Inside the `<title>` tags, add some text (e.g., `My First Webpage`). Refresh the browser and look at the tab at the top – your title should appear there!

---

## 💡 Pro Tip

While inline styling (using the `style` attribute) is great for quick changes and learning, it's not the best practice for larger projects. In future lessons, you'll learn how to use separate CSS files to keep your styles organized and reusable.

---

## ➡️ What's Next?

In Lesson 02, we'll dive deeper into HTML structure, learn about semantic elements, and start using internal and external CSS stylesheets to style our pages more efficiently.

Great job on completing your first lesson! 🎉