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



## Scene video sources and licenses

The scene selector streams video from Pexels. The same source footage is used in both comparison panels so lens overlays can be compared against the same moving scene.

- **Night Driving:** “POV night drive in city, vibrant nightlife through car windshield” by Orhan Pergel. [Pexels clip](https://www.pexels.com/video/a-car-driving-through-a-city-at-night-19830439/)
- **Reading:** Main clip: “A Woman Sitting on Her Desk while Holding a Book and Her Phone” by Polina Tankilevitch, Pexels, 3 seconds, 1920×1080, 16:9. [Source](https://www.pexels.com/video/a-woman-sitting-on-her-desk-while-holding-a-book-and-her-phone-6927292/). Longer backup: “A Woman Having a Phone Call While Holding a Book” by KoolShooters, Pexels, 32 seconds, 4K. [Source](https://www.pexels.com/video/a-woman-having-a-phone-call-while-holding-a-book-8946363/). If those clips cannot load, the scene falls back to printed-page footage: “Pages of an Open Book” by Tima Miroshnichenko [source](https://www.pexels.com/video/pages-of-an-open-book-7034147/) and “Close Up Video of an Open Book” by SHVETS production [source](https://www.pexels.com/video/close-up-video-of-an-open-book-7034161/).
- **Outdoor:** “Vibrant Nightlife in Bustling Asian Street Market” by Media Dung. The listed clip is 35 seconds, 4K (3840 × 2160), 16:9 and 25 fps. [Pexels clip](https://www.pexels.com/video/vibrant-nightlife-in-bustling-asian-street-market-29192124/)

Pexels states that its photos and videos may be used for free for personal and commercial purposes under the [Pexels license](https://www.pexels.com/license/), subject to its terms and restrictions. Creator credits and source links are shown on the simulator page as a courtesy. The clips are streamed from Pexels rather than redistributed as standalone stock files.

## How the condition and IOL selectors interact

- With **Select Lens** still selected, the scene illustrates the selected eye-condition preset (a simplified pre-IOL view).
- Selecting an IOL switches the view to a simplified post-IOL concept. The cataract haze is removed because cataract surgery replaces the cloudy natural lens.
- Astigmatism uses a deliberately visible, offset duplicate edge layer. In night scenes, directional light streaks are added so the ghosting is easier to notice. The combined presbyopia + astigmatism preset shows both near blur and astigmatic ghost edges. The listed lens selections are not explicitly toric variants; real astigmatism correction depends on the measured cylinder, surgical plan, and an appropriate toric option where indicated.
- Presbyopia blur is restricted to the lower/near reading area; Night Driving and Outdoor remain clear of presbyopia blur. The near-reading overlay is strongest before IOL selection and with distance-targeted monofocal, lighter with RayOne EMV, and mostly removed for trifocal/Galaxy in this conceptual demo.
- Trifocal vs Galaxy now have visibly different night-light overlays: trifocal uses more pronounced concentric halo rings and a slight text-edge fringe on the Reading scene; Galaxy uses a smoother glow without the pronounced rings and a clean near-text preview.
- Lens and condition overlays are deliberately exaggerated teaching illustrations, not optical ray tracing or patient-specific predictions. They must not be used to compare clinical performance, counsel an individual patient, or promise spectacle independence.


- **Monofocal vs RayOne EMV in driving scenes:** both retain distance detail; the standard monofocal preset softens the nearer dashboard/intermediate region more, while RayOne EMV retains more intermediate detail to illustrate its increased range of focus.
- **Reading scene:** the distance-targeted monofocal preset is softened most; RayOne EMV is shown as an intermediate/near transition; trifocal and Galaxy presets are clearer at the near task. RayOne Galaxy is designed to provide a continuous full range of focus—distance, intermediate and near—with the aim of reducing dependence on glasses for everyday activities; this is not a guarantee of spectacle independence.
- **Night effects:** the trifocal preset uses a more visible halo illustration; Galaxy's glow is milder, in line with Rayner's description of minimized dysphotopsia. These are teaching overlays, not patient-specific optical predictions.

## Educational sources

The behavior descriptions are based on general educational descriptions from:
- [American Academy of Ophthalmology — IOL types and focusing distances](https://www.aao.org/eye-health/diseases/cataracts-iol-implants)
- [National Eye Institute — Cataracts](https://www.nei.nih.gov/eye-health-information/eye-conditions-and-diseases/cataracts)
- [National Eye Institute — Astigmatism](https://www.nei.nih.gov/eye-health-information/eye-conditions-and-diseases/astigmatism)
- [National Eye Institute — Presbyopia](https://www.nei.nih.gov/eye-health-information/eye-conditions-and-diseases/presbyopia)
- [Rayner — RayOne EMV](https://rayner.com/global/en/iol/rayone-emv/)
- [Rayner — Trifocal IOLs](https://rayner.com/global/en/iol/trifocal/)
- [Rayner — RayOne Galaxy](https://rayner.com/us/rayner-announces-fda-approval-of-galaxy-the-worlds-first-spiral-iol/)


## Night-driving video credit and reuse terms

The Night Driving scene uses the 16-second clip [“Cars Passing by at Night”](https://commons.wikimedia.org/wiki/File:Cars_Passing_by_at_Night.webm) by Maximilian Schönherr, licensed under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/). The video is streamed from Wikimedia Commons rather than copied into this repository. It is looped in the simulator and displayed with CSS-based illustrative viewing effects. The adapted presentation of this clip is shared under CC BY-SA 4.0; this attribution does not imply endorsement by the creator.

## Run locally
Open `index.html` in a modern browser, or run `python -m http.server 8000` from the repository root and open `http://localhost:8000`.

## Educational-use limitation
The visual effects are simplified front-end approximations, not clinically validated optical simulations. Do not use them for diagnosis, lens selection, patient-specific counseling, or prediction of surgical outcomes. Clinical deployment requires validated models/assets and appropriate clinical review.
