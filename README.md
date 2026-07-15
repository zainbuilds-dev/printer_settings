# Proof Sheet — Photo Print Layouts

A browser-based tool that lets you print multiple photos on a single page, with exact control over how many photos per sheet — no cm-based sizing, no PDF conversion, no extra software.

## The Problem

Windows doesn't make it easy to print multiple photos the way most people actually want to:

- Selecting several photos in File Explorer and pressing **Ctrl+P** doesn't open a layout option at all — it just prints each photo full-page, one at a time.
- The alternative (right-click → Print) opens Windows' legacy "Print Pictures" wizard, but it only offers fixed physical sizes (4×6, 5×7, Wallet) — not a true "N photos per page" choice.
- There's no built-in way to choose black & white vs. color for the print job itself.
- The usual workaround — converting photos to a PDF first — adds an unnecessary extra step just to get a basic contact sheet.

There was no quick way to say: *"put 4 of these on one page and print them in black & white."*

## The Solution

A single-file, fully static web app that runs entirely in the browser:

- **Drag-and-drop or file picker** to load photos directly from the desktop — nothing is uploaded anywhere, all processing happens locally via the browser's File API.
- **Exact layout control** — choose 1, 2, 4, 6, or 9 photos per sheet using CSS Grid, with automatic pagination into multiple sheets if more photos are loaded than fit one layout.
- **Color / B&W toggle** — applied instantly via CSS filters before printing.
- **One-click print** — triggers the browser's native print dialog (`window.print()`), with a dedicated print stylesheet that maps each on-screen "sheet" to one physical printed page.
- **Zero install, zero backend** — just an HTML file. Works offline once opened, and can be hosted for free as a static site (e.g., GitHub Pages).

## Features

- Multi-photo select via drag-and-drop or file input
- Layout presets: 1 / 2 / 4 / 6 / 9 photos per page
- Auto-pagination across multiple print sheets
- Color and black & white printing modes
- Thumbnail preview with individual photo removal
- Sheet-by-sheet navigation before printing
- Fully client-side — no data ever leaves the device

## Tech Stack

- HTML5, CSS Grid, vanilla JavaScript
- Browser File API (drag & drop, file reading)
- Browser Print API (`window.print()` + print-specific CSS)
- No frameworks, no dependencies, no backend

## How to Use

1. Open `index.html` in any modern browser (or visit the [live demo](#)).
2. Drag photos in from your desktop, or click **Load photos**.
3. Pick a layout: 1, 2, 4, 6, or 9 photos per sheet.
4. Toggle **Color** or **B&W**.
5. Click **Print**, then choose your printer in the browser's print dialog.

## Deployment

This is a static site with no build step — it deploys directly to GitHub Pages, Netlify, or Vercel by pointing to `index.html`.

## Why This Project

Solves a genuine everyday annoyance — Windows' lack of a proper multi-photo, layout-aware print flow — with a lightweight tool that needed no framework, no server, and no installation to be useful.

---

**Live demo:** `[https://121425408001-ctrl.github.io/printer_settings/]`
**Repository:** `[https://github.com/121425408001-ctrl/printer_settings/]`
