# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static marketing/landing page for Atlasight AI, built on Bootstrap 5. No build pipeline or package manager — SCSS is compiled to CSS using **CodeKit** (Mac app).

## SCSS Compilation

The only build step is compiling SCSS → CSS:

- **Source:** `scss/theme.scss` (entry point)
- **Output:** `assets/css/theme.css`
- **Tool:** CodeKit 3 (`scss/config.codekit3` is the project config — do not hand-edit)
- **CLI alternative:** `sass scss/theme.scss assets/css/theme.css`

After editing any `.scss` file, recompile to update `assets/css/theme.css`. Never edit `assets/css/theme.css` directly.

## Architecture

**Single-page site** — everything is in `index.html`. No routing, no JS framework.

**SCSS structure:**
- `scss/theme.scss` — entry point: defines all color/brand variables, imports Bootstrap, then imports theme styles
- `scss/theme/styles.scss` — imports `_mixins.scss`, `_base.scss`, `_landing.scss`
- `scss/bootstrap/` — Bootstrap 5 source (vendor, do not edit)

**Color variables** (defined at top of `scss/theme.scss`):
- `$theme-color-primary: #47b0df` — blue, used as `$primary` and dark backgrounds
- `$theme-color-secondary: #71c853` — green
- `$theme-text-color-primary: #212B35`

**JS:** `assets/js/main.js` — only initializes the Flickity testimonial carousel.

**Vendor assets (do not edit):**
- `assets/plugins/bootstrap/` — compiled Bootstrap CSS/JS
- `assets/plugins/flickity/` — carousel plugin
- `assets/fontawesome/` — icon font

**Legal pages:** `legal/privacy.md`, `legal/terms.md`, `legal/data-owner-agreement.md` — Markdown files served as-is (not compiled to HTML).

## Deployment

Static files only — deploy the root directory. No server-side processing required.
