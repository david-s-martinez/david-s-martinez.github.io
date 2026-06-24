![Github Forks](https://img.shields.io/github/forks/david-s-martinez/david-s-martinez.github.io?style=flat)
![Github Stars](https://img.shields.io/github/stars/david-s-martinez/david-s-martinez.github.io?style=flat)
![License](https://img.shields.io/github/license/david-s-martinez/david-s-martinez.github.io)
![Last Commit](https://img.shields.io/github/last-commit/david-s-martinez/david-s-martinez.github.io)

# David Martinez — Personal Portfolio

Personal portfolio website of **David Martinez**, AI & Robotics Engineer.

:milky_way: Live: https://david-s-martinez.github.io/

Built on the [vCard Personal Portfolio](https://github.com/codewithsadee/vcard-personal-portfolio) template — a fully responsive, single-page site using vanilla **HTML, CSS, and JavaScript**. No build step or framework is required.

## Sections

A fixed sidebar (photo, contacts, links) plus tabbed navigation:

- **About** — bio and areas of expertise
- **Resume** — education, conferences & presentations, awards, research interests
- **Portfolio** — projects with descriptions, media, and links, filterable by category
- **Contact** — location map and contact form

## Project structure

```
.
├── index.html              # The entire site (content lives here)
├── assets
│   ├── css
│   │   ├── style.css        # vCard template theme
│   │   └── custom.css       # Project-specific overrides
│   ├── js
│   │   └── script.js        # Tab navigation, portfolio filter, etc.
│   └── images               # Photos, project media, icons, favicon
└── contents                 # Original Markdown content (kept as a backup/source)
```

## Editing content

All page content is written directly in `index.html` — find the relevant
`<article data-page="...">` block (about / resume / portfolio / contact) and edit it.
To add a portfolio project, copy an existing `<li class="project-item ...">` card,
update the image/text/links, and set its `data-category` to match a filter button.
Replace images by dropping files into `assets/images/` and pointing the `src` at them.

## Run locally

Because the site uses relative asset paths and fetches nothing at build time, any
static file server works. From the project root:

```bash
# Option 1 — Python (no install needed on macOS/Linux)
# Free port 8000 first (kills any server already bound to it), then serve:
lsof -ti tcp:8000 | xargs kill -9 2>/dev/null; python3 -m http.server 8000

# Option 2 — Node
npx serve .
```

Then open **http://localhost:8000** in your browser. Edit a file and refresh to see changes.

> Opening `index.html` directly via `file://` mostly works too, but a local server
> matches how GitHub Pages serves the site and avoids browser path quirks.

## Deploy (GitHub Pages)

This repository is a GitHub **user site** (`david-s-martinez.github.io`), so GitHub
Pages serves `index.html` from the root of the default branch automatically — there
is no build pipeline. To publish changes:

```bash
git add -A
git commit -m "Update site"
git push origin main
```

The live site at https://david-s-martinez.github.io/ updates within about a minute.
(If Pages was ever disabled: repo **Settings → Pages → Build and deployment →
Source: Deploy from a branch**, branch `main`, folder `/ (root)`.)

## Credits & License

Template by [@codewithsadee](https://github.com/codewithsadee/vcard-personal-portfolio) (MIT).

Copyright David Martinez, 2024–2025. Licensed under an MIT license.
