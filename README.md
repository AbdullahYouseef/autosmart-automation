# AutoSmart Automation — Website

A 4-page static website: `index.html` (Home), `services.html`, `about.html`, `contact.html`.
No build tools needed — plain HTML/CSS/JS. Open `index.html` in any browser to preview.

## Logo files

Your logo is already wired in across all four pages. Here's what's in `assets/img/` and where each one is used:

| File | Used where | Notes |
|---|---|---|
| `logo-full.png` | Header (all pages) | Icon + wordmark, original green/black, transparent background |
| `logo-full-brass.png` | Footer (all pages) | Same lockup, recolored to the brass accent so it reads on the dark teal footer |
| `logo-icon.png` | — (spare) | Icon mark only, original color, transparent background |
| `logo-icon-brass.png` | — (spare) | Icon mark only, brass color, transparent background |
| `favicon.png` | Browser tab icon (all pages) | Icon mark only |

If you get new or updated logo files later, just replace these filenames with your new versions (keep the same names) and every page updates automatically — no HTML edits needed. If a new logo's proportions are very different, you may need to tweak `.logo-img { height: 38px; }` and `.footer-logo img.logo-img { height: 30px; }` in `css/style.css`.

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
