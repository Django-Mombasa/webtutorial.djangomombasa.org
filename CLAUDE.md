# CLAUDE.md

Notes for Claude Code when working in this repository.

## What this is

A HonKit-built Django web development tutorial published at
[webtutorial.djangomombasa.org](https://webtutorial.djangomombasa.org).
The book is multilingual — English (`en/`) and Kiswahili (`sw/`) —
registered in `LANGS.md`.

## Content layout

Each language folder contains one folder per chapter. A chapter folder
holds a `README.md` (intro + mini table of contents) and one short
Markdown file per section:

```
en/<chapter-slug>/
├── README.md
├── <section-1>.md
├── <section-2>.md
└── ...
```

Kiswahili mirrors the same layout with translated slugs (e.g.
`wavuti-na-kivinjari/`, `javascript-ya-msingi/`, `git-na-github/`).

The sidebar is driven by `en/SUMMARY.md` and `sw/SUMMARY.md`. A page
that is not listed in `SUMMARY.md` will not appear in the sidebar,
even if it builds.

## When editing content

- **Keep sections in their own files.** Do not merge multiple
  `##` sections back into a single page — the per-section layout is
  intentional so changes stay small and reviewable.
- **Mirror changes across languages.** If you add or rename a section
  in `en/`, make the matching change under `sw/` (and both
  `SUMMARY.md` files). Ask if you're unsure about a Kiswahili
  translation rather than guessing.
- **Update the chapter's `README.md` table of contents** whenever you
  add, remove, or reorder sections in that chapter.
- **Chapter `README.md` files** start with `# <Chapter Title>`, a
  short intro paragraph, then a numbered list of links to each
  section file in reading order.
- **Section files** start with `# <Section Title>` (matching the
  original `##` heading) followed by the section body.

## When adding a new chapter

1. Create `<lang>/<chapter-slug>/` with a `README.md` and one file per
   section.
2. Add the chapter to the language's `SUMMARY.md` as a top-level
   entry pointing at the chapter `README.md`, with each section
   nested (two-space indent) underneath.
3. Repeat for the other language.

## Build and preview

- `npm install` — install dependencies (HonKit + plugins).
- `npm run serve` — live-reloading preview at http://localhost:4000.
- `npm run build` — static build into `_book/` (gitignored).
- `npm run clean` — remove `_book/`.

After any structural change (new/renamed files, `SUMMARY.md` edits),
run `npm run build` to confirm HonKit still finds every page — the
final log line should read
`generation finished with success`, and the page count per language
should match the number of entries in that language's `SUMMARY.md`.

## Configuration

- `book.json` — HonKit title, description, author, plugins.
- `LANGS.md` — list of languages that make up the multilingual book.
- `.gitignore` — excludes `_book/` and `node_modules/`.

Do not commit `_book/` or `node_modules/`.
