# RGUHS MPT Paper IV - Model Answers (May 2025)

An interactive, accessible HTML study tool built from the **RGUHS Master of Physiotherapy (MPT)**
**Paper IV - Physiotherapy Interventions in Musculoskeletal Disorders** solved paper
(Q.P. Code 8132), **May 2025** examination.

The whole resource is a **single self-contained HTML file** - no build step, no dependencies, no
internet connection required. Just open it in a browser.

## Files

| File | Purpose |
| --- | --- |
| `RGUHS_MPT_PaperIV_Model_Answers_May2025.html` | The interactive study page (open this). |
| `index.html` | Minimal landing page used by the GitHub Pages site. |
| `README.md` | This documentation. |

## What the build does to the source text

The raw solved paper is processed into clean, readable HTML:

- **Whitespace cleanup** - stray/duplicated spaces removed and text re-flowed.
- **LaTeX converted to readable symbols** - `\text{...}`, `^\circ` -> degrees, `\sigma`, `\epsilon`,
  `\mu`, `\beta`, `\times`, `\le`, `\int`, `\vert` and subscript notation (`\sigma_u` -> sigma-sub-u).
- **Structure rebuilt** - question headings, sub-headings, and **nested** bullet/numbered lists
  (indented sub-points become proper nested lists).
- **Tables recovered** - both TAB-separated tables and ASCII box tables become real bordered tables
  with header rows.
- **ASCII flow diagrams** - single-column box diagrams become clean vertical flow boxes with arrows.
- **Term popups** - difficult words are wrapped with definitions (see below).

## Components

### 1. Toolbar (sticky, top)
Minimal, monochrome by default. Contains: three highlight swatches, **Erase**, **Clear all**,
**Term notes** (toggles the popup underlines), **Night mode**, and **Fit to screen**.

### 2. Content sections (`.card > section.q`)
One `<section class="q">` per question. Each has a heading row (with its notes pill) and a body
containing the answer, tables and diagrams.

### 3. Term popups (`.term[data-note]`)
Every difficult word is wrapped in `<span class="term" data-note="...">`. Hovering or tapping shows a
plain-English definition in a floating popup. Definitions also appear in the collapsible **glossary**
at the foot of the page.

### 4. Study Notes (auto-saving)
Two synced entry points, both saved automatically in the browser:

- **Floating "Study Notes" button** (`#notesFab`, bottom-right, always visible) opens a slide-out
  drawer (`#notesDrawer`) listing every question with its own notes box. A badge shows how many
  questions have notes.
- **Notes pill on each question heading** (`.notes-toggle`) opens a notes box beside the question
  (wide screens) or under the heading (narrow screens). When a question has no notes, it collapses to
  a small numbered button.

### 5. Night mode
A light/dark toggle; the choice is remembered. Both themes meet contrast expectations for body text.

### 6. Fit to screen
Toggles between a comfortable reading width and full-window width; remembered between visits.

### 7. Highlighting
Select text, then click a colour swatch (yellow / green / pink). **Erase** removes highlights in the
selection; **Clear all** removes every highlight.

### Storage keys
All user data is stored locally in the browser (nothing is uploaded), namespaced to this paper so it
does not mix with other papers on the same site:

- `rguhsMay2025-highlights` - your highlights
- `rguhsMay2025-note-qN` - notes for question N
- `rguhsMay2025-theme` - `dark` / `light`
- `rguhsMay2025-fit` - `1` / `0`

## Accessibility

- Semantic headings (`h1`-`h4`), real `<table>` elements with header cells, and real lists.
- Interactive controls are native `<button>` elements with `aria-expanded` / `aria-controls` on the
  notes toggles and `aria-live` on the save status.
- Term popups are keyboard reachable (`tabindex="0"`, opened with Enter/Space, dismissed with Escape).
- Readable default font size, generous line height, and a print stylesheet (toolbar, popups and the
  notes UI are hidden when printing).

## Regenerating / editing

The HTML is generated from the source paper text. To change the content, edit the source and
re-run the generator; to tweak the look, edit the `<style>` block at the top of the HTML. The CSS
uses variables (`--bg`, `--ink`, `--accent`, ...) so the palette can be changed in one place.

## Definitions and sources

Definitions are written in plain English to explain the paper's terminology, drawing on standard
musculoskeletal physiotherapy references and the concepts cited in the paper itself (for example the
stress-strain behaviour of connective tissue associated with Nordin & Frankel, and Melzack and Wall's
Gate Control Theory). They are study aids, not quotations.

## Disclaimer

Study aid only - not a substitute for clinical judgement, and not an official university marking
scheme.
