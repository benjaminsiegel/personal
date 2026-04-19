# Handoff: benjaminrsiegel.com Redesign

## Overview
This is a full redesign of benjaminrsiegel.com — a personal author/historian website for Benjamin R. Siegel. The design is inspired by Carina del Valle Schorske's site: intimate, single-page feel, large photo left, conversational bio right, with scrollable sections below. The goal is a clean, literary, personal site that feels warm and human — not a sprawling academic CV.

## About the Design Files
The files in this bundle are **high-fidelity design references created in HTML** — not production code to copy directly. Your task is to recreate these designs in your existing site's codebase (likely a static HTML/CSS site managed via GitHub), preserving the visual design, typography, layout, and interactions as closely as possible.

The reference file is: `index v3.html`

## Fidelity
**High-fidelity.** Colors, typography, spacing, layout, and copy are all final (or close to it). Recreate pixel-accurately. The only placeholder element is the cover for *The Price of Protein* (no cover image exists yet — use the striped placeholder or omit the thumbnail).

---

## Layout

### Overall Structure
- **Nav** — sticky top bar, full width
- **Main** — two-column CSS grid: `42% | 1fr`, `gap: 72px`, `padding: 0 52px 64px`, `max-width: 1200px`, centered
- **Footer** — single line, centered copyright

### Left Column (Photo)
- Fixed/sticky photo (`position: sticky; top: 24px`)
- Photo: `aspect-ratio: 3/4`, `object-fit: cover`, `object-position: 40% top`
- Three icon links centered below photo: Faculty Page, Instagram, LinkedIn
- Icons: 20×20px SVG strokes, stacked above label text, `font-size: 10px`, uppercase, centered

### Right Column (Bio + Sections)
All content scrolls in the right column. Sections in order:
1. Bio (opening paragraph + body paragraphs)
2. Books
3. Events
4. Essays & Features
5. Media Appearances
6. Praise for Markets of Pain

---

## Design Tokens

### Colors
| Token | Value | Use |
|---|---|---|
| `--bg` | `#f2ede8` | Page background (warm blush) |
| `--plum` | `#40093c` | Accent: links, section labels, borders |
| `--ink` | `#1c1410` | Primary text |
| `--mid` | `#6b5e58` | Secondary text (bio body) |
| `--light` | `#a09490` | Tertiary: venues, credits, labels |

### Typography
| Role | Font | Size | Weight | Notes |
|---|---|---|---|---|
| Nav brand | Playfair Display | 26px | 400 | letter-spacing: 0.01em |
| Nav links | DM Sans | 11px | 400 | uppercase, letter-spacing: 0.12em |
| Bio opening | Cormorant Garamond | clamp(18px, 1.6vw, 22px) | 400 | line-height: 1.65 |
| Bio body | Cormorant Garamond | clamp(17px, 1.5vw, 20px) | 400 | line-height: 1.65, color: --mid |
| Section labels | DM Sans | 10px | 500 | uppercase, letter-spacing: 0.16em, color: --light |
| Book titles | Cormorant Garamond | 20px | 500 | |
| Book subtitles | Cormorant Garamond italic | 16px | 400 | color: --mid |
| Writing items | Cormorant Garamond | 18px | 400 | |
| Venue labels | DM Sans | 10px | 400 | uppercase, letter-spacing: 0.08em, color: --light |
| Praise quotes | Cormorant Garamond italic | 18px | 400 | line-height: 1.6 |
| Praise citations | DM Sans | 10px | 400 | uppercase, letter-spacing: 0.08em, color: --light |
| Footer | DM Sans | 10px | 400 | centered, letter-spacing: 0.06em |

### Spacing
- Nav height: `52px`, padding: `0 52px`
- Main padding: `0 52px 64px`
- Section top padding: `36px` (`.writing-section`)
- Section border: `1px solid rgba(28,20,16,0.12)` on top
- Book entry gap: `24px` between thumbnail and text
- Book entry bottom border: `1px solid rgba(28,20,16,0.08)`
- Writing item padding: `11px 0`
- Writing item border: `1px solid rgba(28,20,16,0.07)` on bottom

---

## Nav

```
[Benjamin R. Siegel]          [Books] [Writing] [Media] [Events] [Contact]
```

- Background: `--bg` (same as page — floats above content)
- Brand: Playfair Display, 26px, `--ink`
- Links: DM Sans, 11px, uppercase, color: `--mid`, hover: `--plum`
- "Contact" links to `mailto:siegelb@bu.edu`
- Sticky (`position: sticky; top: 0; z-index: 100`)

---

## Photo Column

- **Image**: `photo-informal.jpg` (casual outdoor photo, man with coffee and book)
  - Source on current site: `https://www.benjaminrsiegel.com/headshot.jpg` (formal) — replace with new photo
  - `object-position: 40% top` — slightly left of center to show tattoo on left arm
- **Icon links** (centered, `gap: 28px`, `margin-top: 20px`):
  - Faculty Page → `https://www.bu.edu/history/profile/benjamin-siegel/` — building icon
  - Instagram → `https://www.instagram.com/benjaminsiegel/` — IG icon
  - LinkedIn → `https://www.linkedin.com/in/benjamin-siegel29/` — LinkedIn icon
  - Each: icon (20×20 SVG stroke) stacked above label, `font-size: 10px`, uppercase, color: `--light`, hover: `--plum`

---

## Bio Text (right column top)

**Opening paragraph** (larger, `--ink`):
> I'm a writer and historian at Boston University. I uncover the commodity chains that have shaped modern life — from the power of empires to the drugs in our medicine cabinets and the food on our plates.

**Body paragraphs** (smaller, `--mid`):
1. New book: *Markets of Pain* (OUP 2026) — link to marketsofpain.com
2. Previous book: *Hungry Nation* (CUP 2018) — link to Cambridge UP
3. Next book: *The Price of Protein* (Ecco US / Monoray UK, forthcoming)
4. Writing venues + countries (US, Canada, UK, India, Pakistan, China, Germany, Switzerland, Italy)
5. Training/fellowships: Yale, Harvard, Harvard Academy, Yale Agrarian Studies
6. Personal: "I live with my family and too many bicycles in Jamaica Plain, Mass., and Lecco, Italy."
7. Agent: Sarah Khalil at Calligraph (link to calligraphagency.com); email link to siegelb@bu.edu

Links in bio: color `--plum`, `text-decoration: underline`, `text-decoration-thickness: 1px`, `text-underline-offset: 2px`

---

## Books Section

Label: "BOOKS" (section label style)
Border top separating from bio.

Three entries, each `display: flex; gap: 24px`:

| Book | Press | Thumbnail | Buy Links |
|---|---|---|---|
| Markets of Pain | Oxford UP · 2026 | `markets-of-pain-cover.jpg` | Book Website, Oxford UP, Amazon, Bookshop |
| Hungry Nation | Cambridge UP · 2018 | `hungry-nation-cover.jpg` | Cambridge UP, Amazon, Bookshop |
| The Price of Protein | Ecco (US) · Monoray (UK) · Forthcoming | Striped placeholder | (none yet) |

Thumbnail size: `width: 60px`, `aspect-ratio: 2/3`, `object-fit: cover`

Buy links: `font-size: 10px`, uppercase, `letter-spacing: 0.1em`, color: `--plum`, `border-bottom: 1px solid --plum`, no underline decoration, hover: `opacity: 0.65`

---

## Events Section

Label: "EVENTS"

Four items, each `display: flex; justify-content: space-between; align-items: baseline`:

| Title | Venue · Date |
|---|---|
| Book Launch: *Markets of Pain* | April 2026 · TBD |
| "Automatic for the People?: Labor, Machines, and Ecology in Modern India" | IIT Bombay · May 2025 |
| "Automatic for the People?" | U Penn CASI · Feb 2025 |
| "How Pain Came to Matter" | Harvard Medical School · May 2024 |

---

## Essays & Features Section

Label: "ESSAYS & FEATURES"

Five items with title (link) + venue:

| Title | Venue |
|---|---|
| The US Opioid Crisis Started in India | Vice |
| The Green Revolution at 50 | Public Books |
| Before Malala | Marginalia |
| Global Imaginaries of Indian Development | Am. Historical Review |
| Weeds and Power in Indian Environmental History | Environmental History |

---

## Media Appearances Section

Label: "MEDIA APPEARANCES"

Four items:

| Title | Venue |
|---|---|
| Food in Post-Independence India | Eat This! |
| Hungry Nation | New Books Network |
| The Kinds of Pain | Syntalk |
| From Bengal Famine to the Green Revolution | Ramblings of a Sikh |

---

## Praise Section

Label: "PRAISE FOR MARKETS OF PAIN"

Three blockquotes, each with `border-left: 2px solid rgba(64,9,60,0.2)`, `padding-left: 18px`:

1. David T. Courtwright (*Forces of Habit*)
2. David Herzberg (*White Market Drugs*)
3. Gabriela Soto Laveaga, Harvard University

Full quote text is in the HTML reference file.

---

## Footer

```
© 2026 Benjamin R. Siegel
```
Centered, DM Sans 10px, color `--light`, `border-top: 1px solid rgba(28,20,16,0.1)`

---

## Assets

| File | Source | Notes |
|---|---|---|
| `photo-informal.jpg` | Uploaded by user | Casual outdoor portrait — use this as main photo |
| `markets-of-pain-cover.jpg` | benjaminrsiegel.com/markets-of-pain-cover.jpg | Download and host locally |
| `hungry-nation-cover.jpg` | benjaminrsiegel.com/hungry-nation-cover.jpg | Download and host locally |

---

## Google Fonts

Add to `<head>`:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;1,400;1,500&family=DM+Sans:wght@300;400;500&family=Playfair+Display:wght@400;500&display=swap" rel="stylesheet">
```

---

## Files in This Bundle

- `README.md` — this document
- `index v3.html` — full high-fidelity reference design
- `photo-informal.jpg` — author photo to use on site
