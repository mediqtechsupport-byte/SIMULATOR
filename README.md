# MEDIQ Vision Lab — Interactive Vision Simulator

A responsive, static website inspired by the interaction pattern of a scene-based vision/IOL simulator. It uses original copy, styling, and hand-authored SVG illustrations. It does not use the Galaxy IOL / Rayner logo, brand assets, or proprietary simulator media.

## Features

- Four scenes: daytime city, night driving, reading/near task, and distance landscape.
- Four illustrative viewing conditions: clear baseline, cataract-like haze, astigmatism-like ghosting, and near-vision difficulty.
- Four selectable IOL categories: extended depth of focus, monofocal, multifocal, and toric.
- Adjustable effect intensity for non-baseline conditions.
- Side-by-side comparison using the same scene and condition.
- Responsive layout and keyboard-accessible form controls.
- Educational disclaimer explaining the limits of the simplified visual effects.

## Run locally

No build step or package installation is required. Open `index.html` in a modern browser, or run a local server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Deploy to Vercel

This is a static site; no framework, build command, or install command is required.

1. Import `https://github.com/mediqtechsupport-byte/SIMULATOR` into Vercel.
2. Set the Root Directory to the repository root (`./`).
3. Set Framework Preset to Other.
4. Leave Build Command and Install Command empty.
5. Set Output Directory to `.` if Vercel asks for one.
6. Deploy. Future commits to `main` will trigger new deployments when the Git integration is enabled.

The included `vercel.json` enables clean URLs and disables trailing slashes. The project is served directly from the repository root.

## Important scope note

The vision effects are front-end visual approximations created with CSS filters and SVG artwork. They are not validated optical simulations and must not be used for diagnosis, lens selection, patient-specific counseling, or prediction of surgical outcomes. Replace these simplified effects with clinically validated visual assets/models and obtain appropriate clinical review before using the tool in patient education.
