# Manuals

Online documentation for Bruker EPR instrumentation, built with [Hugo](https://gohugo.io/) and the [Docsy](https://www.docsy.dev/) theme.

Published at: **https://spinlaboratory.github.io/manuals/**

---

## Prerequisites

| Tool | Version | Notes |
|------|---------|-------|
| [Hugo Extended](https://gohugo.io/installation/) | ≥ 0.157.0 | Extended variant required for SCSS |
| [Go](https://go.dev/dl/) | ≥ 1.21 | Required for Hugo module downloads |
| [Node.js / npm](https://nodejs.org/) | any LTS | Required for production builds only |

### Install PostCSS (production builds only)

```bash
npm install -g postcss postcss-cli autoprefixer
```

> The local dev server does not require PostCSS. It is only needed when running `hugo` (non-server) to build the static site for deployment.

---

## Getting started

### Clone the repository

```bash
git clone https://github.com/spinlaboratory/manuals.git
cd manuals
```

### Start the development server

```bash
hugo server
```

The site will be available at `http://localhost:1313/manuals/`.

Hugo watches for file changes and reloads the browser automatically.

---

## Project structure

```
manuals/
├── content/en/          # All page content (Markdown / HTML)
│   ├── _index.html      # Landing page
│   ├── probes/          # Probe head manuals (QLP, etc.)
│   └── resources/       # Reference tables and standard samples
├── static/
│   ├── images/          # All images referenced in content
│   └── downloads/       # Downloadable files (PDFs, etc.)
├── assets/scss/         # SCSS overrides (_styles_project.scss)
├── layouts/             # Hugo template overrides (Docsy customizations)
│   ├── _default/_markup/render-link.html   # Opens external links in new tab
│   └── _partials/head-css.html             # CSS pipeline override
├── hugo.toml            # Hugo configuration
└── go.mod               # Hugo module dependencies
```

---

## Branching and deployment

| Branch | Purpose |
|--------|---------|
| `develop` | Active development — edit content here |
| `main` | Production — merged from `develop` with `--no-ff` |

Changes pushed to `main` are deployed automatically to GitHub Pages via the repository's CI workflow.

**Always merge with `--no-ff`** to preserve branch history:

```bash
git checkout main
git merge --no-ff develop
git push origin main
```

---

## Content authoring

- Pages live under `content/en/`. Each section has an `_index.md` that controls the section title, weight, and draft status.
- Set `draft: True` in a page's front matter to hide it from the published site.
- Images must be placed under `static/images/` and referenced as `/manuals/images/...` in shortcodes.
- The `figure_manuals` shortcode is used for all figures — it passes the `src` attribute through as-is, so the `/manuals/` prefix must be included.

---

## Contact

EPR Applications Team — epr-applications@bruker.com
