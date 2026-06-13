# Context — Online Ruler Website

Context file for AI assistants working on this project. Read this first.

## What this is

A free **online ruler** web tool that measures objects on screen at actual (real-world) size in cm, mm, and inches. Single static HTML page, no build step, no backend. Goal is to rank on Google/Bing for "online ruler" and related queries (see SEO files).

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire app — HTML, CSS, and JS in one file. This is the deliverable that ships. |
| `Online_Ruler_SEO_Keywords.md` | Keyword research (primary / secondary / long-tail) based on top-ranking competitors, June 2026. |
| `Online_Ruler_SEO_Keywords.xlsx` | Same keyword data in spreadsheet form. |

## How `index.html` works

Everything lives in one file. Structure:

- **`.stage`** — full-viewport measuring area. Two ruler strips: `.ruler-top` (horizontal) and `.ruler-left` (vertical), drawn dynamically with JS-generated tick marks (`.tick`) and number labels (`.tnum`).
- **`.block`** — the draggable/resizable orange measuring rectangle, anchored to the top-left corner. The user drags its handles to wrap an object; live width/height show in `#hRead` and `#vRead`.
  - Resize handles: `.edge-r` (width), `.edge-b` (height), `.corner-h` (both).
- **`.toolbar`** — floating top-right: cm/inch unit toggle, Calibrate button, lock button.
- **Calibration modal** (`#calOverlay`) — user lays a credit card (85.6 mm wide) on the screen and drags a slider until the orange bar matches, setting pixels-per-cm for true actual size.

### Key JS details
- `DEFAULT_PXCM = 37.795275591` (96 dpi fallback).
- Calibration constant `pxPerCm` is the heart of accuracy. Persisted in **`localStorage`** under `ruler.pxcm`; lock state under `ruler.locked`.
- `CARD_MM = 85.6` (standard ID/credit card width) is the calibration reference.
- `ORIGIN = 46` px matches the `--strip` CSS var (ruler strip thickness) — keep these in sync if you change one.
- Units: `cm` or `in`; conversion via `2.54` cm/inch. `fmt()` formats readouts.

### Theming
CSS custom properties in `:root` (dark navy bg `--bg:#0f1530`, orange accent `--accent:#f6a623`). Change colors there, not inline.

## Conventions / gotchas

- **Single-file by design** — keep HTML, CSS, JS together in `index.html`. Don't split into separate assets unless the project owner asks.
- **No frameworks, no dependencies, no build.** Vanilla JS only. Open the file in a browser to test.
- `localStorage` is the only persistence — there's no server.
- Mobile matters: `touch-action:none`, viewport locked (`maximum-scale=1.0`), `dvh` units used. Test touch dragging, not just mouse.
- SEO is a primary goal. The `.info` block below the fold and the `<head>` meta tags carry the target keywords — preserve/extend them when editing copy (cross-reference `Online_Ruler_SEO_Keywords.md`).
- If you edit ruler strip thickness, update **both** `--strip` (CSS) and `ORIGIN` (JS).

## Common tasks
- **Improve accuracy / calibration UX** → calibration modal + `pxPerCm` logic in the `<script>`.
- **Add units (e.g. mm display)** → `fmt()` and the unit toggle.
- **SEO copy changes** → `<head>` meta + `.info` section; align with keyword files.
- **Styling** → `:root` CSS variables first.
