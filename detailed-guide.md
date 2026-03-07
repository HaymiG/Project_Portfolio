# Portfolio - COMPLETE BEGINNER'S GUIDE (Every Line Explained)

> This guide explains EVERY single line of code in detail so you can understand it,
> memorize it, and write it from scratch for your mid exam.

---
---

# DAY 1 — Project Setup (HTML Boilerplate + CSS Reset)

## What you're doing today:
Creating the skeleton of your website (HTML) and resetting the browser's default styles (CSS).

---

## index.html — Full Explanation

```html
<!DOCTYPE html>
```
**What it does:** Tells the browser "This is an HTML5 document."
**Why we need it:** Without this, the browser might render your page in an old, weird mode called "quirks mode." Always put this as the VERY FIRST line.

---

```html
<html lang="en">
```
**What it does:** Opens the root HTML element. `lang="en"` tells the browser the page is in English.
**Why we need it:** Helps screen readers (for blind users) know what language to speak. Also helps Google understand your page.

---

```html
<head>
```
**What it does:** Opens the `<head>` section. This section contains **metadata** — information ABOUT the page that the user doesn't see directly.
**Think of it as:** The backstage of your webpage.

---

```html
  <meta charset="UTF-8">
```
**What it does:** Sets the character encoding to UTF-8.
**In simple words:** It tells the browser how to read text. UTF-8 supports ALL characters — English, Arabic, Chinese, emojis, etc.
**Without it:** Special characters might show as weird symbols like `Ã©` instead of `é`.

---

```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
```
**What it does:** Makes your website responsive (looks good on phones).
- `width=device-width` → The page width matches the device screen width
- `initial-scale=1.0` → No zoom when the page first loads
**Without it:** Your website would look tiny on a phone (like viewing a desktop site on mobile).

---

```html
  <title>Portfolio</title>
```
**What it does:** Sets the text that appears on the browser tab.
**Example:** When you open this page, the tab will say "Portfolio".

---

```html
  <link rel="stylesheet" href="style.css">
```
**What it does:** Connects your CSS file to this HTML file.
- `rel="stylesheet"` → Tells the browser "this linked file is a stylesheet"
- `href="style.css"` → The path to your CSS file
**Without it:** Your page would have NO styling — just plain black text on white background.

---

```html
</head>
```
**What it does:** Closes the `<head>` section. Everything after this is the visible page content.

---

```html
<body>

</body>
```
**What it does:** The `<body>` contains everything the user SEES on the page — text, images, buttons, etc.
**Right now it's empty** because we'll add content starting Day 2.

---

```html
</html>
```
**What it does:** Closes the entire HTML document. Every opening tag needs a closing tag.

---

### Complete index.html file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

</body>
</html>
```

---
---

## style.css — Full Explanation

### What is a "CSS Reset"?
Every browser (Chrome, Firefox, Safari) adds its own default styles. For example:
- `<h1>` has a big margin by default
- `<ul>` has bullet points by default
- `<body>` has a small margin around the edge

A CSS Reset **removes all these defaults** so you start from a clean slate and your website looks the same in every browser.

---

```css
/* ===== Reset & Base ===== */
```
**What it does:** This is a CSS **comment**. It does NOTHING — it's just a note for you (the developer).
**Syntax:** `/* your comment here */`
**Why use comments:** To organize your code into sections. Makes it easy to find things later.

---

```css
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```
**This is the most important reset. Let's break it down:**

`*` → The **universal selector**. It selects EVERY SINGLE element on the page (divs, paragraphs, headings, links, everything).

`*::before` → Selects every element's `::before` pseudo-element (a virtual element you can create with CSS).

`*::after` → Selects every element's `::after` pseudo-element.

**The comma `,`** means "and also". So we're selecting: every element AND their before/after pseudo-elements.

**Inside the curly braces `{ }`:**

- `margin: 0;` → Removes all outer spacing. By default, `<body>` has ~8px margin, `<h1>` has big margin, etc. Now everything starts with 0 margin.

- `padding: 0;` → Removes all inner spacing. By default, `<ul>` has left padding for bullets. Now everything starts with 0 padding.

- `box-sizing: border-box;` → This is CRUCIAL. By default, if you set `width: 200px` and add `padding: 20px`, the total width becomes 240px (200 + 20 + 20). With `border-box`, padding is INCLUDED in the width, so 200px stays 200px. This makes sizing WAY easier.

**EXAM TIP:** If asked "What does `box-sizing: border-box` do?" → Answer: "It makes padding and border included in the element's width and height, instead of added on top."

---

```css
html {
  scroll-behavior: smooth;
}
```
**What it does:** When you click a link that jumps to another section (like clicking "About" in the navbar), instead of instantly jumping there, the page will **smoothly scroll** to that section.
**Without it:** Clicking anchor links causes an instant, jarring jump.

---

```css
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #333;
  background: #fafafa;
}
```

- `font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;`
  - This is a **font stack**. The browser tries each font in order:
    1. First tries "Segoe UI" (Windows default)
    2. If not available, tries Tahoma
    3. Then Geneva (Mac)
    4. Then Verdana
    5. If none work, uses any `sans-serif` font
  - `sans-serif` = fonts without the little "feet" on letters (modern, clean look)

- `line-height: 1.6;` → Space between lines of text. 1.6 means 1.6 times the font size. Makes text easier to read. (Default is about 1.2, which feels cramped.)

- `color: #333;` → Sets the default text color. `#333` is a dark gray (not pure black `#000`, which is too harsh on eyes).
  - **How hex colors work:** `#333` is shorthand for `#333333`. Hex goes from `00` (none) to `FF` (full). So `#333` = a little bit of red + green + blue = dark gray.

- `background: #fafafa;` → Sets page background to a very light gray. Almost white, but slightly softer on the eyes than pure white `#fff`.

---

```css
a {
  text-decoration: none;
  color: inherit;
}
```
- `a` → Selects ALL `<a>` (anchor/link) elements.
- `text-decoration: none;` → Removes the default blue underline from links.
- `color: inherit;` → Makes links use the same color as their parent element, instead of the default blue.

---

```css
ul {
  list-style: none;
}
```
- `ul` → Selects ALL `<ul>` (unordered list) elements.
- `list-style: none;` → Removes the default bullet points (•) from lists.
**Why:** In our portfolio, we use `<ul>` for the nav menu, and we don't want bullets there.

---

```css
img {
  max-width: 100%;
}
```
- `img` → Selects ALL `<img>` elements.
- `max-width: 100%;` → Images will never be wider than their container. If a 2000px image is inside a 500px div, the image shrinks to 500px. Prevents images from overflowing and breaking the layout.

---

### Complete style.css file:
```css
/* ===== Reset & Base ===== */
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #333;
  background: #fafafa;
}

a {
  text-decoration: none;
  color: inherit;
}

ul {
  list-style: none;
}

img {
  max-width: 100%;
}
```

---
---

# DAY 2 — Navigation Bar HTML

## What you're building today:
A navigation bar (the menu at the top of the website) that has a logo on the left and links on the right.

## Key Concepts to Understand First:

### What is `<nav>`?
`<nav>` is a **semantic HTML element**. "Semantic" means it has meaning — it tells the browser "this is a navigation area." You could use `<div>` instead, but `<nav>` is better because:
1. Screen readers know it's navigation
2. Google knows it's navigation
3. Your code is more readable

### What are classes?
`class="navbar"` gives an element a name so you can style it with CSS.
- HTML: `<nav class="navbar">` → "This nav is called 'navbar'"
- CSS: `.navbar { ... }` → "Style anything with class 'navbar'"

### What is `#home`, `#about`, etc.?
These are **anchor links** (also called hash links). When you click `<a href="#home">`, the browser scrolls to the element with `id="home"`. We'll add those sections later.

---

## The Code (add inside `<body>` in index.html):

```html
  <!-- Navigation -->
  <nav class="navbar">
    <a href="#" class="logo">Portfolio</a>
    <ul class="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
```

### Line-by-line:

```html
  <!-- Navigation -->
```
An HTML comment. The browser ignores this. It's just a note for you.

---

```html
  <nav class="navbar">
```
- Opens a `<nav>` element (semantic: means "navigation")
- `class="navbar"` → We'll use this class name in CSS to style it

---

```html
    <a href="#" class="logo">Portfolio</a>
```
- `<a>` → A link element
- `href="#"` → Links to the top of the page (# alone means "top of page")
- `class="logo"` → We'll style this differently (bigger, bold, colored)
- `Portfolio` → The text that appears as the logo
- This is a text-based logo (no image needed)

---

```html
    <ul class="nav-links">
```
- `<ul>` → Unordered list. We use a list for navigation links because semantically, a menu IS a list of links.
- `class="nav-links"` → For CSS styling

---

```html
      <li><a href="#home">Home</a></li>
```
- `<li>` → List item
- `<a href="#home">` → When clicked, scrolls to the element with `id="home"` (our hero section, added Day 4)
- `Home` → The visible text
- **Each menu item follows this same pattern:** `<li><a href="#section-id">Link Text</a></li>`

---

```html
    </ul>
  </nav>
```
Closes the list and the nav. **Every opening tag must have a closing tag.**

---

### Your index.html should now look like:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- Navigation -->
  <nav class="navbar">
    <a href="#" class="logo">Portfolio</a>
    <ul class="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

</body>
</html>
```

**No CSS changes today** — we style it tomorrow.

---
---

# DAY 3 — Style Navigation Bar

## What you're doing today:
Making the navbar look professional — fixed at the top, horizontal layout, hover animations.

## Key CSS Concepts:

### What is `position: fixed`?
Normally, elements scroll with the page. `position: fixed` **locks** an element on the screen — it stays visible even when you scroll. Perfect for a navbar.

### What is Flexbox?
Flexbox is a CSS layout system. When you set `display: flex` on a container, its children line up in a row (by default).

**Think of it like this:** Imagine a shelf. `display: flex` turns a box into a shelf, and the items inside line up on that shelf.

Key flexbox properties:
- `display: flex;` → Activate flexbox
- `justify-content: space-between;` → Push items to opposite ends (logo left, links right)
- `align-items: center;` → Vertically center items

### What is `transition`?
Makes changes happen gradually instead of instantly. `transition: color 0.3s;` means "when the color changes, take 0.3 seconds to do it" — creating a smooth fade effect.

### What are pseudo-elements (`::after`)?
They let you create a fake element using CSS only (no HTML needed). We use `::after` to create an underline that appears when you hover over a link.

---

## The Code (add at the bottom of style.css):

```css
/* ===== Navbar ===== */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 18px 40px;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.06);
  z-index: 1000;
}
```

- `position: fixed;` → Navbar stays at the top even when scrolling
- `top: 0; left: 0; right: 0;` → Stick to the top edge, stretch from left to right
- `display: flex;` → Children (logo & links) go in a row
- `justify-content: space-between;` → Logo goes left, links go right, with space between
- `align-items: center;` → Vertically center everything
- `padding: 18px 40px;` → 18px top/bottom, 40px left/right (inner spacing)
  - **Shorthand:** `padding: top/bottom left/right;`
- `background: rgba(255, 255, 255, 0.95);`
  - `rgba` = Red, Green, Blue, Alpha(opacity)
  - `255, 255, 255` = white
  - `0.95` = 95% opaque (slightly see-through)
- `backdrop-filter: blur(10px);` → Blurs whatever is behind the navbar (glassmorphism effect)
- `box-shadow: 0 2px 20px rgba(0, 0, 0, 0.06);`
  - Creates a subtle shadow below the navbar
  - `0` = no horizontal offset
  - `2px` = 2px down
  - `20px` = 20px blur
  - `rgba(0,0,0,0.06)` = black at 6% opacity (very faint)
- `z-index: 1000;` → Makes the navbar appear ON TOP of everything else. Higher number = closer to you.

---

```css
.logo {
  font-size: 1.5rem;
  font-weight: 800;
  color: #4f46e5;
}
```
- `font-size: 1.5rem;` → 1.5 times the root font size (usually 16px, so 24px)
  - **rem** = "root em" — relative to the HTML root font size. Better than px for accessibility.
- `font-weight: 800;` → Extra bold (100=thin, 400=normal, 700=bold, 900=heaviest)
- `color: #4f46e5;` → An indigo/purple-blue color (our brand color throughout the site)

---

```css
.nav-links {
  display: flex;
  gap: 32px;
}
```
- `display: flex;` → Makes the list items go in a row (instead of stacked vertically)
- `gap: 32px;` → 32px space between each link

---

```css
.nav-links a {
  font-weight: 500;
  color: #555;
  transition: color 0.3s;
  position: relative;
}
```
- `.nav-links a` → Selects `<a>` elements INSIDE `.nav-links`
- `font-weight: 500;` → Medium weight (between normal 400 and bold 700)
- `color: #555;` → Medium gray
- `transition: color 0.3s;` → When color changes (on hover), take 0.3s to change smoothly
- `position: relative;` → Needed so the `::after` pseudo-element positions relative to this link

---

```css
.nav-links a::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: #4f46e5;
  transition: width 0.3s;
}
```
**This creates an invisible underline that will grow when you hover:**
- `content: "";` → REQUIRED for pseudo-elements. Even if empty, you must have this.
- `position: absolute;` → Position it relative to the link (which has `position: relative`)
- `bottom: -4px;` → Place it 4px below the bottom of the link text
- `left: 0;` → Start from the left edge
- `width: 0;` → Starts invisible (0 width)
- `height: 2px;` → The underline is 2px thick
- `background: #4f46e5;` → Indigo color
- `transition: width 0.3s;` → Animate the width change over 0.3 seconds

---

```css
.nav-links a:hover {
  color: #4f46e5;
}
```
- `:hover` → This style applies when the mouse is OVER the link
- Changes text color to indigo

---

```css
.nav-links a:hover::after {
  width: 100%;
}
```
- When hovering, the underline (pseudo-element) grows from `width: 0` to `width: 100%`
- Combined with the transition, this creates a smooth sliding underline effect

---
---

# DAY 4 — Hero Section HTML

## What you're building today:
The hero section — the big, impressive first thing visitors see. It has a greeting, your name, your title, a tagline, and two buttons.

## Key Concepts:

### What is a "Hero Section"?
The large banner area at the top of a website. It's the first thing people see and should grab their attention. Usually contains a headline, subtitle, and call-to-action buttons.

### What is `id` vs `class`?
- `id="home"` → A UNIQUE identifier. Only ONE element can have `id="home"`. Used for anchor links (`href="#home"`).
- `class="hero"` → A reusable name. Multiple elements can share the same class. Used for styling.

### What is a `<section>`?
A semantic HTML element that represents a standalone section of content. Better than using `<div>` because it tells the browser "this is a distinct section."

---

## The Code (add after `</nav>` in index.html):

```html
  <!-- Hero Section -->
  <section id="home" class="hero">
    <div class="hero-content">
      <p class="greeting">Hello, I'm</p>
      <h1>Your Name</h1>
      <h2>Full Stack Developer</h2>
      <p class="tagline">I build modern, responsive websites and web applications.</p>
      <div class="hero-buttons">
        <a href="#projects" class="btn btn-primary">View My Work</a>
        <a href="#contact" class="btn btn-outline">Contact Me</a>
      </div>
    </div>
  </section>
```

### Line-by-line:

```html
  <section id="home" class="hero">
```
- `<section>` → Semantic: represents a section of the page
- `id="home"` → When someone clicks "Home" in the navbar (`href="#home"`), the page scrolls here
- `class="hero"` → For CSS styling

---

```html
    <div class="hero-content">
```
- `<div>` → A generic container (no semantic meaning, just for grouping/styling)
- `class="hero-content"` → We'll use this to center and limit the width of the content

---

```html
      <p class="greeting">Hello, I'm</p>
```
- `<p>` → Paragraph element
- Small introductory text above your name

---

```html
      <h1>Your Name</h1>
```
- `<h1>` → The most important heading on the page. **Each page should have only ONE `<h1>`.**
- **Replace "Your Name" with your actual name!**

---

```html
      <h2>Full Stack Developer</h2>
```
- `<h2>` → Second-level heading. Your job title/role.

---

```html
      <p class="tagline">I build modern, responsive websites and web applications.</p>
```
- A short description of what you do

---

```html
      <div class="hero-buttons">
```
- A container to hold both buttons side by side

---

```html
        <a href="#projects" class="btn btn-primary">View My Work</a>
```
- This is a LINK styled to look like a button
- `href="#projects"` → Scrolls to the projects section
- `class="btn btn-primary"` → TWO classes! `btn` gives base button styles, `btn-primary` gives it a filled/solid look
- **Multiple classes:** You can give an element multiple classes separated by spaces

---

```html
        <a href="#contact" class="btn btn-outline">Contact Me</a>
```
- Same as above but `btn-outline` makes it a bordered/outlined button (no fill)

---

### Your index.html should now look like:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- Navigation -->
  <nav class="navbar">
    <a href="#" class="logo">Portfolio</a>
    <ul class="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- Hero Section -->
  <section id="home" class="hero">
    <div class="hero-content">
      <p class="greeting">Hello, I'm</p>
      <h1>Your Name</h1>
      <h2>Full Stack Developer</h2>
      <p class="tagline">I build modern, responsive websites and web applications.</p>
      <div class="hero-buttons">
        <a href="#projects" class="btn btn-primary">View My Work</a>
        <a href="#contact" class="btn btn-outline">Contact Me</a>
      </div>
    </div>
  </section>

</body>
</html>
```

---
---

# DAY 5 — Style Hero Section & Buttons

## What you're doing today:
Making the hero section beautiful with a gradient background, centered content, and styled buttons.

## Key Concepts:

### What is a CSS Gradient?
Instead of one solid color, a gradient smoothly blends between multiple colors.
- `linear-gradient(135deg, #eef2ff, #c7d2fe)` → Blends from light blue to medium blue at a 135° angle.

### What does `min-height: 100vh` mean?
- `vh` = **viewport height** (the visible browser window)
- `100vh` = 100% of the screen height
- `min-height: 100vh` = "Be at LEAST as tall as the full screen"
- This makes the hero section fill the entire screen

### What is `display: inline-block`?
Elements are either:
- **Block** (`<div>`, `<p>`, `<h1>`) → Takes full width, stacks vertically
- **Inline** (`<a>`, `<span>`) → Flows with text, can't set width/height
- **Inline-block** → Flows with text BUT you CAN set width, height, padding, margin

Links (`<a>`) are inline by default. We need `inline-block` so padding works properly on our buttons.

---

## The Code (add at the bottom of style.css):

```css
/* ===== Buttons ===== */
.btn {
  display: inline-block;
  padding: 12px 28px;
  border-radius: 6px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  border: 2px solid #4f46e5;
}
```
- `display: inline-block;` → Allows padding and sizing on our `<a>` links
- `padding: 12px 28px;` → 12px top/bottom, 28px left/right
- `border-radius: 6px;` → Rounds the corners (higher number = more rounded)
- `font-size: 1rem;` → 1x the root font size (16px)
- `font-weight: 600;` → Semi-bold
- `cursor: pointer;` → Shows a hand cursor when hovering (tells user "this is clickable")
- `transition: all 0.3s ease;` → Animate ALL property changes over 0.3s with an ease curve
- `border: 2px solid #4f46e5;` → 2px solid indigo border

---

```css
.btn-primary {
  background: #4f46e5;
  color: #fff;
}

.btn-primary:hover {
  background: #4338ca;
  border-color: #4338ca;
}
```
- `.btn-primary` → The filled button. Indigo background, white text.
- `:hover` → On mouse hover, darken the background slightly (`#4338ca` is slightly darker than `#4f46e5`)

---

```css
.btn-outline {
  background: transparent;
  color: #4f46e5;
}

.btn-outline:hover {
  background: #4f46e5;
  color: #fff;
}
```
- `.btn-outline` → Transparent background, indigo text (just the border shows)
- `:hover` → On hover, fill it with indigo and change text to white (inverse effect)

---

```css
/* ===== Hero ===== */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 100px 20px 60px;
  background: linear-gradient(135deg, #eef2ff 0%, #e0e7ff 50%, #c7d2fe 100%);
}
```
- `min-height: 100vh;` → At least full screen height
- `display: flex;` → Enable flexbox
- `align-items: center;` → Vertically center the content
- `justify-content: center;` → Horizontally center the content
- `text-align: center;` → Center all text inside
- `padding: 100px 20px 60px;`
  - **Three values:** top right/left bottom
  - 100px top (to push content below the fixed navbar)
  - 20px left & right
  - 60px bottom
- `background: linear-gradient(...)` → Beautiful gradient from light blue to medium blue
  - `135deg` → Angle of the gradient (diagonal, top-left to bottom-right)
  - `#eef2ff 0%` → Start with very light blue
  - `#e0e7ff 50%` → Middle is slightly darker
  - `#c7d2fe 100%` → End with medium blue

---

```css
.hero-content {
  max-width: 650px;
}
```
- Limits content width to 650px so text lines aren't too long (better readability)

---

```css
.greeting {
  font-size: 1.15rem;
  color: #4f46e5;
  font-weight: 600;
  margin-bottom: 8px;
}
```
- The "Hello, I'm" text — indigo color, slightly larger, semi-bold, 8px gap below

---

```css
.hero h1 {
  font-size: 3.5rem;
  font-weight: 800;
  color: #1e1b4b;
  margin-bottom: 10px;
}
```
- `.hero h1` → Only `<h1>` INSIDE `.hero` (not all h1s on the page)
- `3.5rem` → Very large (56px). This is the most prominent text.
- `#1e1b4b` → Very dark indigo (almost black, but with a blue tint)

---

```css
.hero h2 {
  font-size: 1.5rem;
  font-weight: 600;
  color: #6366f1;
  margin-bottom: 18px;
}
```
- Your title (e.g., "Full Stack Developer")
- `#6366f1` → A lighter indigo

---

```css
.tagline {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 32px;
}
```
- The description paragraph — gray, with 32px space below before the buttons

---

```css
.hero-buttons {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
}
```
- `display: flex;` → Buttons go in a row
- `gap: 16px;` → 16px space between buttons
- `justify-content: center;` → Center the buttons
- `flex-wrap: wrap;` → If the screen is too narrow, buttons wrap to the next line instead of overflowing

---
---

# DAY 6 — About Section HTML

## What you're building today:
An "About Me" section with a photo placeholder on the left, bio text on the right, and statistics below.

## Key Concepts:

### HTML Structure Strategy:
We need a two-column layout (image | text). The pattern is:
```
container → limits width, centers on page
  section-title → "About Me" heading
  grid-container → holds the two columns
    column 1 → image
    column 2 → text + stats
```

### What is `<span>`?
An **inline** element (doesn't break to a new line). Used to style a piece of text within a larger block.
- `<div>` = block container (takes full width)
- `<span>` = inline container (flows with text)

---

## The Code (add after closing `</section>` of hero):

```html
  <!-- About Section -->
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title">About Me</h2>
      <div class="about-grid">
        <div class="about-image">
          <div class="image-placeholder">Your Photo</div>
        </div>
        <div class="about-text">
          <p>
            I'm a passionate developer with experience in building web applications.
            I love turning ideas into reality using clean, efficient code.
          </p>
          <p>
            With a strong foundation in both front-end and back-end technologies,
            I create seamless user experiences that make a difference.
          </p>
          <div class="about-stats">
            <div class="stat">
              <span class="stat-number">3+</span>
              <span class="stat-label">Years Experience</span>
            </div>
            <div class="stat">
              <span class="stat-number">20+</span>
              <span class="stat-label">Projects</span>
            </div>
            <div class="stat">
              <span class="stat-number">15+</span>
              <span class="stat-label">Happy Clients</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
```

### Key elements:

- `<section id="about" class="about">` → The about section. `id="about"` links to navbar's "About" link.
- `<div class="container">` → A reusable wrapper that limits content width (we'll style it Day 7)
- `<h2 class="section-title">About Me</h2>` → Section heading (reused in every section)
- `<div class="about-grid">` → Will become a CSS grid with 2 columns
- `<div class="image-placeholder">Your Photo</div>` → Placeholder for your photo
- Two `<p>` paragraphs → Your bio text
- `<div class="about-stats">` → Container for the 3 statistics
- Each stat has two `<span>` elements:
  - `<span class="stat-number">3+</span>` → The big number
  - `<span class="stat-label">Years Experience</span>` → The label below it

---
---

# DAY 7 — Style About Section

## What you're doing today:
Creating a two-column grid layout, styling the image placeholder, text, and statistics.

## Key Concepts:

### What is CSS Grid?
CSS Grid is a 2D layout system (rows AND columns). Unlike Flexbox (mainly 1D — rows OR columns), Grid excels at creating layouts with both rows and columns.

```css
display: grid;
grid-template-columns: 1fr 1.5fr;
```
- `1fr 1.5fr` → Two columns. The first takes 1 fraction, the second takes 1.5 fractions.
- Think of the total as 2.5 parts: first column gets 1/2.5 (40%), second gets 1.5/2.5 (60%).

### What is `aspect-ratio`?
`aspect-ratio: 1;` means width = height. So the image placeholder is a perfect square. `aspect-ratio: 16/9` would be widescreen.

### What is a pseudo-element (`::after`) on titles?
We use it to create a colored underline below section titles — without adding extra HTML.

---

## The Code (add at the bottom of style.css):

```css
/* ===== Reusable ===== */
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 20px;
}
```
- `max-width: 1100px;` → Content won't be wider than 1100px
- `margin: 0 auto;` → 0 top/bottom, `auto` left/right → **centers the container**
  - **EXAM TIP:** `margin: 0 auto` is the classic way to horizontally center a block element
- `padding: 0 20px;` → Small side padding so content doesn't touch screen edges on mobile

---

```css
.section-title {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 50px;
  position: relative;
  color: #222;
}

.section-title::after {
  content: "";
  display: block;
  width: 60px;
  height: 4px;
  background: #4f46e5;
  margin: 12px auto 0;
  border-radius: 2px;
}
```
- The title is centered, 2rem size, dark color
- `::after` creates a small indigo bar below the title:
  - `display: block;` → Makes it take its own line (pseudo-elements are inline by default)
  - `width: 60px; height: 4px;` → Small horizontal bar
  - `margin: 12px auto 0;` → 12px below text, centered horizontally
  - This is REUSABLE — every section title gets this underline automatically

---

```css
/* ===== About ===== */
.about {
  padding: 100px 0;
  background: #fff;
}
```
- `padding: 100px 0;` → 100px top/bottom, 0 left/right → creates generous vertical spacing

---

```css
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 50px;
  align-items: center;
}
```
- `display: grid;` → Activates CSS Grid
- `grid-template-columns: 1fr 1.5fr;` → Two columns: image (smaller) and text (larger)
- `gap: 50px;` → 50px space between columns
- `align-items: center;` → Vertically center the image and text

---

```css
.image-placeholder {
  width: 100%;
  aspect-ratio: 1;
  background: linear-gradient(135deg, #c7d2fe, #a5b4fc);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  color: #4338ca;
  font-weight: 600;
}
```
- `aspect-ratio: 1;` → Perfect square
- Pretty gradient background
- Rounded corners
- Text centered inside (the "Your Photo" text)

---

```css
.about-text p {
  font-size: 1.05rem;
  color: #555;
  margin-bottom: 16px;
}

.about-stats {
  display: flex;
  gap: 40px;
  margin-top: 30px;
}

.stat {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2rem;
  font-weight: 800;
  color: #4f46e5;
}

.stat-label {
  font-size: 0.85rem;
  color: #777;
}
```
- `.about-text p` → Style paragraphs inside the about text area
- `.about-stats` → Flexbox row to place stats side by side
- `.stat-number` → `display: block` makes `<span>` take its own line (normally spans are inline). Big, bold, indigo number.
- `.stat-label` → Small, gray text below each number

---
---

# DAY 8 — Skills Section HTML

## What you're building today:
A grid of 6 skill cards, each with an icon, skill name, and a progress bar.

## Key Concepts:

### HTML Entities for Icons:
Since we're not using icon libraries, we use **HTML entities** — special codes that display as symbols:
- `&#9998;` → ✎ (pencil)
- `&#9881;` → ⚙ (gear)
- `&#9883;` → ⚛ (atom)
- `&#9879;` → ⚗ (alembic)
- `&#128202;` → 📊 (chart)
- `&#128451;` → 🗃 (file box)

### What is `&amp;`?
In HTML, `&` is a special character. To display an actual `&`, you write `&amp;`. So `HTML &amp; CSS` displays as "HTML & CSS".

### Inline Styles (`style="width: 90%"`)
Normally we put CSS in the stylesheet. But sometimes we need UNIQUE values per element. Each skill has a different progress %, so we set `width` directly in the HTML.

---

## The Code (add after closing `</section>` of about):

```html
  <!-- Skills Section -->
  <section id="skills" class="skills">
    <div class="container">
      <h2 class="section-title">My Skills</h2>
      <div class="skills-grid">
        <div class="skill-card">
          <div class="skill-icon">&#9998;</div>
          <h3>HTML &amp; CSS</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 90%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#9881;</div>
          <h3>JavaScript</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 85%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#9883;</div>
          <h3>React</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 80%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#9879;</div>
          <h3>Node.js</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 75%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#128202;</div>
          <h3>Python</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 70%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#128451;</div>
          <h3>Databases</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 75%;"></div></div>
        </div>
      </div>
    </div>
  </section>
```

### Structure of each skill card:
```html
<div class="skill-card">           <!-- The card container -->
  <div class="skill-icon">ICON</div>   <!-- The emoji/symbol -->
  <h3>Skill Name</h3>                  <!-- The skill name -->
  <div class="skill-bar">              <!-- The gray track -->
    <div class="skill-fill" style="width: 90%;"></div>  <!-- The colored fill -->
  </div>
</div>
```

The progress bar is two nested divs:
- Outer div (`.skill-bar`) → Full-width gray bar
- Inner div (`.skill-fill`) → Colored portion that shows the skill level

---
---

# DAY 9 — Style Skills Section

## What you're doing today:
Making the skill cards look beautiful with a 3-column grid, hover effects, and animated progress bars.

## Key Concepts:

### `repeat(3, 1fr)` in Grid
- `grid-template-columns: repeat(3, 1fr);` → Create 3 equal-width columns
- `repeat(3, 1fr)` is shorthand for `1fr 1fr 1fr`
- `1fr` = 1 fraction of available space

### `transform: translateY(-6px)`
- Moves an element UP by 6px (negative Y = up)
- Combined with `transition`, creates a "lift" effect on hover

### `overflow: hidden`
- Hides any content that goes outside the element's boundary
- Used on the skill bar so the rounded corners look clean

---

## The Code (add at the bottom of style.css):

```css
/* ===== Skills ===== */
.skills {
  padding: 100px 0;
  background: #f8fafc;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}
```
- Light gray background to alternate with the white About section
- 3-column grid with 24px gaps

---

```css
.skill-card {
  background: #fff;
  padding: 30px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s, box-shadow 0.3s;
}

.skill-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 8px 30px rgba(79, 70, 229, 0.12);
}
```
- White card with rounded corners and a subtle shadow
- `transition: transform 0.3s, box-shadow 0.3s;` → Animate BOTH transform and shadow
- On hover: card lifts up 6px and shadow becomes larger/more purple

---

```css
.skill-icon {
  font-size: 2.2rem;
  margin-bottom: 14px;
}

.skill-card h3 {
  font-size: 1.1rem;
  margin-bottom: 16px;
  color: #333;
}
```
- Large icon, spaced below, then the skill name

---

```css
.skill-bar {
  width: 100%;
  height: 8px;
  background: #e5e7eb;
  border-radius: 4px;
  overflow: hidden;
}

.skill-fill {
  height: 100%;
  background: linear-gradient(90deg, #4f46e5, #818cf8);
  border-radius: 4px;
  transition: width 1s ease;
}
```
- `.skill-bar` → The gray track (full width, 8px tall, light gray)
- `.skill-fill` → The colored fill (gradient from dark to light indigo)
- `transition: width 1s ease;` → If width changes, animate over 1 second

---
---

# DAY 10 — Projects Section HTML

## What you're building today:
A grid of 4 project cards, each with an image area, title, description, tech tags, and links.

## The Structure Pattern:
```
project-card
  project-image        → Colored placeholder
  project-info         → All the text content
    h3                 → Project title
    p                  → Description
    project-tags       → Technology badges
      tag, tag, tag
    project-links      → Demo + Source buttons
      btn, btn
```

---

## The Code (add after closing `</section>` of skills):

```html
  <!-- Projects Section -->
  <section id="projects" class="projects">
    <div class="container">
      <h2 class="section-title">My Projects</h2>
      <div class="projects-grid">
        <div class="project-card">
          <div class="project-image">Project 1</div>
          <div class="project-info">
            <h3>E-Commerce Website</h3>
            <p>A full-featured online store with cart, checkout, and payment integration.</p>
            <div class="project-tags">
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
              <span class="tag">JavaScript</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-image">Project 2</div>
          <div class="project-info">
            <h3>Task Manager App</h3>
            <p>A productivity app for organizing tasks with drag-and-drop functionality.</p>
            <div class="project-tags">
              <span class="tag">React</span>
              <span class="tag">Node.js</span>
              <span class="tag">MongoDB</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-image">Project 3</div>
          <div class="project-info">
            <h3>Weather Dashboard</h3>
            <p>Real-time weather data visualization with interactive maps and charts.</p>
            <div class="project-tags">
              <span class="tag">JavaScript</span>
              <span class="tag">API</span>
              <span class="tag">CSS</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-image">Project 4</div>
          <div class="project-info">
            <h3>Blog Platform</h3>
            <p>A content management system with rich text editing and user authentication.</p>
            <div class="project-tags">
              <span class="tag">Python</span>
              <span class="tag">Django</span>
              <span class="tag">PostgreSQL</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
```

### Key things to notice:
- `<span class="tag">HTML</span>` → `<span>` is inline, perfect for small badges in a row
- `class="btn btn-small"` → Two classes: base button + small size variant
- `class="btn btn-small btn-outline"` → Three classes: base + small + outline style
- All 4 cards follow the **exact same structure** — only the content changes

---
---

# DAY 11 — Style Projects Section

## What you're doing today:
2-column grid for project cards, image placeholders, card hover effects.

---

## The Code (add at the bottom of style.css):

```css
/* ===== Projects ===== */
.projects {
  padding: 100px 0;
  background: #fff;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
}
```
- White background
- 2-column grid (each card takes half the width)

---

```css
.project-card {
  border-radius: 14px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
  transition: transform 0.3s, box-shadow 0.3s;
  background: #fff;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 36px rgba(0, 0, 0, 0.1);
}
```
- `overflow: hidden;` → Important! The image div has no border-radius, but the card does. `overflow: hidden` clips the image to match the card's rounded corners.
- Hover: lifts up + stronger shadow (same pattern as skill cards)

---

```css
.project-image {
  height: 200px;
  background: linear-gradient(135deg, #c7d2fe, #a5b4fc);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.3rem;
  font-weight: 700;
  color: #4338ca;
}
```
- Fixed 200px height
- Gradient background (placeholder for a real project screenshot)
- Text centered with flexbox

---

```css
.project-info {
  padding: 24px;
}

.project-info h3 {
  font-size: 1.2rem;
  margin-bottom: 10px;
  color: #222;
}

.project-info p {
  font-size: 0.95rem;
  color: #666;
  margin-bottom: 14px;
}

.project-links {
  display: flex;
  gap: 10px;
}
```
- Content area with padding
- Title, description, and buttons spaced out
- `.project-links` → Flexbox to put buttons side by side

---
---

# DAY 12 — Contact Section HTML

## What you're building today:
A contact section with your info on the left and a message form on the right.

## Key Concepts:

### HTML Forms
A `<form>` element collects user input. Key form elements:
- `<input type="text">` → Single-line text input
- `<input type="email">` → Email input (browser validates it has an @)
- `<textarea>` → Multi-line text input
- `<button type="submit">` → Submits the form

### The `required` Attribute
Adding `required` to an input means the form can't be submitted unless that field is filled in. The browser shows a warning automatically.

### The `placeholder` Attribute
Shows gray hint text inside the input that disappears when typing.

---

## The Code (add after closing `</section>` of projects):

```html
  <!-- Contact Section -->
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Get In Touch</h2>
      <div class="contact-grid">
        <div class="contact-info">
          <h3>Let's work together</h3>
          <p>Feel free to reach out for collaborations or just a friendly hello!</p>
          <div class="contact-details">
            <div class="contact-item">
              <span class="contact-icon">&#9993;</span>
              <span>your.email@example.com</span>
            </div>
            <div class="contact-item">
              <span class="contact-icon">&#9742;</span>
              <span>+1 234 567 890</span>
            </div>
            <div class="contact-item">
              <span class="contact-icon">&#128205;</span>
              <span>Your City, Country</span>
            </div>
          </div>
          <div class="social-links">
            <a href="#" class="social-link">GitHub</a>
            <a href="#" class="social-link">LinkedIn</a>
            <a href="#" class="social-link">Twitter</a>
          </div>
        </div>
        <form class="contact-form" action="#" method="POST">
          <div class="form-group">
            <input type="text" name="name" placeholder="Your Name" required>
          </div>
          <div class="form-group">
            <input type="email" name="email" placeholder="Your Email" required>
          </div>
          <div class="form-group">
            <input type="text" name="subject" placeholder="Subject">
          </div>
          <div class="form-group">
            <textarea name="message" rows="5" placeholder="Your Message" required></textarea>
          </div>
          <button type="submit" class="btn btn-primary">Send Message</button>
        </form>
      </div>
    </div>
  </section>
```

### Line-by-line highlights:

**Contact Info (left side):**
- `&#9993;` → ✉ (envelope icon)
- `&#9742;` → ☎ (phone icon)
- `&#128205;` → 📍 (pin/location icon)
- Each contact item is a flex row with icon + text

**Social Links:**
- Three links to your social profiles (update `href="#"` with real URLs later)

**The Form (right side):**
- `<form action="#" method="POST">` → Where the form data goes when submitted. `#` is a placeholder. `POST` means the data is sent in the request body (not visible in the URL).
- `<input type="text" name="name" placeholder="Your Name" required>`
  - `type="text"` → Regular text input
  - `name="name"` → The field's name (used when sending data)
  - `placeholder="Your Name"` → Gray hint text
  - `required` → Must be filled in
- `<input type="email">` → Special input that validates email format
- `<textarea rows="5">` → Multi-line input, 5 rows tall
- `<button type="submit">` → Submitting the form

---
---

# DAY 13 — Style Contact Section

## What you're doing today:
Two-column grid for contact, styled form inputs with focus effects.

## Key Concept:

### `:focus` pseudo-class
When a user clicks/tabs into an input field, it's "focused." We use `:focus` to change the border color, giving visual feedback.

### `outline: none`
Browsers add a default outline around focused elements. We remove it and use our own border effect instead.

---

## The Code (add at the bottom of style.css):

```css
/* ===== Contact ===== */
.contact {
  padding: 100px 0;
  background: #f8fafc;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
}
```
- Light gray background
- Two equal columns

---

```css
.contact-info h3 {
  font-size: 1.5rem;
  margin-bottom: 14px;
  color: #222;
}

.contact-info p {
  color: #666;
  margin-bottom: 28px;
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 18px;
  margin-bottom: 30px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 12px;
  color: #555;
}

.contact-icon {
  font-size: 1.3rem;
}
```
- `flex-direction: column;` → Stack items vertically (default is row/horizontal)
- Each contact item is a horizontal flex row (icon next to text)

---

```css
/* Form */
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 14px 18px;
  border: 2px solid #e5e7eb;
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
  background: #fff;
  transition: border-color 0.3s;
  outline: none;
}

.contact-form input:focus,
.contact-form textarea:focus {
  border-color: #4f46e5;
}

.contact-form textarea {
  resize: vertical;
}
```

- `.contact-form` → Flex column = inputs stack vertically with 16px gap
- `width: 100%;` → Inputs take full width of the form
- `border: 2px solid #e5e7eb;` → Light gray border
- `font-family: inherit;` → Inputs use the same font as the rest of the page (by default they don't)
- `transition: border-color 0.3s;` → Smooth color change on focus
- `outline: none;` → Remove default browser outline
- `:focus` → When clicked/selected, border turns indigo
- `resize: vertical;` → Textarea can only be resized vertically (not horizontally)

---
---

# DAY 14 — Footer

## What you're building today:
A simple footer with a copyright notice.

---

## HTML (add after closing `</section>` of contact, before `</body>`):

```html
  <!-- Footer -->
  <footer class="footer">
    <p>&copy; 2026 Your Name. All rights reserved.</p>
  </footer>
```

- `<footer>` → Semantic element for the page footer
- `&copy;` → HTML entity for the © (copyright) symbol
- Replace "Your Name" with your name!

---

## CSS (add at the bottom of style.css):

```css
/* ===== Footer ===== */
.footer {
  text-align: center;
  padding: 30px;
  background: #1e1b4b;
  color: #a5b4fc;
  font-size: 0.9rem;
}
```
- Dark indigo background
- Light blue/purple text
- Simple centered text

---
---

# DAY 15 — Tag Badges, Social Links & Small Button

## What you're doing today:
Adding the styles that were missing for project tags, social link buttons, and the small button variant used in project cards.

---

## CSS (add at the bottom of style.css):

```css
/* ===== Tags ===== */
.project-tags {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  margin-bottom: 18px;
}

.tag {
  padding: 4px 12px;
  background: #eef2ff;
  color: #4f46e5;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
}
```
- Tags/badges in a flex row that wraps
- `border-radius: 20px;` → Pill-shaped (very rounded corners)
- Light indigo background with indigo text

---

```css
/* ===== Small Button ===== */
.btn-small {
  padding: 8px 18px;
  font-size: 0.85rem;
}
```
- A smaller version of `.btn`. Since `.btn-small` comes after `.btn` AND is more specific when combined, it overrides just the padding and font-size.
- **CSS Cascade:** When two rules conflict, the LAST one wins (if same specificity). This is why we put `.btn-small` after `.btn`.

---

```css
/* ===== Social Links ===== */
.social-links {
  display: flex;
  gap: 14px;
}

.social-link {
  padding: 8px 18px;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-weight: 600;
  font-size: 0.9rem;
  color: #555;
  transition: all 0.3s;
}

.social-link:hover {
  border-color: #4f46e5;
  color: #4f46e5;
}
```
- Social links are bordered buttons in a row
- On hover: border and text turn indigo

---
---

# DAY 16 — Tablet Responsive Design

## What you're doing today:
Making the website look good on tablet screens (768px and smaller).

## KEY CONCEPT — Media Queries:

```css
@media (max-width: 768px) {
  /* These styles ONLY apply when screen is 768px or narrower */
}
```

**How it works:**
1. On a desktop (e.g., 1200px wide) → These rules are IGNORED
2. On a tablet (e.g., 768px wide) → These rules ACTIVATE
3. They OVERRIDE the desktop styles

**Common breakpoints:**
- 768px → Tablet
- 480px → Mobile phone

**EXAM TIP:** `@media` queries don't replace your existing CSS — they add overrides. The original CSS still works on larger screens.

---

## The Code (add at the bottom of style.css):

```css
/* ===== Responsive - Tablet ===== */
@media (max-width: 768px) {
  .nav-links {
    gap: 18px;
    font-size: 0.9rem;
  }
```
- Nav links: smaller gap and font so they fit on narrower screens

---

```css
  .navbar {
    padding: 14px 20px;
  }
```
- Less padding on the navbar

---

```css
  .hero h1 {
    font-size: 2.4rem;
  }

  .hero h2 {
    font-size: 1.2rem;
  }
```
- Reduce heading sizes so they don't overflow

---

```css
  .about-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .image-placeholder {
    max-width: 280px;
    margin: 0 auto;
  }

  .about-stats {
    justify-content: center;
  }
```
- About grid: goes from 2 columns → 1 column (image stacks above text)
- `grid-template-columns: 1fr;` → Single column
- Image limited to 280px and centered
- Stats centered

---

```css
  .skills-grid {
    grid-template-columns: repeat(2, 1fr);
  }
```
- Skills: 3 columns → 2 columns

---

```css
  .projects-grid {
    grid-template-columns: 1fr;
  }
```
- Projects: 2 columns → 1 column (cards stack vertically)

---

```css
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
```
- Contact: 2 columns → 1 column
- **Note the closing `}` → This closes the entire `@media` block**

---
---

# DAY 17 — Mobile Responsive & Final Polish

## What you're doing today:
Making the website look good on phone screens (480px and smaller).

---

## The Code (add at the bottom of style.css):

```css
/* ===== Responsive - Mobile ===== */
@media (max-width: 480px) {
  .nav-links {
    display: none;
  }
```
- **Hides the navigation links entirely** on small phones (not enough space). Only the logo remains visible.
- In a real project, you'd add a hamburger menu button, but that requires JavaScript.

---

```css
  .hero h1 {
    font-size: 2rem;
  }
```
- Even smaller heading on phones

---

```css
  .skills-grid {
    grid-template-columns: 1fr;
  }
```
- Skills: 2 columns (from tablet) → 1 column on mobile

---

```css
  .about-stats {
    flex-direction: column;
    gap: 20px;
  }
}
```
- Stats go from a row → a column (stacked vertically)
- **Closing `}` ends the `@media` block**

---
---

# COMPLETE FILES — For Reference

## Final index.html:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portfolio</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- Navigation -->
  <nav class="navbar">
    <a href="#" class="logo">Portfolio</a>
    <ul class="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- Hero Section -->
  <section id="home" class="hero">
    <div class="hero-content">
      <p class="greeting">Hello, I'm</p>
      <h1>Your Name</h1>
      <h2>Full Stack Developer</h2>
      <p class="tagline">I build modern, responsive websites and web applications.</p>
      <div class="hero-buttons">
        <a href="#projects" class="btn btn-primary">View My Work</a>
        <a href="#contact" class="btn btn-outline">Contact Me</a>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title">About Me</h2>
      <div class="about-grid">
        <div class="about-image">
          <div class="image-placeholder">Your Photo</div>
        </div>
        <div class="about-text">
          <p>
            I'm a passionate developer with experience in building web applications.
            I love turning ideas into reality using clean, efficient code.
          </p>
          <p>
            With a strong foundation in both front-end and back-end technologies,
            I create seamless user experiences that make a difference.
          </p>
          <div class="about-stats">
            <div class="stat">
              <span class="stat-number">3+</span>
              <span class="stat-label">Years Experience</span>
            </div>
            <div class="stat">
              <span class="stat-number">20+</span>
              <span class="stat-label">Projects</span>
            </div>
            <div class="stat">
              <span class="stat-number">15+</span>
              <span class="stat-label">Happy Clients</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills Section -->
  <section id="skills" class="skills">
    <div class="container">
      <h2 class="section-title">My Skills</h2>
      <div class="skills-grid">
        <div class="skill-card">
          <div class="skill-icon">&#9998;</div>
          <h3>HTML &amp; CSS</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 90%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#9881;</div>
          <h3>JavaScript</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 85%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#9883;</div>
          <h3>React</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 80%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#9879;</div>
          <h3>Node.js</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 75%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#128202;</div>
          <h3>Python</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 70%;"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">&#128451;</div>
          <h3>Databases</h3>
          <div class="skill-bar"><div class="skill-fill" style="width: 75%;"></div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects Section -->
  <section id="projects" class="projects">
    <div class="container">
      <h2 class="section-title">My Projects</h2>
      <div class="projects-grid">
        <div class="project-card">
          <div class="project-image">Project 1</div>
          <div class="project-info">
            <h3>E-Commerce Website</h3>
            <p>A full-featured online store with cart, checkout, and payment integration.</p>
            <div class="project-tags">
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
              <span class="tag">JavaScript</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-image">Project 2</div>
          <div class="project-info">
            <h3>Task Manager App</h3>
            <p>A productivity app for organizing tasks with drag-and-drop functionality.</p>
            <div class="project-tags">
              <span class="tag">React</span>
              <span class="tag">Node.js</span>
              <span class="tag">MongoDB</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-image">Project 3</div>
          <div class="project-info">
            <h3>Weather Dashboard</h3>
            <p>Real-time weather data visualization with interactive maps and charts.</p>
            <div class="project-tags">
              <span class="tag">JavaScript</span>
              <span class="tag">API</span>
              <span class="tag">CSS</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-image">Project 4</div>
          <div class="project-info">
            <h3>Blog Platform</h3>
            <p>A content management system with rich text editing and user authentication.</p>
            <div class="project-tags">
              <span class="tag">Python</span>
              <span class="tag">Django</span>
              <span class="tag">PostgreSQL</span>
            </div>
            <div class="project-links">
              <a href="#" class="btn btn-small">Live Demo</a>
              <a href="#" class="btn btn-small btn-outline">Source Code</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Get In Touch</h2>
      <div class="contact-grid">
        <div class="contact-info">
          <h3>Let's work together</h3>
          <p>Feel free to reach out for collaborations or just a friendly hello!</p>
          <div class="contact-details">
            <div class="contact-item">
              <span class="contact-icon">&#9993;</span>
              <span>your.email@example.com</span>
            </div>
            <div class="contact-item">
              <span class="contact-icon">&#9742;</span>
              <span>+1 234 567 890</span>
            </div>
            <div class="contact-item">
              <span class="contact-icon">&#128205;</span>
              <span>Your City, Country</span>
            </div>
          </div>
          <div class="social-links">
            <a href="#" class="social-link">GitHub</a>
            <a href="#" class="social-link">LinkedIn</a>
            <a href="#" class="social-link">Twitter</a>
          </div>
        </div>
        <form class="contact-form" action="#" method="POST">
          <div class="form-group">
            <input type="text" name="name" placeholder="Your Name" required>
          </div>
          <div class="form-group">
            <input type="email" name="email" placeholder="Your Email" required>
          </div>
          <div class="form-group">
            <input type="text" name="subject" placeholder="Subject">
          </div>
          <div class="form-group">
            <textarea name="message" rows="5" placeholder="Your Message" required></textarea>
          </div>
          <button type="submit" class="btn btn-primary">Send Message</button>
        </form>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="footer">
    <p>&copy; 2026 Your Name. All rights reserved.</p>
  </footer>

</body>
</html>
```

---

## Final style.css:
```css
/* ===== Reset & Base ===== */
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #333;
  background: #fafafa;
}

a {
  text-decoration: none;
  color: inherit;
}

ul {
  list-style: none;
}

img {
  max-width: 100%;
}

/* ===== Navbar ===== */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 18px 40px;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.06);
  z-index: 1000;
}

.logo {
  font-size: 1.5rem;
  font-weight: 800;
  color: #4f46e5;
}

.nav-links {
  display: flex;
  gap: 32px;
}

.nav-links a {
  font-weight: 500;
  color: #555;
  transition: color 0.3s;
  position: relative;
}

.nav-links a::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: #4f46e5;
  transition: width 0.3s;
}

.nav-links a:hover {
  color: #4f46e5;
}

.nav-links a:hover::after {
  width: 100%;
}

/* ===== Buttons ===== */
.btn {
  display: inline-block;
  padding: 12px 28px;
  border-radius: 6px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  border: 2px solid #4f46e5;
}

.btn-primary {
  background: #4f46e5;
  color: #fff;
}

.btn-primary:hover {
  background: #4338ca;
  border-color: #4338ca;
}

.btn-outline {
  background: transparent;
  color: #4f46e5;
}

.btn-outline:hover {
  background: #4f46e5;
  color: #fff;
}

/* ===== Hero ===== */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 100px 20px 60px;
  background: linear-gradient(135deg, #eef2ff 0%, #e0e7ff 50%, #c7d2fe 100%);
}

.hero-content {
  max-width: 650px;
}

.greeting {
  font-size: 1.15rem;
  color: #4f46e5;
  font-weight: 600;
  margin-bottom: 8px;
}

.hero h1 {
  font-size: 3.5rem;
  font-weight: 800;
  color: #1e1b4b;
  margin-bottom: 10px;
}

.hero h2 {
  font-size: 1.5rem;
  font-weight: 600;
  color: #6366f1;
  margin-bottom: 18px;
}

.tagline {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 32px;
}

.hero-buttons {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
}

/* ===== Reusable ===== */
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 20px;
}

.section-title {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 50px;
  position: relative;
  color: #222;
}

.section-title::after {
  content: "";
  display: block;
  width: 60px;
  height: 4px;
  background: #4f46e5;
  margin: 12px auto 0;
  border-radius: 2px;
}

/* ===== About ===== */
.about {
  padding: 100px 0;
  background: #fff;
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 50px;
  align-items: center;
}

.image-placeholder {
  width: 100%;
  aspect-ratio: 1;
  background: linear-gradient(135deg, #c7d2fe, #a5b4fc);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  color: #4338ca;
  font-weight: 600;
}

.about-text p {
  font-size: 1.05rem;
  color: #555;
  margin-bottom: 16px;
}

.about-stats {
  display: flex;
  gap: 40px;
  margin-top: 30px;
}

.stat {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2rem;
  font-weight: 800;
  color: #4f46e5;
}

.stat-label {
  font-size: 0.85rem;
  color: #777;
}

/* ===== Skills ===== */
.skills {
  padding: 100px 0;
  background: #f8fafc;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.skill-card {
  background: #fff;
  padding: 30px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s, box-shadow 0.3s;
}

.skill-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 8px 30px rgba(79, 70, 229, 0.12);
}

.skill-icon {
  font-size: 2.2rem;
  margin-bottom: 14px;
}

.skill-card h3 {
  font-size: 1.1rem;
  margin-bottom: 16px;
  color: #333;
}

.skill-bar {
  width: 100%;
  height: 8px;
  background: #e5e7eb;
  border-radius: 4px;
  overflow: hidden;
}

.skill-fill {
  height: 100%;
  background: linear-gradient(90deg, #4f46e5, #818cf8);
  border-radius: 4px;
  transition: width 1s ease;
}

/* ===== Projects ===== */
.projects {
  padding: 100px 0;
  background: #fff;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
}

.project-card {
  border-radius: 14px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
  transition: transform 0.3s, box-shadow 0.3s;
  background: #fff;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 36px rgba(0, 0, 0, 0.1);
}

.project-image {
  height: 200px;
  background: linear-gradient(135deg, #c7d2fe, #a5b4fc);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.3rem;
  font-weight: 700;
  color: #4338ca;
}

.project-info {
  padding: 24px;
}

.project-info h3 {
  font-size: 1.2rem;
  margin-bottom: 10px;
  color: #222;
}

.project-info p {
  font-size: 0.95rem;
  color: #666;
  margin-bottom: 14px;
}

.project-links {
  display: flex;
  gap: 10px;
}

/* ===== Contact ===== */
.contact {
  padding: 100px 0;
  background: #f8fafc;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
}

.contact-info h3 {
  font-size: 1.5rem;
  margin-bottom: 14px;
  color: #222;
}

.contact-info p {
  color: #666;
  margin-bottom: 28px;
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 18px;
  margin-bottom: 30px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 12px;
  color: #555;
}

.contact-icon {
  font-size: 1.3rem;
}

/* Form */
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 14px 18px;
  border: 2px solid #e5e7eb;
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
  background: #fff;
  transition: border-color 0.3s;
  outline: none;
}

.contact-form input:focus,
.contact-form textarea:focus {
  border-color: #4f46e5;
}

.contact-form textarea {
  resize: vertical;
}

/* ===== Footer ===== */
.footer {
  text-align: center;
  padding: 30px;
  background: #1e1b4b;
  color: #a5b4fc;
  font-size: 0.9rem;
}

/* ===== Tags ===== */
.project-tags {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  margin-bottom: 18px;
}

.tag {
  padding: 4px 12px;
  background: #eef2ff;
  color: #4f46e5;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
}

/* ===== Small Button ===== */
.btn-small {
  padding: 8px 18px;
  font-size: 0.85rem;
}

/* ===== Social Links ===== */
.social-links {
  display: flex;
  gap: 14px;
}

.social-link {
  padding: 8px 18px;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-weight: 600;
  font-size: 0.9rem;
  color: #555;
  transition: all 0.3s;
}

.social-link:hover {
  border-color: #4f46e5;
  color: #4f46e5;
}

/* ===== Responsive - Tablet ===== */
@media (max-width: 768px) {
  .nav-links {
    gap: 18px;
    font-size: 0.9rem;
  }

  .navbar {
    padding: 14px 20px;
  }

  .hero h1 {
    font-size: 2.4rem;
  }

  .hero h2 {
    font-size: 1.2rem;
  }

  .about-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .image-placeholder {
    max-width: 280px;
    margin: 0 auto;
  }

  .about-stats {
    justify-content: center;
  }

  .skills-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }

  .contact-grid {
    grid-template-columns: 1fr;
  }
}

/* ===== Responsive - Mobile ===== */
@media (max-width: 480px) {
  .nav-links {
    display: none;
  }

  .hero h1 {
    font-size: 2rem;
  }

  .skills-grid {
    grid-template-columns: 1fr;
  }

  .about-stats {
    flex-direction: column;
    gap: 20px;
  }
}
```

---
---

# EXAM CHEAT SHEET — Key Concepts Summary

## HTML Essentials:
| Concept | Example | What it does |
|---------|---------|--------------|
| DOCTYPE | `<!DOCTYPE html>` | Declares HTML5 |
| Charset | `<meta charset="UTF-8">` | Supports all characters |
| Viewport | `<meta name="viewport" ...>` | Makes site responsive |
| Semantic elements | `<nav>`, `<section>`, `<footer>` | Give meaning to structure |
| id vs class | `id="home"` vs `class="hero"` | id = unique, class = reusable |
| Anchor links | `<a href="#about">` | Scrolls to element with that id |
| Entities | `&amp;` `&copy;` `&#9993;` | Special characters |
| Form elements | `<input>`, `<textarea>`, `<button>` | Collect user input |
| required | `<input required>` | Field must be filled |

## CSS Essentials:
| Concept | Example | What it does |
|---------|---------|--------------|
| Universal selector | `*` | Selects everything |
| Class selector | `.navbar` | Selects class="navbar" |
| Descendant selector | `.hero h1` | h1 inside .hero |
| Pseudo-class | `:hover`, `:focus` | State-based styling |
| Pseudo-element | `::before`, `::after` | Create virtual elements |
| box-sizing: border-box | `* { box-sizing: border-box; }` | Padding included in width |
| Flexbox | `display: flex;` | 1D layout (row or column) |
| CSS Grid | `display: grid;` | 2D layout (rows and columns) |
| position: fixed | `.navbar { position: fixed; }` | Stays on screen when scrolling |
| z-index | `z-index: 1000;` | Controls stacking order |
| transition | `transition: all 0.3s;` | Smooth animation |
| transform | `transform: translateY(-6px);` | Move element |
| linear-gradient | `background: linear-gradient(...)` | Color blend |
| @media | `@media (max-width: 768px)` | Responsive breakpoint |
| margin: 0 auto | `margin: 0 auto;` | Center a block element |
| rem | `font-size: 1.5rem;` | Relative to root font (16px) |
| vh | `min-height: 100vh;` | Relative to viewport height |

## Layout Patterns Used:
1. **Center horizontally:** `margin: 0 auto;` (for block elements)
2. **Center with Flexbox:** `display: flex; justify-content: center; align-items: center;`
3. **Two-column layout:** `display: grid; grid-template-columns: 1fr 1fr;`
4. **Items in a row:** `display: flex; gap: 16px;`
5. **Stack vertically:** `display: flex; flex-direction: column;`
6. **Responsive columns → single column:** Media query changing `grid-template-columns: 1fr;`
