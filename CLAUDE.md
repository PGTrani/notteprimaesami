# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project status

This repository contains a single-page, self-contained static site: a prayer-vigil
page for students the night before the *maturità* exam ("notte prima esami",
Esame di Stato, 17 giugno 2026). The whole site is `index.html` (CSS and JS
inlined, no external dependencies), ready for GitHub Pages.

## Source of truth for content

The liturgical text in `index.html` is transcribed **verbatim** from
`Momento_di_preghiera_maturandi_2026.docx` (the `_SMARTPHONE.docx` variant has
identical text). Do not rewrite, paraphrase, or invent liturgical text — any
content change must trace back to that source. The three Pope Leo XIV quotations
in the introduction have footnote citations (Giubileo dei Giovani, Tor Vergata,
2-3 agosto 2025) in the page footer.

## Build / run / deploy

No build step.

- Preview locally: open `index.html` in a browser, or `python3 -m http.server` then visit the served page.
- Deploy: push to GitHub and enable GitHub Pages (Settings → Pages → Deploy from a
  branch → `main` / root). For a custom domain add a `CNAME` file; a plain
  `username.github.io/notteprimaesami` address needs nothing extra. See `README.md`
  for the full deploy checklist.
- After deploying, update the `og:url` placeholder (`https://USERNAME.github.io/notteprimaesami/`)
  in `index.html`'s `<head>` with the real site URL.

## Architecture of `index.html`

- **Theming**: CSS custom properties on `:root`, light values by default, dark
  values via `@media (prefers-color-scheme: dark)`. `:root[data-theme="light"|"dark"]`
  blocks let the user override the system preference; the choice is stored in
  `localStorage` (`theme`) and re-applied by an inline `<head>` script before
  first paint (avoids a flash of the wrong theme).
- **Text size**: a `--font-scale` CSS variable drives `html { font-size: ... }`.
  The `A−` / `A` / `A+` buttons adjust it (0.85–1.5, step 0.125), persisted in
  `localStorage` (`fontScale`) and re-applied the same way as the theme.
- **Content structure**: four `<section>`s matching the brief's four parts
  (Introduzione, Preghiera dei maturandi, Preghiera a San Giuseppe da Copertino,
  Benedizione finale), each `id`-anchored and linked from the in-page index nav.
- **Formatting conventions** (CSS classes used throughout the prayer text):
  - `.voce` — speaker labels (Celebrante / Maturando N / Tutti), accent-colored.
  - `.risposta` — highlighted box for the assembly's responses (`Ascoltaci,
    Signore` / `Amen`).
  - `.preghiamo` — bold `Preghiamo.` cue.
  - `.orazione` — serif verse blocks with `<br>` preserving the original line breaks.
  - `.amen` — accent-colored `Amen`.
  - `.cit-papa` + `<sup><a href="#notaN">` — Pope quotations linked to footnotes
    in the `<footer>`.
- Palette: bordeaux accent `#7B2D26` (light) / `#E59387` (dark) on ivory `#FBF6EE`
  / dark `#1E1A17`; serif (`Georgia`/system serif) for prayers, sans-serif
  (system UI stack) for chrome.
