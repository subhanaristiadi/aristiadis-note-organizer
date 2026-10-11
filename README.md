# Aristiadi's Note Organizer

A clean, dependency-free web tool for creating, saving, editing, deleting, and categorizing notes — right in your browser. No backend, no build step, no frameworks: everything lives in a single HTML file, and your data is stored locally via `localStorage`.

🌐 **Live demo:** https://subhanaristiadi.github.io/aristiadis-note-organizer/

## Features

- **Notes** — Each note stores a **title**, **tags**, **note text**, **date created**, and **date modified**.
- **Card view** — Notes are shown as a responsive grid of cards, each with a title, truncated body, tag chips, and created/modified timestamps.
- **Create / Edit / Delete** — Add a note with the **+** button (bottom-right), edit by clicking any card, and delete via the trash icon that appears on hover (with a confirmation).
- **Tag-based filtering** — A horizontal, scrollable list of tag chips (`All` plus one per tag) to filter notes by category.
- **Full-text search** — Search matches titles, note bodies, and tags.
- **Sorting** — Toggle between *Date created* and *Date modified* (newest first).
- **Local persistence** — All data is saved to your browser's `localStorage`, so notes survive reloads on the same device.
- **First-load sample data** — The app seeds three example notes on the first visit so it isn't empty.

## Tech

- **Vanilla** HTML, CSS, and JavaScript — no external libraries or dependencies.
- Single-file app (`index.html`) with embedded styles and logic.
- **Responsive** layout: a search bar on desktop, and a tappable search icon that expands the field on mobile.

## Data model

Each note is stored as an object:

| Field        | Description                             |
| ------------ | --------------------------------------- |
| `id`         | Unique identifier                       |
| `title`      | Note title                              |
| `tags`       | Array of lowercase tag strings          |
| `text`       | Note body                               |
| `created`    | Creation timestamp (ms since epoch)     |
| `modified`   | Last-modified timestamp (ms since epoch)|

Data is kept in `localStorage` under the key `aristiadi_notes_v1`.

## Getting started

No installation or build required.

1. Clone the repository (or just use the live demo above).
2. Open `index.html` in any modern browser.

```bash
git clone https://github.com/subhanaristiadi/aristiadis-note-organizer.git
cd aristiadis-note-organizer
# open index.html in your browser, or:
python -m http.server   # optional, serve locally
```

> Notes are tied to the browser you use (per origin). Clearing your browser storage will clear your notes.

## Usage

- **Add** — Click the black **+** button in the bottom-right corner.
- **Edit** — Click any note card to open it in the editor.
- **Delete** — Hover a card and click the trash icon (confirm to delete).
- **Filter** — Click a tag chip to show only notes with that tag; click **All** to clear.
- **Search** — Type keywords in the search box to find notes by title, text, or tag.
- **Sort** — Use the sort dropdown to order by *Date created* or *Date modified*.

## Project structure

```
.
└── index.html   # The entire app: markup, styles, and logic
```

## License

Free to use, modify, and share.
