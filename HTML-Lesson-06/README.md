# 📄 Lesson 06: Building a Services Section with CSS Grid & Advanced Hover Effects

Welcome to Lesson 06! You’ve mastered Flexbox for one-dimensional layouts. Now, it’s time to level up with **CSS Grid**, the powerhouse for creating complex, two-dimensional layouts. In this lesson, you’ll build a stunning “Services” section featuring a grid of cards with beautiful hover animations.

This is where your website starts to look truly professional.

---

## 🎯 Learning Objectives

By the end of this lesson, you will be able to:

*   Use **CSS Grid** to create a responsive, multi-column layout for a services section.
*   Understand and apply Grid properties like `grid-template-columns`, `gap`, and `grid-auto-rows`.
*   Create sophisticated **CSS Hover Effects** using `transition`, `transform`, and pseudo-elements (`::before`, `::after`).
*   Master **Positioning** (`position: relative`, `position: absolute`) to layer elements like text overlays on images.
*   Use the `object-fit` property to control how images are resized within their containers.
*   Apply `box-shadow` for depth and visual feedback on hover.
*   Utilize CSS Variables for a consistent color theme.

---

## 📝 Code Breakdown

This lesson focuses on the new `.services-section` and its child elements in your `style.css`, and the corresponding HTML structure you need to add to `home.html`.

### 1. The HTML Structure (Add to `home.html`)

You need to add this new section *after* the `<main>` element but *before* the closing `</body>` tag in your `home.html` file.

```html
<!-- Add this inside the <body>, after </main> -->
<section class="services-section">
    <h3>Our Services</h3>
    <div class="service-container">
        <div class="service-item">
            <img src="./images/service1.jpg" alt="Service 1">
            <p>Web Design</p>
        </div>
        <div class="service-item">
            <img src="./images/service2.jpg" alt="Service 2">
            <p>Development</p>
        </div>
        <div class="service-item">
            <img src="./images/service3.jpg" alt="Service 3">
            <p>SEO</p>
        </div>
    </div>
</section>
```

*   **`<section>`**: A semantic element to group thematically related content.
*   **`.service-container`**: The Grid container that holds all the service cards.
*   **`.service-item`**: Each individual card, containing an image and a text overlay.

> **Important:** You need to create an `images` folder and add three placeholder images named `service1.jpg`, `service2.jpg`, and `service3.jpg`. If you don't have images, you can use free stock photos or even solid color placeholders.

### 2. The CSS: Grid & Magic

The real magic happens in your `style.css` file.

#### A. Styling the Section

```css
.services-section {
    width: 100vw;
    height: 500px;
    background-color: var(--white);
    padding: 100px 0;
}
.services-section h3 {
    width: 100%;
    text-align: center;
    font-size: 50px;
    margin: 0 0 50px 0;
}
```

This sets up a full-width, white section with a large, centered heading.

#### B. The Grid Container

```css
.service-container {
    width: 100%;
    display: grid; /* This is the key! */
    grid-template-columns: repeat(3, 1fr); /* Creates 3 equal columns */
    /* grid-template-rows: 350px; */ /* Optional: Define row height */
    gap: 20px; /* Space between grid items */
    justify-content: center;
    align-items: center;
}
```

*   **`display: grid;`**: This turns the container into a CSS Grid.
*   **`grid-template-columns: repeat(3, 1fr);`**: This is the heart of the layout. It creates 3 columns, each taking up 1 fraction (`1fr`) of the available space, making them equal width.
*   **`gap: 20px;`**: Adds a 20-pixel gap between each grid item (both rows and columns).

#### C. Styling the Grid Items (Cards)

```css
.service-item {
    height: 350px;
    width: 350px;
    position: relative; /* Crucial for absolute positioning of child elements */
    transition: all 300ms ease-in-out; /* Smooth transition for hover effects */
    border-radius: 10px;
    overflow: hidden; /* Ensures content doesn't spill out of the rounded corners */
}
```

*   **`position: relative;`**: This allows the `<p>` tag (the text overlay) to be positioned absolutely *relative to this card*.
*   **`transition: all 300ms ease-in-out;`**: Makes any property change (like `box-shadow` or `transform`) animate smoothly over 300 milliseconds.

#### D. The Image

```css
.service-item img {
    position: relative;
    width: 100%;
    height: 100%;
    object-fit: cover; /* Ensures image covers the area without distortion */
    border-radius: 10px;
}
```

*   **`object-fit: cover;`**: This is essential. It makes the image fill its container while maintaining its aspect ratio, cropping if necessary. This prevents awkward stretching.

#### E. The Text Overlay

```css
.service-item p {
    position: absolute; /* Positions text ON TOP of the image */
    top: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: var(--white);
    font-size: 50px;
    text-align: center;
    text-transform: capitalize;
    text-shadow: 5px 3px 5px var(--page-color);
    z-index: 100; /* Ensures text is above other elements */
    margin: 0;
}
```

*   **`position: absolute;`**: Takes the text out of the normal flow and positions it relative to the nearest positioned ancestor (the `.service-item` with `position: relative`).
*   **`z-index: 100;`**: Controls the stacking order. A higher number means it appears on top.

#### F. The Advanced Hover Effect

This is where things get really cool. Instead of just changing the color, we create a dynamic overlay that grows on hover.

```css
/* Creates an invisible overlay that grows on hover */
.service-item::before {
    content: "";
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 0; /* Starts at 0 height */
    background-color: #343434;
    opacity: 0.5;
    z-index: 50;
    border-radius: 10px;
    transition: all 300ms ease-in-out; /* Animates the height change */
}

/* Triggered when hovering over the card */
.service-item:hover {
    box-shadow: 5px 5px 5px var(--page-color); /* Adds a subtle shadow */
}

/* On hover, the ::before pseudo-element grows to full height */
.service-item:hover::before {
    height: 100%;
}
```

*   **`::before` pseudo-element**: Creates a virtual element that acts as a darkening overlay.
*   **`height: 0;` initially, `height: 100%;` on hover**: This is the core of the animation. The overlay starts invisible (0 height) and grows to cover the entire card when hovered.
*   **`transition` on `::before`**: Makes the height change smooth and animated.

---

## 🛠 Your Tasks

1.  **Update Your HTML:**
    *   Open `home.html`.
    *   Add the `<section class="services-section">...</section>` code block shown above, placing it right after the closing `</main>` tag.

2.  **Prepare Your Images:**
    *   Create a new folder named `images` in your project directory.
    *   Find or create three images and save them as `service1.jpg`, `service2.jpg`, and `service3.jpg` inside the `images` folder.
    *   *(Optional but recommended)*: Also create folders for the background images used in the `<main>` section (`child.png`, `RE4wyTK.jpg`) if you haven't already.

3.  **Observe the Layout:**
    *   Open `home.html` in your browser.
    *   Scroll down. You should see a white section titled “Our Services” with three beautifully arranged cards in a grid.

4.  **Hover and Marvel:**
    *   Move your mouse over one of the service cards.
    *   Watch as a dark overlay smoothly animates up from the bottom, and a subtle shadow appears around the card. This is pure CSS magic!

5.  **Experiment:**
    *   In `style.css`, change `grid-template-columns: repeat(3, 1fr);` to `grid-template-columns: repeat(2, 1fr);`. Refresh. The grid now has 2 columns.
    *   Change the `gap` value from `20px` to `50px`.
    *   Change the `font-size` for the service titles (the `<p>` tag inside `.service-item`) from `50px` to `30px`.
    *   Try changing the `background-color` in the `.service-item::before` rule to `var(--primary)`.

---

## 💡 Key Takeaway: CSS Grid vs. Flexbox

*   **Flexbox** is ideal for laying out items in a **single row or column**. Think navigation bars, centering content, or a simple row of cards.
*   **CSS Grid** is designed for **two-dimensional layouts** (rows AND columns). Think entire page layouts, image galleries, or complex dashboards.

They are complementary tools, not competitors. Use the right tool for the job!

---

## ➡️ What's Next?

In Lesson 07, we’ll tackle **Responsive Design** using **Media Queries**. You’ll learn how to make your beautiful grid and header adapt perfectly to mobile phones and tablets, ensuring your website looks great on any device.

You’re building incredible things — keep going! 🏆