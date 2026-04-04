# juditbekker-site — Project Reference

Astro 5 static site migrated from Wix (€170/yr) to GitHub Pages (free).
Staging: https://judkacag.github.io/juditbekker-site — DNS cutover to juditbekker.com pending (Wix still live).

---

## Commands

```bash
npm run dev      # local dev at localhost:4321
npm run build    # production build — must pass before pushing
git push         # triggers GitHub Actions deploy automatically (~1 min)
```

---

## Design System

### Colors (`src/styles/global.css`)
| Variable | Value | Use |
|---|---|---|
| `--color-bg` | `#ffffff` | page background |
| `--color-text` | `#363636` | body text |
| `--color-accent` | `#D14B64` | links, hover states |
| `--color-muted` | `#9b9b9b` | nav links, footer |
| `--color-border` | `#e8e8e8` | dividers, nav border |
| Peach gradient | `linear-gradient(180deg, rgba(250,212,189,0.75) 0%, #ffffff 100%)` | portfolio hero box, about-me page bg |
| Heading accent | `#DC9C79` | "HEY THERE" / "HELLO," display headings |

### Typography
- **Font**: Jost (Google Fonts, weights 300–700) — **not Futura** (dropped: only rendered on Judit's machine, not visitors')
- **Display headings only**: Impact for "HEY THERE" and "HELLO,"
- **Base size**: 17px (bumped from 16px — Jost reads smaller than Futura at same size)

### Layout
- Global container: `max-width: 1200px`, `padding: 0 40px`
- About Me cards: `max-width: 1050px` (narrower → more peach gradient on sides)
- Nav height: 76px

---

## Architecture

- **Base path**: `base: '/juditbekker-site/'` in `astro.config.mjs` — every internal link and image `src` must use `${base}` prefix: e.g. `` `${base}images/foo.jpg` ``
- **Social icons**: plain PNG files in `public/images/icons/` — no CSS filters (attempts to tint them caused grey boxes due to non-transparent backgrounds)
- **Blog**: Astro Content Collections, glob loader, files in `src/content/blog/`. Frontmatter fields: `title`, `date`, `draft`
- **Portfolio**: hardcoded array of 16 items in `src/pages/index.astro` (title, image path, external link, description)

---

## Pages & Key Files

| File | Purpose |
|---|---|
| `src/pages/index.astro` | Portfolio: hero + masonry grid + nav search slot |
| `src/pages/about-me.astro` | About Me: peach bg, two white cards |
| `src/pages/blog/index.astro` | Blog listing sorted newest-first |
| `src/pages/blog/[slug].astro` | Individual blog post template |
| `src/layouts/Layout.astro` | Shared nav + footer |
| `src/styles/global.css` | Design tokens + CSS reset |
| `public/images/portfolio/` | 16 portfolio project images |
| `public/images/icons/` | Social icon PNGs |

---

## Blog Editing (no terminal needed)

1. Create `src/content/blog/YYYY-MM-DD-post-title.md`:
```markdown
---
title: "Post Title"
date: "2025-06-01"
draft: false
---

Post content in markdown...
```
2. In Cursor's Source Control panel: stage → commit message → Commit & Push
3. GitHub Actions deploys in ~1 minute

---

## DNS Cutover (when ready to leave Wix)

1. Add `public/CNAME` containing: `juditbekker.com`
2. `astro.config.mjs`: set `base: '/'` and `site: 'https://juditbekker.com'`
3. Domain registrar: remove all Wix DNS records, add:
   - A records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - CNAME: `www` → `judkacag.github.io`
4. GitHub repo Settings → Pages → set custom domain `juditbekker.com` (SSL auto-provisions)
5. Cancel Wix subscription
