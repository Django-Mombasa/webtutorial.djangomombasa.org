# webtutorial.djangomombasa.org

Django Web Development Tutorial, built with [HonKit](https://honkit.netlify.app/).

## Prerequisites

- [Node.js](https://nodejs.org/) 18 or newer
- npm (bundled with Node.js)
- Git

## Setup

Clone the repository and install dependencies:

```bash
git clone https://github.com/Django-Mombasa/webtutorial.djangomombasa.org.git
cd webtutorial.djangomombasa.org
npm install
```

## Local development

Start the live-reloading preview server:

```bash
npm run serve
```

The site will be available at http://localhost:4000. Edits to Markdown files
trigger an automatic rebuild.

## Building

Generate the static site into `_book/`:

```bash
npm run build
```

To remove the build output:

```bash
npm run clean
```

## Chapter layout

The book is multilingual — each language lives in its own folder
(`en/` for English, `sw/` for Kiswahili) and is registered in
`LANGS.md`. Inside a language folder, every chapter is its own folder
with a `README.md` introduction and one short file per section:

```
en/
├── README.md               # Language landing page
├── SUMMARY.md              # Sidebar for this language
├── web-and-browser/
│   ├── README.md           # Chapter intro + mini table of contents
│   ├── what-is-the-web.md
│   ├── what-is-a-browser.md
│   ├── request-and-response.md
│   └── whats-next.md
├── html/
│   ├── README.md
│   ├── first-document.md
│   ├── tags-and-elements.md
│   └── ...
└── ...
```

This keeps each section small enough to edit or review independently.
The Kiswahili side (`sw/`) mirrors the same structure with translated
folder and file names (e.g. `wavuti-na-kivinjari/`,
`javascript-ya-msingi/`).

## Adding pages

1. Decide which chapter the page belongs to and create a new Markdown
   file inside that chapter folder, e.g.
   `en/html/forms.md`.
2. Register the page in the language's `SUMMARY.md` so HonKit includes
   it in the sidebar. Indentation controls nesting:

   ```markdown
   # Summary

   * [Introduction](README.md)
   * [HTML](html/README.md)
     * [Your first HTML document](html/first-document.md)
     * [Forms](html/forms.md)
   ```

3. If you are adding the page to both languages, mirror the change in
   the other language folder (`sw/` ↔ `en/`) and its `SUMMARY.md`.
4. Run `npm run serve` to preview the new page.

Only pages listed in `SUMMARY.md` appear in the sidebar.

## Adding a new chapter

1. Create a chapter folder inside the language directory, e.g.
   `en/django-basics/`.
2. Add a `README.md` with the chapter title, a short intro, and a
   numbered list of links to each section file.
3. Create one Markdown file per section inside the folder.
4. Add the chapter to `en/SUMMARY.md` (and its Kiswahili counterpart)
   as a top-level entry pointing at the chapter `README.md`, with
   each section nested underneath.

## Editing pages

- Pages are plain GitHub-flavored Markdown — headings, lists, links,
  fenced code blocks, and images all work out of the box.
- Link between pages using relative paths. Within a chapter folder
  you can use the bare filename, e.g. `[attributes](attributes.md)`;
  across chapters use the folder too, e.g.
  `[see forms](../html/forms.md)`.
- Place images under an `assets/` folder (create it if it does not
  exist) and reference them with `![alt](assets/diagram.png)`.
- Book-wide settings (title, author, plugins) live in `book.json`.
  The list of languages lives in `LANGS.md`.

## Project layout

```
.
├── README.md        # This file — project overview
├── LANGS.md         # Registers the available languages
├── book.json        # HonKit configuration
├── package.json     # npm scripts and dependencies
├── en/              # English book (chapters as folders)
├── sw/              # Kiswahili book (chapters as folders)
└── _book/           # Build output (gitignored)
```

## Contributing

1. Create a branch: `git checkout -b your-feature`
2. Make your changes and preview with `npm run serve`
3. Commit, push, and open a pull request

## License

See [LICENSE](LICENSE).
