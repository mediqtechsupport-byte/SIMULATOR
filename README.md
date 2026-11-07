# MEDIQ Vision Lab — Interactive Vision Simulator

A responsive static website for exploring illustrative eye-condition and intraocular lens (IOL) scenarios. It uses original styling, copy, and hand-authored SVG scenes. It does not use Galaxy IOL / Rayner branding, logos, or proprietary media.

## What it includes

- Four scenes: daytime city, night driving, reading/near task, and distance landscape.
- Four illustrative viewing conditions: clear baseline, cataract-like haze, astigmatism-like blur, and near-vision difficulty.
- Four selectable IOL categories: extended depth of focus, monofocal, multifocal, and toric.
- Adjustable effect intensity.
- Side-by-side lens comparison using the same scene and condition.
- Responsive layout and keyboard-accessible controls.

## Project files

The web app source is stored in `site.tar.gz` at the repository root. It contains `index.html`, `styles.css`, `app.js`, and `.nojekyll`.

## Run locally

Extract the archive into a folder, then open `index.html` in a modern browser. Alternatively, run a local static server from the extracted folder:

```bash
python -m http.server 8000
```

Open `http://localhost:8000`.

## Deploy with Cloudflare Pages

Connect this GitHub repository to Cloudflare Pages and use these settings:

- **Production branch:** `main`
- **Framework preset:** `None` / `Other`
- **Build command:** `mkdir -p dist && tar -xzf site.tar.gz -C dist`
- **Build output directory:** `dist`
- **Root directory:** `/`
- **Environment variables:** none required

The build step extracts the static site into Cloudflare Pages' publish directory. Each push to `main` can then trigger a new deployment.

## Educational-use limitation

The visual effects are simplified front-end approximations created with CSS and SVG artwork. They are not clinically validated optical simulations and must not be used for diagnosis, lens selection, patient-specific counseling, or prediction of surgical outcomes. Obtain appropriate clinical review and use validated models and assets before any clinical deployment.
