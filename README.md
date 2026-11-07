# MEDIQ Vision Lab — Interactive Vision Simulator

A responsive static HTML website for exploring illustrative vision conditions and intraocular lens (IOL) categories. Original branding and artwork are used; Galaxy IOL / Rayner logos and proprietary media are not included.

## Features
- Four illustrative scenes: daytime city, night driving, reading/near task, and distance landscape.
- Four viewing-condition presets with adjustable effect intensity.
- Four selectable lens categories: EDOF, monofocal, multifocal, and toric.
- Side-by-side comparison using the same scene and condition.
- Responsive layout and a step-by-step “How it works” section.

## Cloudflare Workers deployment (existing Worker)

The repository is configured for the existing Cloudflare Worker named `simulator` using `wrangler.jsonc`. The website is served from `public/index.html` as a static asset. No framework or build step is required.

To enable automatic deployments:
1. In Cloudflare, open **Workers & Pages** and select the existing Worker named `simulator`.
2. Open **Settings → Builds** and select **Connect**.
3. Connect GitHub and select `mediqtechsupport-byte/SIMULATOR`.
4. Select branch `main`.
5. Leave the build command blank. Use the default deploy command (`npx wrangler deploy`).
6. Save the configuration. A new push to `main` should trigger a Worker build and deployment.

The Wrangler configuration's `name` must match the existing Worker name `simulator`.

## Run locally
Open `index.html` in a modern browser, or run `python -m http.server 8000` from the repository root and open `http://localhost:8000`.

## Educational-use limitation
The visual effects are simplified front-end approximations, not clinically validated optical simulations. Do not use them for diagnosis, lens selection, patient-specific counseling, or prediction of surgical outcomes. Clinical deployment requires validated models/assets and appropriate clinical review.
