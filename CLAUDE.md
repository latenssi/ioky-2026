# CLAUDE.md

## Project

Website for Itäharjun Omakotiyhdistys ry (neighborhood association in Itäharju, Turku). Hosted at ioky.fi via GitHub Pages.

## Stack

- **Hugo** static site generator (no theme — layouts are in `layouts/`)
- **Tailwind CSS v4** via Hugo's built-in `css.TailwindCSS` pipeline (`assets/css/main.css`)
- **GitHub Actions** deploys to GitHub Pages on push to `main`
- **Nix flake** for dev shell (`flake.nix` — provides Hugo + Node.js)

## Structure

- `content/` — all pages as Markdown. This is what gets edited most often.
- `layouts/_default/baseof.html` — shared shell (header, nav, footer)
- `layouts/_default/single.html` and `list.html` — content page templates
- `layouts/index.html` — homepage with hero section
- `assets/css/main.css` — Tailwind entry point
- `static/CNAME` — custom domain config for GitHub Pages
- `hugo.toml` — site config, menus, params

## Build

```
nix develop
npm ci
hugo server        # dev
hugo --minify      # production build → public/
```

## Content notes

- All content is in Finnish. Do not translate or summarize Finnish text.
- `content/saannot.md` contains the association's legal bylaws — do not paraphrase or alter wording.
- The site has no backend, no database, no forms. Contact and membership are handled via email (hallitus@ioky.fi).
- This replaced an older Astro + Directus setup (see `latenssi/ioky-frontend-2022` on GitHub for history).
