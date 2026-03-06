# 🗂️ Achraf El Makaoui — Portfolio Website

A personal developer portfolio built with **pure HTML & CSS** (no frameworks), showcasing full-stack and data science projects with a clean dark-themed design and dedicated project detail pages.

---

## 📁 Project Structure

```
portfolioWeb/
│
├── Portfolio.html          # Main portfolio page (single-page layout)
├── Portfolio.css           # Styles for the main portfolio page
│
├── Projects.css            # Shared styles for all project detail pages
│
├── H2chainSolutions.html   # Project detail page — H2chain Solutions
├── SAMQE-Learning.html     # Project detail page — SAMQ E-Learning
├── SneakersDashboard.html  # Project detail page — Sneakers Dashboard
├── SneakersStore.html      # Project detail page — Sneakers Store
├── TaxiDriverLoyalty.html  # Project detail page — Taxi Driver Loyalty
│
└── images/                 # All image assets (logos, screenshots)
```

---

## 🧠 Main Concepts

### Architecture — Multi-Page Application (MPA)
The portfolio follows a classic **multi-page** architecture. The main page (`Portfolio.html`) serves as the hub. Each project card links to its own dedicated HTML file (e.g., `H2chainSolutions.html`). Navigation between pages is handled with standard `<a href="...">` anchor tags — no JavaScript routing needed.

### Single-Page Scroll Navigation (Portfolio.html)
The main page is divided into **sections**, each with a unique `id`:

| Section ID  | Content                        |
|-------------|--------------------------------|
| `#Home`     | Hero / intro section           |
| `#AboutMe`  | About me bento-grid layout     |
| `#Career`   | Work experience / career path  |
| `#Skills`   | Tech skills display            |
| `#Projects` | Project cards grid             |
| `#Contact`  | Contact form                   |

The `<nav>` bar contains anchor links (`<a href="#SectionID">`) that scroll smoothly to each section using `scroll-behavior: smooth` set in the CSS on `html {}`.

---

## 📄 Project Detail Pages

All five project pages (`H2chainSolutions.html`, `SAMQE-Learning.html`, etc.) share an **identical HTML structure** and are all styled by `Projects.css`. This ensures visual consistency and makes adding new projects straightforward — just duplicate the template and fill in the content.

### Structure of Each Project Page

```
.ProjectInfo
  └── .projectInfoContainer
        ├── .ProjectInfo-Header
        │     ├── .Header-Content     → Logo, project title, description
        │     └── .Header-Divider     → Date, divider line, author avatar
        │
        ├── .ProjectInfo-Details
        │     ├── .ProjectInfo-images
        │     │     ├── .ProjectInfo-MainImage       → Project screenshot
        │     │     └── .ProductDetails-SecondaryImages → Project screnshot 
        │     │
        │     └── .projectInfo-Text 
        │           ├── 🤨 What is this?
        │           ├── ❓ Why
        │           ├── 🔨 Tech Stack
        │           ├── 🚀 Key Features
        │           ├── 🎯 My Role
        │           ├── 📊 Challenges & Solutions
        │           └── 📎 Live Demo / GitHub
        │
        └── .projectInfo-Footer
              ├── ← Go back (links back to Portfolio.html)
              └── Social icons (GitHub, LinkedIn)
```

---

## 🎨 Styling Concepts

### CSS File Separation
There are **two CSS files** with clear separation of concerns:

- **`Portfolio.css`** — styles everything on the main portfolio page: navbar, hero section, about grid, career timeline, skills, project cards, contact form, and footer.
- **`Projects.css`** — styles the shared layout of all project detail pages. One file, five pages — any global change applies everywhere instantly.

### Root Font Sizing Trick
```css
html {
    font-size: 62.5%;
}
```
Setting the root to `62.5%` makes `1rem = 10px`, which allows all sizes to be written in intuitive rem values (e.g., `font-size: 1.5rem` = 15px, `font-size: 3rem` = 30px). This is a widely-used scaling technique.

### Color Palette (Dark Theme)
| Role             | Color      |
|------------------|------------|
| Background       | `#111111`  |
| Primary text     | `#f5f5f5`  |
| Secondary text   | `#a8a8a8`  |
| Accent / links   | `#60A1FB`  |
| Tech stack tags  | `#dedede`  |

### Tech Stack Grid
The tech stack list in each project detail page uses CSS Grid to display badges in a clean 3-column layout:
```css
.projectinfo-TechStack ul {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
}
```
Each `<li>` badge has a hover effect that turns it accent blue (`#60A1FB`).

### Image Gallery
Each project page features a main image with a strip of 5 thumbnails below. The thumbnails use `filter: brightness(60%)` to appear dimmed by default. An `.active` class removes the filter on the selected image — this is meant to be toggled with a small JavaScript click handler.

### Responsive Design
Both CSS files use `@media` queries to adapt layouts:
- At `max-width: 1000px` — padding is reduced for tablet viewports.
- At `max-width: 768px` — font sizes scale down for mobile readability.

The navbar collapses into a hamburger menu on small screens, revealing the `mobileNav` overlay.

---

## 🔗 Navigation Flow

```
Portfolio.html
    │
    ├──→ H2chainSolutions.html   ──→ back to Portfolio.html
    ├──→ SAMQE-Learning.html     ──→ back to Portfolio.html
    ├──→ SneakersDashboard.html  ──→ back to Portfolio.html
    ├──→ SneakersStore.html      ──→ back to Portfolio.html
    └──→ TaxiDriverLoyalty.html  ──→ back to Portfolio.html
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Page structure and semantic markup |
| CSS3 | Styling, layouts (Flexbox & Grid), animations |
| Google Fonts (Poppins, Mulish) | Typography |
| SVG Icons (inline) | Lightweight, scalable icons — no icon library dependency |
| skillicons.dev | Tech stack icon display in the hero section |

> **No JavaScript framework, no build tools, no dependencies.** The entire portfolio runs directly in the browser by opening `Portfolio.html`.

---
