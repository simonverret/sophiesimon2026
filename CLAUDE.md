# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Static wedding invitation site for Simon et Sophie, deployed at www.sophisimon2026.com. No build tools, no framework, no dependencies — just [index.html](index.html) and [styles.css](styles.css).

## Deployment

Pushing to `main` automatically deploys to GitHub Pages via [.github/workflows/static.yml](.github/workflows/static.yml). Preview locally by opening `index.html` directly in a browser.

## Architecture

- **[index.html](index.html)**: Single page in French. Contains an RSVP form that POSTs to Google Forms using a hidden `<iframe>` trick — this avoids a redirect to Google's confirmation page. On iframe load after submission, the form is hidden and a thank-you message shown instead.
- **[styles.css](styles.css)**: Dark theme (black background, light text). Two Google Fonts loaded: *EB Garamond* for `h1`, *Source Sans Pro* for body. Custom radio buttons via `appearance: none` + CSS.

## Google Form integration

The form `action` URL and `entry.*` field names in `index.html` correspond to a specific Google Form. To change form fields, update both the `name="entry.XXXXXXXXX"` attributes and the Google Form itself.
