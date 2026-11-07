# MEDIQ Vision Lab — Interactive Vision Simulator

A responsive static HTML website for exploring illustrative vision conditions and intraocular lens (IOL) categories. Original branding and artwork are used; Galaxy IOL / Rayner logos and proprietary media are not included.

## Features
- Four illustrative scenes: daytime city, night driving, reading/near task, and distance landscape.
- Four viewing-condition presets with adjustable effect intensity.
- Four selectable lens categories: EDOF, monofocal, multifocal, and toric.
- Side-by-side comparison using the same scene and condition.
- Responsive layout and a step-by-step “How it works” section.

## Cloudflare Pages deployment
Connect this GitHub repository to Cloudflare Pages with:
- Production branch: `main`
- Framework preset: `None` / `Other`
- Build command: leave blank
- Build output directory: `.` (repository root, where `index.html` lives)
- Root directory: leave at the repository root
- Environment variables: none

The site is a single `index.html` file with embedded CSS, SVG scenes, and JavaScript. No package install or build command is needed.

## Run locally
Open `index.html` in a modern browser, or run `python -m http.server 8000` from the repository root and open `http://localhost:8000`.

## Educational-use limitation
The visual effects are simplified front-end approximations, not clinically validated optical simulations. Do not use them for diagnosis, lens selection, patient-specific counseling, or prediction of surgical outcomes. Clinical deployment requires validated models/assets and appropriate clinical review.
