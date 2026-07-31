# AutoSmart Automation — Website

A 4-page static website: `index.html` (Home), `services.html`, `about.html`, `contact.html`.
No build tools needed — plain HTML/CSS/JS. Open `index.html` in any browser to preview.

## Adding your real logo

Right now the site uses a small placeholder SVG mark + text as the logo (in the header and footer of every page). Once you have your two logo files:

1. Put them here:
   - `assets/img/logo-dark.png`  → the version that works on a **light** background (used in the header)
   - `assets/img/logo-light.png` → the version that works on a **dark** background (used in the footer, and in the header if you switch the header to a dark bar)
2. In each HTML file, find this block inside `<header class="site-header">`:
   ```html
   <a href="index.html" class="logo">
     <svg class="logo-mark" ...>...</svg>
     <span>AutoSmart<br><small>Automation</small></span>
   </a>
   ```
   Replace it with:
   ```html
   <a href="index.html" class="logo">
     <img src="assets/img/logo-dark.png" alt="AutoSmart Automation" class="logo-img">
   </a>
   ```
3. Do the same in the `<footer>` block using `logo-light.png`.
4. If your logo's proportions are very different from a square, adjust `.logo-img { height: 34px; }` in `css/style.css` if it looks too big/small.

## Making the contact form actually send emails

The form on `contact.html` currently just shows a "thanks" message in the browser — it doesn't send anywhere yet, since that needs a backend or a form service. Easiest options, no server needed:

- **Formspree** (free tier available): sign up at formspree.io, get a form endpoint, then change `<form id="contact-form">` to `<form id="contact-form" action="https://formspree.io/f/YOUR_ID" method="POST">` and remove the `e.preventDefault()` line in `js/script.js`.
- **Netlify Forms**: if you host on Netlify instead of GitHub Pages, just add `data-netlify="true"` to the `<form>` tag — Netlify handles the rest automatically.

## File structure

```
autosmart-automation/
├── index.html
├── services.html
├── about.html
├── contact.html
├── css/style.css
├── js/script.js
├── assets/img/        ← put your logo files here
└── README.md
```
