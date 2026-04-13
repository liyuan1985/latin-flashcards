# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static, single-page Latin flashcard web app for kids. No build step, no dependencies — open `index.html` directly in a browser.

## Running the App

Open `index.html` directly in a browser, **or** serve locally to avoid `fetch()` restrictions on `file://` URLs:

```bash
python -m http.server 8080
# then visit http://localhost:8080
```

## Architecture

- **`index.html`** — the entire application (HTML + CSS + JS in one file). Fetches `vocabulary.json` on load, picks a random card, and manages all state in plain JS variables.
- **`vocabulary.json`** — the word list. Each entry: `{ "latin": "...", "english": "..." }`. Add new vocabulary checklists here.
- **`vocabulary_pic/`** — original photos of vocabulary checklist pages (source material, not served by the app).

## Adding More Vocabulary

Append entries to `vocabulary.json`. The app loads the full array and picks randomly from all entries, so no code changes are needed.

## Deployment

The app is hosted via GitHub Pages at `https://liyuan1985.github.io/latin-flashcards/`. Pushing to `master` updates the live site.
