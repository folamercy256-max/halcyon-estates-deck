# Halcyon Estates — Presentation Site

A 14-slide interactive presentation for **Halcyon Estates**, a boutique real
estate brokerage in California (est. 2014). Built as a static, dependency-free
HTML site — no build step, no framework, no environment variables.

**Design system:** Heritage palette — Ivory `#F7F3EC` · Forest Green `#1F3D2C` · Copper `#B8763D`
**Typography:** Playfair Display (headings) + Source Sans 3 (body), served via Google Fonts

---

## Structure

```
├── index.html          # Slide player ( Prev / Next, ←/→ / Home / End keys, auto-scaling )
└── slides/
    ├── slide_01.html   # 01 · Cover
    ├── slide_02.html   # 02 · Brand story — Marlene Vasquez
    ├── slide_03.html   # 03 · Track record (11+ yrs · 480+ closings · 14-day avg · 92% referral)
    ├── slide_04.html   # 04 · Portfolio index
    ├── slide_05.html   # 05 · Southlea Residence      — $1.35M
    ├── slide_06.html   # 06 · The Design Loft        — $6,200/mo
    ├── slide_07.html   # 07 · Crown Heights Penthouse — $1.86M
    ├── slide_08.html   # 08 · Garden Cottage          — $895K
    ├── slide_09.html   # 09 · Bayview Apartment       — $4,500/mo
    ├── slide_10.html   # 10 · Halls Manor             — $1.18M
    ├── slide_11.html   # 11 · Services (2×2)
    ├── slide_12.html   # 12 · Three-step process
    ├── slide_13.html   # 13 · Client testimonials — 4.9/5
    ├── slide_14.html   # 14 · Contact
    ├── global.css      # Heritage design tokens
    └── *.jpg / *.png   # Local image assets (no hotlinking)
```

Slides are fixed 1280 × 720 canvases; the player scales them to fit any viewport.

---

## Run locally

Any static server works. From the repo root:

```bash
python3 -m http.server 3000
# then open http://localhost:3000
```

Or simply open `index.html` directly in a browser.

---

## Deploy to Vercel (zero config)

This is a pure static site — Vercel needs no framework preset, build command,
or output directory override.

1. Push this repository to GitHub (see below).
2. Go to [vercel.com/new](https://vercel.com/new) and **Import** the repository.
3. Leave all build settings at their defaults (Framework Preset: **Other**).
4. Click **Deploy** — your site is live at `https://<project-name>.vercel.app`.

Alternative — deploy from your machine with the Vercel CLI:

```bash
npm i -g vercel
vercel          # from the repo root, follow the prompts
vercel --prod   # subsequent production deployments
```

---

## Pushing to GitHub

```bash
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

When prompted, authenticate with a GitHub Personal Access Token
(classic token with `repo` scope, or a fine-grained token with
*Contents: Read and write* permission) — GitHub no longer accepts
account passwords for git pushes.
