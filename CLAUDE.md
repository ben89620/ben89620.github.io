# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal portfolio site for Ben Hung, hosted on GitHub Pages at `ben89620.github.io`. The entire site is a single self-contained `index.html` file — no build tools, no package manager, no frameworks.

## Structure

- `index.html` — all HTML, CSS, and JavaScript in one file
- `images/` — profile photo and skill card images (PNG/JPG)
- `CV/` — downloadable PDF resume

## Development

Open `index.html` directly in a browser to preview. No server or build step is required.

To preview with a local server (avoids some browser file:// restrictions):

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

## Architecture

All content is in `index.html`:

- **CSS** is inline in `<style>` — dark navy theme (`#0f172a` background, `#38bdf8` accent blue)
- **Profile picture** (`.profile-pic`) is absolutely positioned top-right relative to the viewport, outside the centered `.container` div
- **Skill cards** (`.skill-card`) use a `data-skill` attribute to key into the `skillData` JS object; clicking opens a modal with description text and an image
- **Modal** (`#skill-modal`) is toggled via `modal.style.display` — no CSS class toggling
- **`skillData`** object maps skill names to `{ description, image }` — descriptions mix English and Traditional Chinese

## Deployment

Pushing to the `main` branch on GitHub automatically deploys via GitHub Pages. No CI configuration needed.
