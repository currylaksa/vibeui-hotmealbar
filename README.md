# Hot Meal Bar — Website

A single-page marketing site for **Hot Meal Bar** (好米巴 · مطعم المسلم الصيني),
a Halal Chinese-Muslim restaurant known for hand-pulled *mee tarik*, slow-simmered
beef broth, and a signature house chili oil. Built as a website-design competition
entry.

🔗 **Live:** https://currylaksa.github.io/vibeui-hotmealbar/

---

## About the brand

Northwestern-Chinese / Xinjiang / Hui style cooking, **fully halal** (no pork, no
lard). Affordable and generous — student discounts, free refills, and a **Menu
Rahmah** at RM5. Three branches: **UKM Bangi** (PUSANIKA, Level 3), **Cyberjaya**,
and **UTM Johor Bahru**.

## Design approach

The site deliberately avoids the generic "restaurant template" look:

- **Art direction — "Chili-Oil Editorial":** deep chili red + warm cream, bold
  serif display type, with the chili-oil drip as a recurring brand motif.
- **Signature interaction:** a glossy chili-oil stream that tracks your scroll
  progress down the page (disabled under `prefers-reduced-motion`).
- **Graphic-led, not photo-led:** since usable food photography was limited, the
  visuals lean on CSS/SVG art (a hand-pulled-noodle bowl, abstract dish gradients,
  inline SVG icons) instead of stock imagery.
- **Authentic content:** real branches, prices, contact, and the Hui/Xinjiang
  heritage story.

## Features

- One-page cinematic scroll with sticky anchor navigation
- Fully **responsive** (laptop → phone), with a mobile slide-down menu
- **Accessible:** semantic landmarks, skip link, visible focus states, `aria`
  labels on icon-only controls, and full `prefers-reduced-motion` support
- Lightweight scroll-reveal and animations via `IntersectionObserver` — no
  libraries
- Real brand logo, processed into transparent, theme-matched assets

## Tech stack

Plain **HTML + hand-written CSS + vanilla JS**. No framework, no build step, no
runtime dependencies (web fonts load from Google Fonts). Just static files — ideal
for GitHub Pages.

## Project structure

```
.
├── index.html              # the entire page
├── styles.css              # all styling, responsive rules, reduced-motion
├── script.js               # scroll-reveal, chili-oil scroll rail, mobile nav
├── assets/
│   ├── logo-mark.png       # navy H-mark (nav)
│   └── logo-full-light.png # cream full logo (footer)
├── logo.jpg                # original source logo
├── CONTEXT.md              # domain glossary (Mee Tarik, Menu Rahmah, …)
└── README.md
```

## Run locally

Open `index.html` directly, or serve it:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Push to the `main` branch (already configured — see below).
2. On GitHub: **Settings → Pages**.
3. **Build and deployment → Source:** *Deploy from a branch*.
4. **Branch:** `main`, **folder:** `/ (root)`. Save.
5. Wait ~1 minute. The site goes live at
   **https://currylaksa.github.io/vibeui-hotmealbar/**.

No configuration needed — all paths are root-relative.

## Logo assets

The real logo (`logo.jpg`, navy on white) is processed into transparent,
theme-matched assets:

- `assets/logo-mark.png` — navy H-mark, used in the nav (on cream).
- `assets/logo-full-light.png` — cream silhouette of the full logo
  (mark + 好米巴 / HotMealBa), used in the dark footer.

To regenerate after changing `logo.jpg`, re-run the Pillow crop script that builds
these (crops to content, knocks out the white background, recolors the footer copy
to cream).

## Links & notes

- **Instagram** and **Facebook** are wired to the real profiles.
- **Grab** and **foodpanda** order buttons are intentionally not linked (point to
  `#`); add real URLs in `index.html` if/when wanted.
- **TikTok** is a placeholder (`#`).
- Menu prices are marked *indicative — confirm in-store*.
