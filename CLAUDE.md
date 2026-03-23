# CLAUDE.md — Gray Photography Portfolio

## Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

---

## Project Overview

| Field | Value |
|---|---|
| **Brand Name** | Gray Photography |
| **Tagline** | "Memories Shot on Digital or Film" |
| **Genre** | Digital & Film (amateur photography) |
| **Aesthetic** | Monochrome / minimalist — clean, easy on the eyes |
| **Build Type** | Multi-page HTML site |

---

## Pages & Structure

Build the following pages:

| Page | File | Purpose |
|---|---|---|
| Home / Hero | `index.html` | Full-screen photo backdrop, tagline, nav |
| Portfolio / Gallery | `gallery.html` | Filterable grid with lightbox |
| About | `about.html` | Photographer bio, portrait, brief story |
| Services | `services.html` | What Gray Photography offers |

### Navigation
- Consistent nav across all pages
- Links: Home, Gallery, About, Services

---

## Gallery Requirements
- **Filter categories:** Digital, Film, Medium Format
- **Lightbox:** Full-screen photo viewer on click, keyboard navigation (arrow keys + Escape)
- **Layout:** Masonry or equal-aspect grid — whichever suits the monochrome aesthetic better

---

## Photo Assets

> Photos will be provided by the client. Until then, use `https://placehold.co/` in monochrome tones (e.g. `?text=Digital` with dark/grey backgrounds).

Photo drop-in folders (swap placeholders when real photos arrive):
- `photos/digital/` — Digital category images
- `photos/film/` — Film category images
- `photos/medium-format/` — Medium format category images
- `brand_assets/` — Logo, color guide, or any brand files (provided later)

When real photos are dropped in, update `src` paths accordingly. Do not redesign — only swap assets.

---

## Design System

### Aesthetic Rules
- **Monochrome palette** — blacks, whites, greys only. No color accents unless client provides brand assets.
- **Photos as backdrops** — Hero and section backgrounds use full-bleed photo with dark overlay (`bg-gradient-to-b from-black/70 via-black/30 to-black/70` or similar)
- **Minimal UI chrome** — let photos breathe; keep UI elements sparse and low-contrast
- **Easy on the eyes** — avoid harsh pure white (#fff) for large text blocks; use off-white (~#f5f5f5) or light grey

### Typography
- **Headings:** Serif or thin-weight display font (e.g. `Playfair Display`, `Cormorant Garamond`, or `DM Serif Display`) — tight tracking (`letter-spacing: -0.03em`)
- **Body:** Clean geometric sans (e.g. `Inter`, `DM Sans`) — generous line-height (`1.7`)
- Load via Google Fonts CDN

### Colors (until brand assets provided)
```
--color-bg:        #0a0a0a   /* near-black background */
--color-surface:   #141414   /* elevated cards/panels */
--color-border:    #2a2a2a   /* subtle borders */
--color-text:      #e8e8e8   /* primary text */
--color-muted:     #888888   /* secondary/caption text */
--color-white:     #f5f5f5   /* headings, highlights */
```

### Anti-Generic Rules
- Never use default Tailwind blue/indigo palette
- Never use flat `shadow-md` — use layered, dark-tinted shadows
- Never use `transition-all` — animate only `transform` and `opacity`
- Every clickable element must have hover, focus-visible, and active states
- Surfaces use a layering system: base → elevated → floating
- Add subtle grain/texture to hero sections via SVG noise filter

---

## Technical Setup

- **Tailwind CSS** via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- **Local dev server:** `node serve.mjs` → `http://localhost:3000`
- **Screenshots:** `node screenshot.mjs http://localhost:3000`
- Screenshots auto-save to `./temporary screenshots/screenshot-N.png`
- All styles inline within each HTML file unless a shared `style.css` is explicitly needed

---

## Local Server
- Always serve on localhost — never screenshot a `file:///` URL
- Start server in background before any screenshots
- Do not start a second instance if already running

## Screenshot Workflow
- After any visual change: screenshot → read PNG → compare → fix → re-screenshot
- Do at least 2 comparison rounds before stopping
- Be specific in comparisons: call out exact pixel/spacing/color mismatches

---

## Hard Rules
- Do not add sections or features not listed above
- Do not add testimonials
- Do not add a contact form or contact page
- Do not use color accents until brand assets are provided
- Do not use `transition-all`
- Do not use default Tailwind blue/indigo as primary color
- Do not stop after one screenshot pass
- Match the monochrome aesthetic strictly — reject any "pop of color" suggestions
