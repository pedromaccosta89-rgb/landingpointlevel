# CLAUDE.md — PointLevel Landing Page

## Project Overview

This repository contains a **static marketing landing page** for **PointLevel**, a digital marketing agency led by Pedro Costa. The page is written in Portuguese (pt-PT) and targets Portuguese-speaking businesses seeking digital marketing services.

- **Type**: Single-page static HTML site
- **Language**: Portuguese (pt-PT)
- **Purpose**: Lead generation and conversion for digital marketing services

---

## Repository Structure

```
landingpointlevel/
├── CLAUDE.md                        # This file
└── Landing PointLevel/
    ├── index.html                   # The entire site (HTML + CSS + JS, ~1000 lines)
    └── assets/
        └── img/
            ├── logo.webp            # PointLevel brand logo
            └── pedro.webp           # Pedro Costa hero photo
```

All HTML, CSS (inline `<style>`), and JavaScript are contained in a single `index.html` file. There is no build system, no package manager, and no external dependencies beyond CDN-loaded resources.

---

## Technology Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 (semantic) |
| Styling | Tailwind CSS (CDN) + inline `<style>` block |
| Typography | Poppins (Google Fonts CDN) |
| Scripting | Vanilla JavaScript |
| Images | WebP format |

**CDN Dependencies** (loaded at runtime, no local install needed):
- `https://cdn.tailwindcss.com` — Tailwind CSS utility classes
- Google Fonts — Poppins typeface

---

## Page Sections (index.html)

| Section | Anchor ID | Lines (approx.) | Description |
|---|---|---|---|
| `<head>` / Styles | — | 1–272 | Meta, Tailwind config, inline CSS, animations |
| Header / Nav | — | 274–324 | Fixed nav with logo, desktop menu, mobile hamburger |
| Hero | — | 328–411 | Value prop, CTA buttons, KPI cards, hero image |
| Credibility Bar | — | 413–422 | Three key selling-point pills |
| Problem Section | — | 424–500 | Pain points (4 cards) |
| Approach | — | 505–563 | Core values (ROI focus, transparency, efficiency) |
| Services | `#servicos` | 595–650 | Four service cards |
| Process | `#processo` | 660–690 | Three-step process (Analyse → Strategy → Execute) |
| Target Audience | — | 700–778 | Ideal vs non-ideal client profiles |
| Contact Form | `#formulario` | 780–830 | Lead capture form |
| Sticky CTA | — | 832–835 | Mobile-only fixed bottom button |
| Footer | — | 838–884 | Links, contact info, copyright |
| JavaScript | — | 888–943 | Mobile menu, form handling, smooth scroll |

---

## Brand / Design System

### Color Palette (Tailwind custom config)

| Token | Hex | Usage |
|---|---|---|
| `brand-dark` | `#021b23` | Background, dark sections |
| `brand-green` | `#7dc1a3` | Primary accent, CTAs |
| `brand-light` | `#aff4a7` | Highlights, secondary accent |

### Typography
- Font family: **Poppins** (weights 300–800 used)
- Headings: large, bold, gradient text effects common
- Body: light weight (300–400) on dark backgrounds

### CSS Animations
- `float` — subtle vertical float for decorative elements
- `slideInLeft` — entrance animation for hero content
- `fadeIn` — general fade-in for sections

### CSS Patterns
- All styles live in a single `<style>` block in `<head>`
- Tailwind utility classes used for layout, spacing, and responsive breakpoints
- Custom classes like `.gradient-hero`, `.service-card`, `.hero-photo` layer on top of Tailwind
- CSS masks used on hero image for fade-out effect

### Responsive Breakpoints (Tailwind defaults)
- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px

---

## JavaScript Functionality

All JS is at the bottom of `index.html` inside a `<script>` tag.

| Function | Purpose |
|---|---|
| `toggleMobileMenu()` | Opens/closes hamburger nav panel |
| `selectService(service)` | Pre-selects a service in the contact form |
| Outside-click listener | Closes mobile menu when tapping outside |
| Form submit handler | Shows success message; **no actual backend submission** |
| Smooth scroll | Handles `#anchor` link navigation |

> **Note**: The contact form currently only displays a client-side success message on submit. There is no backend or API endpoint wired up. If form submissions need to be captured, integrate a service like Formspree, Netlify Forms, or a custom endpoint.

---

## Development Workflow

### Making Changes

Since there is no build step, edit `Landing PointLevel/index.html` directly and open it in a browser to preview.

```bash
# Open locally
open "Landing PointLevel/index.html"
# or on Linux:
xdg-open "Landing PointLevel/index.html"
```

### No Build / No Install Required

There is no `npm install`, `yarn`, `pip install`, or any setup step. The page is self-contained.

### Branching Strategy

- `master` — production branch, stable
- Feature branches use prefixes: `codex/`, `claude/`, etc.
- Changes go through pull requests before merging to `master`

---

## Key Conventions

1. **Single-file architecture**: All HTML, CSS, and JS stays in `index.html` unless the project explicitly migrates to a build system.
2. **Inline styles**: Custom CSS goes in the `<style>` block in `<head>`, not in separate files.
3. **Tailwind first**: Use Tailwind utility classes for spacing, layout, and responsive design before adding custom CSS.
4. **Portuguese copy**: All user-facing text must remain in Portuguese (pt-PT). Do not translate or alter copy without explicit instruction.
5. **No frameworks**: Keep JavaScript vanilla. Do not introduce React, Vue, or other frameworks without explicit approval.
6. **WebP images**: Use `.webp` format for all images to maintain performance.
7. **Semantic HTML**: Use appropriate semantic elements (`<section>`, `<header>`, `<nav>`, `<footer>`, `<main>`, `<article>`).
8. **Mobile-first**: Design and test mobile layout first, then scale up.
9. **Conversion focus**: Every section exists to move the visitor toward the contact form. Preserve the PAS (Problem–Agitate–Solve) narrative structure.
10. **Commit messages**: Use clear, descriptive messages. Prefer Portuguese for content-related commits, English is also acceptable.

---

## What NOT to Do

- Do not add a build system, bundler, or package manager unless explicitly requested.
- Do not split `index.html` into multiple files unless a migration is planned.
- Do not change the color scheme or typography without explicit design approval.
- Do not add external JavaScript libraries via CDN without verifying they don't conflict with existing functionality.
- Do not wire up the contact form to any backend service without confirming the target endpoint with the repository owner.
- Do not translate the page content to another language.

---

## Deployment

The site is static and can be deployed to any web host that serves static files:
- Upload the `Landing PointLevel/` directory to the web root
- No server-side processing needed
- Ensure WebP image format is supported by the hosting server (all modern hosts support it)

---

## Contact / Owner

- **Repository owner**: pedromaccosta89 (`pedromaccosta89@gmail.com`)
- **Agency**: PointLevel
- **Principal**: Pedro Costa — Estrategista Digital
