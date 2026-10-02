# Halcyon Estates — Website

The official **Halcyon Estates** site — boutique real estate in California
(est. 2014). Fully static, self-contained mirror of the live site:
no build step, no framework install, no environment variables, and **zero
external asset dependencies** (all images and fonts are local).

Also included: a 14-slide interactive presentation of the brand under
[`/deck/`](./deck/) (open `deck/index.html`).

---

## Structure

```
├── index.html            # Homepage (single page — anchor navigation)
├── robots.txt
├── _next/static/         # Site bundle: JS chunks, CSS, self-hosted fonts
├── assets/img/           # All site imagery (served locally)
└── deck/                 # Bonus: 14-slide presentation
    ├── index.html        # Slide player (Prev/Next, ←/→ keys)
    └── slides/           # 14 fixed 1280×720 slides + Heritage design system
```

Sections on the homepage: Home · About · Properties (6 listings) · Services ·
Process · Reviews · Contact (with OpenStreetMap embed).

---

## Run locally

```bash
python3 -m http.server 3000
# open http://localhost:3000
```

(Opening `index.html` via file:// also works.)

---

## Deploy to Vercel (zero config)

1. This repository is already on GitHub — go to
   [vercel.com/new](https://vercel.com/new) and **Import** it.
2. Leave all build settings at their defaults (Framework Preset: **Other** —
   no build command, no output directory override).
3. Click **Deploy** → live at `https://<project-name>.vercel.app`.

Or from your machine:

```bash
npm i -g vercel
vercel          # from the repo root
vercel --prod
```

---

## Notes

- The site was captured as a production static export: HTML + `/_next`
  bundles are served exactly as the original host serves them.
- Formerly hotlinked images (templatekit.jegtheme.com) were downloaded and
  rewritten to `/assets/img/` — the site no longer depends on any third-party host.
- The contact form and OpenStreetMap embed work as on the original site.
