# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A self-study electrical theory course based on the Danish textbook *El-Teori* (EFU / Den Jydske Haandværkerskole, 2006). It is a **static site** built with Markdown + vanilla JavaScript — **no frameworks, no build step, no package manager**. The site is published via GitHub Pages with Jekyll.

## Build / run / deploy

- **Local preview**: open any `.md` or `interaktiv/*.html` file directly in a browser, or run `bundle exec jekyll serve` if Jekyll is installed locally. No `npm`, no compile step.
- **Deployment**: pushing to `main` triggers `.github/workflows/pages.yml`, which builds with `actions/jekyll-build-pages@v1` and deploys to GitHub Pages. The workflow is the canonical build — match its behavior, not local Jekyll quirks.
- **No tests, no linter.** Validate changes by opening the affected page in a browser and clicking through the language switcher.

## Architecture

### Trilingual content layout
Course material is mirrored across three top-level language directories: `da/` (Danish — source of truth), `en/` (English), `ar/` (Arabic, RTL). Each contains `index.md` and `kapitler/NN-slug.md` (22 chapters). Only `da/` also has `opgaver/` (exercises with solutions); `en/` and `ar/` link back to the Danish exercises.

**Filenames are identical across languages** (Danish slugs like `12-1-faset-vekselstroemsteori.md` are kept in `en/` and `ar/` too). When adding/renaming a chapter, update all three directories plus the `index.md` tables in each, or cross-language links break.

### Interactive tools (`interaktiv/`)
Six standalone HTML files (Ohm's law calculator, series/parallel resistance, AC visualizer, base converter, logic-gate sim, quiz). Each file is **self-contained**: inline `<style>`, inline `<script>`, no shared assets, no external CDN. They are linked from chapter pages via relative paths like `../interaktiv/ohms-lov.html`.

**i18n pattern** (consistent across all six tools):
- Top-right `<div class="lang-switcher">` with three buttons `data-lang="da|en|ar"`.
- A single `I18N` object literal in the inline script holds `{ da: {...}, en: {...}, ar: {...} }`.
- `applyLang(lang)` updates `document.documentElement.lang`, sets `dir="rtl"` for `ar`, then walks `[data-i18n]` and `[data-i18n-placeholder]` elements and replaces their text/placeholder from the dict.
- Translatable strings in the markup carry `data-i18n="key"` (or `data-i18n-placeholder="key"`); default Danish text lives in the element body as a fallback.

When adding a new tool or string, follow this exact pattern — do not introduce a framework, build tool, or external i18n library.

### Jekyll / GitHub Pages config (`_config.yml`)
Three plugins are critical and intentional:
- `jekyll-relative-links` — rewrites `[link](foo.md)` to `foo.html` on the deployed site so the same links work locally in a Markdown viewer and on Pages.
- `jekyll-default-layout` + `jekyll-optional-front-matter` — let chapter files skip front matter entirely.
- `readme_index` — renders each `README.md` (and `index.md`) as `index.html`, including in subfolders.

The `defaults` block disables Liquid templating for `interaktiv/` because the inline JavaScript contains `{{` / `{%` characters that would otherwise be parsed by Liquid and break the page. **Do not remove this exclusion** when editing tools.

### Chapter file convention
Each chapter Markdown starts with `# Kapitel N — Title`, a one-line Arabic gloss `> ...`, a `## 🎯 Læringsmål` (learning objectives) list, then numbered sections `## N.1`, `## N.2`, etc. Match this structure when adding chapters so the `index.md` table-of-contents and quiz chapter labels stay consistent.

## Constraints worth remembering

- **No build step** is a deliberate design choice — keep contributions framework-free and dependency-free.
- The original EFU textbook is **not** in the repo (copyright); summaries are reworded. Don't paste textbook content verbatim.
- License is MIT (`LICENSE`); the copyright header notes EFU owns the source textbook.
