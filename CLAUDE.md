# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static personal portfolio website hosted on GitHub Pages. It is a single-page HTML site with no build pipeline or package manager — all dependencies (Bootstrap, jQuery, plugins) are vendored as static files in `css/`, `js/`, and `fonts/`.

## Local Development

The project uses **Prepros** for local development (port 7882 with live reload). There is no `npm`, `yarn`, or `bundle` setup. To preview locally without Prepros, open `index.html` directly in a browser or use any static file server:

```bash
python3 -m http.server 8080
```

## Deployment

Pushing to `master` automatically deploys via GitHub Pages. The `_config.yml` applies the `jekyll-theme-cayman` theme, but the main `index.html` overrides it entirely with custom markup.

## Architecture

- **`index.html`** — the entire site. All content (hero, nav, footer) is here.
- **`css/style.css`** — all custom styles (89KB compiled CSS; no source SCSS files exist in the repo).
- **`js/theme.js`** — custom theme logic (parallax, gallery, nav behavior).
- **`js/contact.js`** + **`js/mail-script.js`** — contact form handling via AjaxChimp (Mailchimp integration).
- **`static/RahulCV.pdf`** — downloadable CV linked from the "Get CV" button.

## Key Points

- No test framework exists.
- The `azure-pipelines.yml` is a placeholder with no real build steps.
- SCSS source files do not exist in the repo; only the compiled `css/style.css` is present.
- All JS libraries are bundled locally — no CDN dependencies.
