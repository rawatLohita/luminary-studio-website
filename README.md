# Luminary Studio — Website

> A complete multi-page website built with **HTML5**, **CSS3** & **JavaScript** — no frameworks, no libraries, no backend required.

---

## Quick Reference

| Field | Details |
|---|---|
| **Project** | Luminary Studio Website |
| **Pages** | 3 (Home, About, Contact) |
| **Languages** | HTML5, CSS3, JavaScript |
| **Fonts** | Playfair Display + DM Sans (Google Fonts) |
| **CSS File** | `css/style.css` (single external file) |
| **Responsive** | Mobile, Tablet, Desktop |
| **Backend** | None required |

---

## File Structure

```
website/
├── index.html          # Home page — hero, features, CTA, footer
├── about.html          # About page — story, image, team cards
├── contact.html        # Contact page — info panel + contact form
├── css/
│   └── style.css       # All CSS for the entire site (one file)
└── images/             # Folder for future real images/assets
```

---

## About the Project

**Luminary Studio** is a fictional digital design agency website. It demonstrates a complete, real-world multi-page site with a cohesive design system — a visitor lands on the Home page, discovers the studio's services, navigates to About to learn about the team, and submits a project enquiry through the Contact page.

**Design direction:** Editorial-refined aesthetic — warm off-white background, deep navy primary (`#1A2340`), amber accent (`#D4882B`), Playfair Display serif headings paired with DM Sans geometric body text.

---

## How to Run Locally

### Option A — VS Code Live Server (Recommended)

1. Open VS Code → Extensions (`Ctrl+Shift+X`) → search **"Live Server"** by Ritwick Dey → Install
2. Open your `website/` folder (`File → Open Folder`)
3. Right-click `index.html` → **"Open with Live Server"**
4. Browser opens at `http://127.0.0.1:5500` and **auto-refreshes on every save**

### Option B — Open Directly

Double-click `index.html` in File Explorer / Finder. No server needed — just refresh the browser manually after each edit.

---

## 🛠️ Technologies & Techniques

### HTML5
All pages use semantic elements — no generic `<div>` containers for structural roles.

| Element | Used For |
|---|---|
| `<header>` | Sticky top navigation bar |
| `<nav>` | Navigation link group with `aria-label` |
| `<main>` | Primary page content wrapper |
| `<section>` | Logical content groupings (hero, features, etc.) |
| `<article>` | Feature cards and team member cards |
| `<aside>` | Contact info panel on the Contact page |
| `<footer>` | Site-wide footer |

### CSS3 — `css/style.css`

One external file styles all three pages. Key techniques:

- **CSS Custom Properties** in `:root` — every colour, font, shadow, and radius is a variable; change the palette in one place
- **CSS Grid** for major two-column layouts (hero, about story, contact, footer columns)
- **Flexbox** for one-dimensional alignment (nav, buttons, form rows, footer bar)
- **`clamp()`** for fluid typography that scales smoothly between screen sizes
- **`position: sticky`** on the header so navigation follows scrolling
- **`backdrop-filter: blur(12px)`** for the frosted-glass nav effect
- **`clip-path: ellipse()`** for the curved wave cutout at the bottom of page heroes
- **`@keyframes` animation** for the pulsing live-status dot in the hero card
- **CSS pseudo-elements** (`::before`, `::after`) for decorative glows and overlays — no extra HTML
- **Hover transitions** on `transform` + `box-shadow` for card lifts and button states
- **Three responsive breakpoints** at `1024px`, `768px`, and `480px`

### Google Fonts

Imported at the top of `style.css` via `@import url(...)`:

- **Playfair Display** — high-contrast serif for headings; conveys elegance and authority
- **DM Sans** — clean geometric sans-serif for body text and UI; highly legible at small sizes

Only the required font weights are loaded to keep page performance fast.

### Vanilla JavaScript

Minimal JS is embedded in a `<script>` tag at the bottom of each page:

- **Mobile nav toggle** — hamburger button adds/removes `.open` class on the nav `<ul>`, with `aria-expanded` updated for accessibility
- **Contact form validation & success state** (`contact.html` only) — validates required fields on click, highlights empty fields in red, then shows a success message without a page reload

---

## 📄 Page-by-Page Breakdown

### `index.html` — Home Page

The entry point. Communicates who the studio is, what they offer, and drives visitors to act.

- **Sticky header** with frosted glass effect, logo mark, nav links, and CTA button
- **Hero** — two-column CSS Grid. Left: headline with italic amber accent, description, two CTA buttons. Right: dark navy card built in CSS with layered decorative elements, four stats, and a pulsing live badge
- **Features section** — four-column grid of `<article>` cards that lift on hover
- **CTA band** — full-width dark section with radial amber glow via `::before`
- **Footer** — four-column grid: brand info, nav links, service links, newsletter input row

### `about.html` — About Page

Builds trust and human connection — telling the studio's story, values, and team.

- **Page hero** — navy background with `clip-path` ellipse wave cutout at the bottom edge
- **Story section** — two-column grid. Left: image placeholder (swap for a real `<img>`), amber stat box breaking out of the image with `position: absolute`. Right: intro text, 2×2 values grid, CTA button
- **Team section** — three-column card grid with emoji placeholders (swap for real photos), name, amber role label, and bio

### `contact.html` — Contact Page

The conversion page — designed entirely to get a visitor to send a message.

- **Contact grid** — unequal CSS Grid (`5fr 7fr`) giving more visual weight to the form
- **Info panel** (`<aside>`) — studio address, email, phone, and hours with icon boxes
- **Contact form** — first/last name row, email, subject `<select>` dropdown, `<textarea>`, submit button. All inputs have matching `label`/`id` pairs. Focus states use an amber `box-shadow` ring
- **Success state** — valid submission hides the form and shows a success message; no page reload

---

Author - Lohita Rawat
