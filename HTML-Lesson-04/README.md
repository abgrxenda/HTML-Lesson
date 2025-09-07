# 📄 Lesson 04: Building a Website Header & Navigating Between Pages

Welcome to Lesson 04! Now that you understand HTML structure and CSS styling, it’s time to build something more realistic: a **website header with navigation**.

This lesson introduces multi-page websites. You’ll learn how to create a navigation menu that links to different HTML files, a fundamental skill for building any website.

---

## 🎯 Learning Objectives

By the end of this lesson, you will be able to:

*   Structure a webpage using semantic HTML5 elements like `<header>` and `<nav>`.
*   Create a horizontal navigation menu using `<ul>` (unordered list) and CSS Flexbox.
*   Link between different HTML pages using relative file paths (e.g., `href="home.html"`).
*   Understand and use CSS Flexbox properties (`display: flex`, `justify-content`, `align-items`) to create layouts.
*   Apply styles to nested elements (e.g., styling `<li>` tags inside a `<ul>` inside a `<nav>`).

---

## 📝 Code Breakdown

This lesson introduces two new files: `home.html` (your main page) and an updated `style.css` containing styles for the header.

### 1. The HTML: `home.html`

This file represents the "Home" page of your website.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Home | Header Lesson</title>
        <!-- Essential meta tags for responsiveness and SEO -->
        <meta name="viewport" content="width=device-width,initial-scale=1.0, maximum-scale=1">
        <meta name="description" content="This is the first HTML lesson for begginers">
        <meta name="author" content="Zain Gamil">
        <!-- Link to the external stylesheet -->
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <!-- The Header Section -->
        <header>
            <!-- Logo Container -->
            <div class="header-logo">
                <img src="./github.svg" class="imgborder smallimg">
            </div>
            <!-- Navigation Menu -->
            <nav>
                <ul>
                    <li>Home</li>
                    <li>Products</li>
                    <li>About Us</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    </body>
</html>
```

*   **`<header>`**: A semantic element that typically contains introductory content or navigation links for its parent section.
*   **`<div class="header-logo">`**: A container for your logo (in this case, the GitHub SVG).
*   **`<nav>`**: A semantic element specifically for navigation links.
*   **`<ul>` and `<li>`**: An unordered list is the standard, semantic way to create a navigation menu. Each `<li>` represents a menu item.
*   **Linking Files**: Currently, the `<li>` items are just text. In the next step, you'll turn them into links to other pages.

### 2. The CSS: `style.css`

The stylesheet now includes rules to style the header and create a horizontal navigation bar.

```css
/* Style for the entire header */
header {
    background-color: #fbfff8; /* Light background color */
    height: 100px; /* Fixed height */
    display: flex; /* Uses Flexbox layout */
    align-items: center; /* Vertically centers children */
}

/* Style for the logo container */
div.header-logo {
    background-color: red; /* Placeholder background */
    width: fit-content; /* Width adjusts to content (the image) */
    height: 100px; /* Matches header height */
    margin-left: 20px; /* Adds space from the left edge */
}

/* Style for the navigation container */
nav {
    width: 50%; /* Takes up half the header width */
    left: 25%; /* Positions it 25% from the left (centering it) */
    right: 25%; /* Positions it 25% from the right */
    position: relative; /* Needed for 'left' and 'right' to work */
}

/* Style for the navigation list */
nav ul {
    list-style: none; /* Removes bullet points */
    color: rgb(107, 43, 43); /* Text color */
    font-family: Cairo; /* Font family */
    font-size: 20px; /* Font size */
    display: flex; /* Makes list items display horizontally */
    justify-content: space-evenly; /* Distributes items evenly with space between them */
    align-items: center; /* Vertically centers items within the ul */
    padding: 0; /* Removes default padding */
    margin: 0; /* Removes default margin */
}
```

*   **Flexbox Magic**: The key to the horizontal layout is `display: flex;` on both the `header` and the `nav ul`.
    *   `header { display: flex; }` makes the logo and nav sit side-by-side.
    *   `nav ul { display: flex; }` makes the list items (`<li>`) sit side-by-side.
*   **Centering**: `align-items: center;` vertically centers elements within their flex container.

---

## 🛠 Your Tasks

1.  **Set Up Your Files:**
    *   Save the provided code as `home.html`.
    *   Ensure your `style.css` file contains the header-related styles shown above (or the full content from the uploaded `style.txt`).
    *   Make sure `github.svg` is in your project folder.

2.  **Create Additional Pages:**
    *   Create three new, empty HTML files in the same folder:
        *   `products.html`
        *   `about.html`
        *   `contact.html`
    *   For now, you can just copy the basic structure of `home.html` into each file and change the `<title>` tag (e.g., `<title>Products | Header Lesson</title>`).

3.  **Add Navigation Links:**
    *   Open `home.html`.
    *   Turn the text inside each `<li>` into a clickable link using the `<a>` tag.
    *   Update your navigation list like this:
        ```html
        <nav>
            <ul>
                <li><a href="home.html">Home</a></li>
                <li><a href="products.html">Products</a></li>
                <li><a href="about.html">About Us</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
        ```
    *   **Important:** Since `home.html` is your current file, you could also use `href="#"` or `href="index.html"` if you plan to rename `home.html` to `index.html` (the default homepage).

4.  **Style the Links (Optional but Recommended):**
    *   Open `style.css`.
    *   Add a rule to style the navigation links. For example:
        ```css
        nav ul li a {
            text-decoration: none; /* Removes underline */
            color: rgb(107, 43, 43); /* Matches the list text color */
        }
        nav ul li a:hover {
            color: darkred; /* Changes color on hover */
        }
        ```

5.  **Open & Test:**
    *   Open `home.html` in your browser.
    *   You should see a header with a red logo box and a horizontal navigation menu.
    *   Click on the "Products," "About Us," and "Contact" links. They should take you to the respective (empty) pages you created.

---

## 💡 Key Takeaway: Relative Paths

The links use **relative paths** like `href="products.html"`. This tells the browser to look for a file named `products.html` in the *same folder* as the current file (`home.html`). This is the most common and flexible way to link between pages in a website.

---

## ➡️ What's Next?

In Lesson 05, we’ll dive deeper into **CSS Flexbox** and **CSS Grid**, the modern tools for creating complex, responsive layouts for your entire webpage, not just the header.

You’re now building real websites! Great job. 🚀