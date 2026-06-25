# Project Context & System Rules — CLA Bumbogo Website

> This file is the **single source of truth** for how this project must be built and
> maintained. The Cursor AI assistant and all human contributors must follow these
> rules on every change. Treat them as non-negotiable constraints.

---

## 1. Project Identity

- **Project:** Static landing hub for the **Christian Life Assembly (CLA) — Bumbogo** branch.
- **Purpose:** Central hub for sermons, photo galleries, and announcements — replacing
  fragmented sharing via chat groups.
- **Parent organisation:** CLA Central HQ — [clarwanda.org](https://clarwanda.org). The
  branch site must stay visually and institutionally consistent with HQ and always link back.
- **Hosting:** Free **GitHub Pages**. Repo: `github.com/64eyes/CLA-Bumbogo`.

---

## 2. Technical Rules (HARD constraints)

1. **Vanilla HTML5 only.** No frameworks, no build step, no npm, no bundlers, no React/Vue.
   The whole site must run by simply opening `index.html` in a browser.
2. **Plain CSS only**, in a single `style.css`. No SASS/LESS, no Tailwind, no CSS-in-JS.
3. **Minimal/zero JavaScript.** Only add tiny vanilla JS if absolutely necessary (e.g. a
   mobile menu toggle). Never add JS dependencies or libraries.
4. **Semantic CSS variables.** All colours, spacing, and fonts must be defined as CSS
   custom properties in `:root` at the top of `style.css`. Never hard-code a hex colour
   deeper in the stylesheet — always reference a `var(--...)`.
5. **Responsive by default.** Use CSS Grid and Flexbox. Must look good on phone, tablet,
   and desktop. Mobile-first where practical.
6. **Accessibility:** semantic tags (`<header>`, `<nav>`, `<main>`, `<section>`,
   `<footer>`), `alt` text on images, sufficient colour contrast.

---

## 3. ZERO Local Media Binary Storage (CRITICAL)

- **Never** commit video, audio, or heavy image files to this repository.
- **Sermons** → embedded from **YouTube** (video) or **Spotify** (audio) via `<iframe>`.
- **Photo galleries** → **linked out** to shared **Google Drive / Google Photos** albums.
- The only binaries allowed in-repo are tiny branding assets (logo, favicon, small icons).
- Rationale: keeps the site fast, the repo light, and hosting free.

---

## 4. Branding & Colour Palette

Derived from the official CLA Bumbogo flyer (deep olive/forest greens fading into warm
ochre/orange, on soft cream neutrals). Use these **semantic variable names**:

| Variable               | Meaning                       | Approx. value |
| ---------------------- | ----------------------------- | ------------- |
| `--color-forest-deep`  | Darkest olive/forest green    | `#1e2a13`     |
| `--color-forest`       | Primary deep green            | `#33421f`     |
| `--color-olive`        | Mid olive (accents/borders)   | `#5a6b34`     |
| `--color-ochre`        | Warm ochre (primary accent)   | `#c2691f`     |
| `--color-orange`       | Bright warm orange (CTAs)     | `#e07d2f`     |
| `--color-cream`        | Soft neutral background       | `#f6f1e7`     |
| `--color-sand`         | Slightly darker neutral       | `#e9e0cf`     |
| `--color-ink`          | Primary dark text             | `#241c11`     |

- **Headings** use a serif font (echoes the HQ "Christ Centered" hero feel).
- **Body** uses a clean sans-serif.
- Hero and header use the **green → ochre** gradient mood from the flyer.

---

## 5. Maintainability Rules (for non-technical media team)

- Every editable text block, link, or embed in `index.html` must be marked with an
  obvious comment: `<!-- EDIT: ... -->` explaining what to change and how.
- Editors should only ever change text **between** tags, never the tags/structure.
- Keep instructions in plain, non-technical language.

---

## 6. Git Workflow

- `main` = production (published by GitHub Pages). **Never commit directly.**
- `dev` = working branch. All edits happen here first, then PR `dev` → `main`.
- Commit messages: short, clear, action-first (e.g. `Add:`, `Update:`, `Fix:`).

---

## 7. File Map

- `index.html` — the entire page; content + structure.
- `style.css` — all styling; palette lives in `:root`.
- `README.md` — human-facing project documentation.
- `context.md` — this rules file.
