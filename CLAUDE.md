# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the marketing landing page for **Atlasight** by Atharch - an AI-powered mobile app that transforms documents into conversational knowledge bases. The site is a static Bootstrap 5 landing page.

## Build & Development

**SCSS Compilation:** The project uses CodeKit for SCSS compilation. The main entry point is `scss/theme.scss` which:
1. Defines theme color variables
2. Imports Bootstrap 5 SCSS
3. Imports custom theme styles from `scss/theme/`

The compiled CSS output is `assets/css/theme.css`.

**Local Development:** Open `index.html` directly in a browser. No build server required.

## Architecture

### File Structure
- `index.html` - Single-page landing site
- `scss/theme.scss` - Main SCSS entry point with color variables (primary: `#47b0df`, secondary: `#71c853`)
- `scss/theme/` - Custom styles split into `_base.scss` (global), `_landing.scss` (page-specific), `_mixins.scss`
- `scss/bootstrap/` - Bootstrap 5 source (do not modify)
- `assets/css/theme.css` - Compiled CSS
- `legal/` - Markdown files for privacy, terms, data-owner-agreement

### Styling Conventions
- Fonts: Maven Pro (body), Nunito (headings)
- Theme classes: `.theme-bg-primary`, `.theme-bg-secondary`, `.theme-btn`, `.theme-btn-ghost`
- Responsive breakpoints follow Bootstrap 5 defaults

### Email Obfuscation
Contact emails (`sales@atharch.com`, `info@atharch.com`) are rendered via JavaScript to prevent scraping - see inline scripts in `index.html`.

## Template Attribution

Based on Nova Bootstrap 5 template by Xiaoying Riley (3rd Wave Media). Footer attribution link must remain unless commercial license is purchased.
