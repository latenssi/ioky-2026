# ioky.fi — Itäharjun Omakotiyhdistys

Website for Itäharjun Omakotiyhdistys ry, built with [Hugo](https://gohugo.io/) and hosted on GitHub Pages.

## Updating content

All pages live in `content/` as Markdown files. Edit them directly and push to `main` — GitHub Actions will build and deploy automatically.

| File | Page |
|------|------|
| `content/_index.md` | Etusivu |
| `content/jaseneksi.md` | Jäseneksi |
| `content/saannot.md` | Säännöt |
| `content/tapahtumat.md` | Tapahtumat |
| `content/vuosikokoukset.md` | Vuosikokoukset |
| `content/usein-kysyttya.md` | Usein kysyttyä |
| `content/yhteydenotto.md` | Yhteydenotto |

Markdown basics: `## Heading`, `**bold**`, `[link text](url)`, `- list item`.

## Local development

Requires Hugo and Node.js. With Nix:

```
nix develop
npm ci
hugo server
```

Site is served at http://localhost:1313 with live reload.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml` which builds the site and deploys to GitHub Pages. The custom domain `ioky.fi` is configured via `static/CNAME`.

### DNS

Point `ioky.fi` to GitHub Pages:

- **A records** to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- Or **CNAME** `ioky.fi` → `<username>.github.io`

Then enable GitHub Pages in repo Settings → Pages → Source: GitHub Actions.
