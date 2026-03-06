# Portfolio - 17 Day Push Guide

## First Time Setup (Do this once before Day 1)

```bash
cd portfolio
git init
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/portfolio.git
```

---

## DAY 1 — Project Setup
**Commit message:** `Initial project setup with HTML boilerplate and CSS reset`

Replace your **index.html** with:
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

Replace your **style.css** with:
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

**Push:**
```bash
git add .
git commit -m "Project setup with HTML and CSS reset"
git push -u origin main
```

---

## DAY 2 — Navigation Bar HTML
**Commit message:** `Add navigation bar HTML structure`

In **index.html**, add the following inside `<body>`:
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

No changes to style.css today.

**Push:**
```bash
git add .
git commit -m "Add navigation bar HTML structure"
git push
```

---

## DAY 3 — Style Navigation Bar
**Commit message:** `Style navigation bar with fixed position and hover effects`

No changes to index.html today.

In **style.css**, add at the bottom:
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
```

**Push:**
```bash
git add .
git commit -m "Style navigation bar with fixed position and hover effects"
git push
```

---

## DAY 4 — Hero Section HTML
**Commit message:** `Add hero section with greeting and call-to-action buttons`

In **index.html**, add after the closing `</nav>` tag:
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

No changes to style.css today.

**Push:**
```bash
git add .
git commit -m "Add hero section with greeting and call-to-action buttons"
git push
```

---

## DAY 5 — Style Hero Section & Buttons
**Commit message:** `Style hero section and add button components`

No changes to index.html today.

In **style.css**, add at the bottom:
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
```

**Push:**
```bash
git add .
git commit -m "Style hero section and add button components"
git push
```

---

## DAY 6 — About Section HTML
**Commit message:** `Add about section with bio and statistics`

In **index.html**, add after the closing `</section>` of the hero:
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

No changes to style.css today.

**Push:**
```bash
git add .
git commit -m "Add about section with bio and statistics"
git push
```

---

## DAY 7 — Style About Section
**Commit message:** `Style about section with grid layout and reusable utilities`

No changes to index.html today.

In **style.css**, add at the bottom:
```css
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
```

**Push:**
```bash
git add .
git commit -m "Style about section with grid layout and reusable utilities"
git push
```

---

## DAY 8 — Skills Section HTML
**Commit message:** `Add skills section with six skill cards`

In **index.html**, add after the closing `</section>` of about:
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

No changes to style.css today.

**Push:**
```bash
git add .
git commit -m "Add skills section with six skill cards"
git push
```

---

## DAY 9 — Style Skills Section
**Commit message:** `Style skills cards with hover effects and progress bars`

No changes to index.html today.

In **style.css**, add at the bottom:
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
```

**Push:**
```bash
git add .
git commit -m "Style skills cards with hover effects and progress bars"
git push
```

---

## DAY 10 — Projects Section HTML
**Commit message:** `Add projects section with four project cards`

In **index.html**, add after the closing `</section>` of skills:
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

No changes to style.css today.

**Push:**
```bash
git add .
git commit -m "Add projects section with four project cards"
git push
```

---

## DAY 11 — Style Projects Section
**Commit message:** `Style projects grid with card hover animations`

No changes to index.html today.

In **style.css**, add at the bottom:
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
```

**Push:**
```bash
git add .
git commit -m "Style projects grid with card hover animations"
git push
```

---

## DAY 12 — Contact Section HTML
**Commit message:** `Add contact section with info and message form`

In **index.html**, add after the closing `</section>` of projects:
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

No changes to style.css today.

**Push:**
```bash
git add .
git commit -m "Add contact section with info and message form"
git push
```

---

## DAY 13 — Style Contact Section
**Commit message:** `Style contact section with grid layout and form inputs`

No changes to index.html today.

In **style.css**, add at the bottom:
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
```

**Push:**
```bash
git add .
git commit -m "Style contact section with grid layout and form inputs"
git push
```

---

## DAY 14 — Footer
**Commit message:** `Add footer with copyright notice`

In **index.html**, add after the closing `</section>` of contact (before `</body>`):
```html
  <!-- Footer -->
  <footer class="footer">
    <p>&copy; 2026 Your Name. All rights reserved.</p>
  </footer>
```

In **style.css**, add at the bottom:
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

**Push:**
```bash
git add .
git commit -m "Add footer with copyright notice"
git push
```

---

## DAY 15 — Tag Badges & Social Link Styles
**Commit message:** `Add tag badges, social links, and small button variant`

No changes to index.html today.

In **style.css**, add at the bottom:
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
```

**Push:**
```bash
git add .
git commit -m "Add tag badges, social links, and small button variant"
git push
```

---

## DAY 16 — Tablet Responsive Design
**Commit message:** `Add responsive design for tablet screens`

No changes to index.html today.

In **style.css**, add at the bottom:
```css
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
```

**Push:**
```bash
git add .
git commit -m "Add responsive design for tablet screens"
git push
```

---

## DAY 17 — Mobile Responsive & Final Polish
**Commit message:** `Add mobile responsive breakpoint and final polish`

No changes to index.html today.

In **style.css**, add at the bottom:
```css
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

**Push:**
```bash
git add .
git commit -m "Add mobile responsive breakpoint and final polish"
git push
```

---

## Summary Table

| Day | What You Add | Commit Message |
|-----|-------------|----------------|
| 1 | HTML boilerplate + CSS reset | `Initial project setup with HTML boilerplate and CSS reset` |
| 2 | Navbar HTML | `Add navigation bar HTML structure` |
| 3 | Navbar CSS | `Style navigation bar with fixed position and hover effects` |
| 4 | Hero HTML | `Add hero section with greeting and call-to-action buttons` |
| 5 | Hero CSS + Buttons | `Style hero section and add button components` |
| 6 | About HTML | `Add about section with bio and statistics` |
| 7 | About CSS + Utilities | `Style about section with grid layout and reusable utilities` |
| 8 | Skills HTML | `Add skills section with six skill cards` |
| 9 | Skills CSS | `Style skills cards with hover effects and progress bars` |
| 10 | Projects HTML | `Add projects section with four project cards` |
| 11 | Projects CSS | `Style projects grid with card hover animations` |
| 12 | Contact HTML | `Add contact section with info and message form` |
| 13 | Contact CSS | `Style contact section with grid layout and form inputs` |
| 14 | Footer HTML + CSS | `Add footer with copyright notice` |
| 15 | Tag + Social styles | `Add tag badges, social links, and small button variant` |
| 16 | Tablet responsive | `Add responsive design for tablet screens` |
| 17 | Mobile responsive | `Add mobile responsive breakpoint and final polish` |
