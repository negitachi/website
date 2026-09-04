# Repository Guidelines

## Project Structure & Module Organization

This repository is a static website served directly from the repository root.

- `index.html` is the main French-language site and contains most page markup and inline JavaScript.
- `css/band.css` holds shared presentation styles.
- `images/` and `videos/` contain site media; reuse existing assets where practical and optimize new files before committing.
- `_newsletters/` archives unpublished newsletter HTML; `images/newsletters/` contains publicly served email media.
- `fdlm/` contains the Fête de la Musique index and individual song pages.
- `concertS13/`, `don/`, and `plusdinfos/` are standalone sections with their own `index.html` entry points.
- Root-level `concert*.html` files are small concert-specific or redirect pages. `CNAME` configures the custom GitHub Pages domain.

Use relative URLs so pages continue to work both locally and on GitHub Pages. Preserve French accents and the existing UTF-8 encoding.

In newsletters, use full `https://www.negitachi.fr/images/newsletters/...` image URLs. Never store subscriber data or secrets in `_newsletters/`; files remain visible on GitHub.

## Build, Test, and Development Commands

There is no package manager, compilation step, or generated output. From the repository root, run:

```sh
python3 -m http.server 8000
```

Then open `http://localhost:8000/`. A local server is preferred to opening files directly because it more closely matches GitHub Pages URL and asset behavior.

Useful checks include:

```sh
git diff --check
git status --short
```

The first detects whitespace errors; the second confirms the intended files are included.

## Coding Style & Naming Conventions

Match surrounding HTML, CSS, and JavaScript rather than reformatting unrelated code. Use two-space indentation, lowercase HTML elements, double-quoted attributes, and semicolons in JavaScript. Keep reusable styling in `css/band.css`; reserve inline styles for page-specific overrides already colocated with a page. Prefer descriptive kebab-case asset names, while retaining established historical names when replacing referenced files.

## Testing Guidelines

No automated tests or coverage thresholds are configured. Manually verify changed pages at desktop and mobile widths. Check navigation anchors, external embeds, images, videos, redirects, and browser-console errors. When editing shared CSS or scripts, spot-check the home page and affected standalone sections.

## Commit & Pull Request Guidelines

Recent history favors short, imperative summaries such as `update banner`, `fix vidéo YT`, and `concert S16`. Keep each commit focused and describe the visible outcome. Pull requests should summarize affected pages, list manual checks, link any related issue, and include before/after screenshots for visual changes. Do not commit editor files, secrets, or unrelated media.
