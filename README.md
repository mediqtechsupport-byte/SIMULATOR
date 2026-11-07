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

The scene selector streams short clips from their original hosts, with a Commons-hosted fallback for the Day Driving and Outdoor scenes.

- **Night Driving:** “Cars Passing by at Night” by Maximilian Schönherr, Wikimedia Commons, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). [Source](https://commons.wikimedia.org/wiki/File:Cars_Passing_by_at_Night.webm)
- **Day Driving:** “Driving at Daytime” by I Am Sorin, Pexels free-use license. [Source](https://www.pexels.com/video/driving-at-daytime-9109808/). Fallback: “ROAD VIEW” by Niyati Sharma 1505, Wikimedia Commons, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). [Source](https://commons.wikimedia.org/wiki/File:ROAD_VIEW.webm)
- **Reading:** “Close-Up Video Of Person Reading A Book” by Olia Danilevich, Pexels free-use license. [Source](https://www.pexels.com/video/close-up-video-of-person-reading-a-book-4625318/)
- **Outdoor:** “Mountain Scenery During Daytime” by Mikhail Nilov, Pexels free-use license. [Source](https://www.pexels.com/video/mountain-scenery-during-daytime-6989136/). Fallback: “Mountain Landscape near Nathu La Pass, Sikkim” by Rajani Gairshail, Wikimedia Commons, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). [Source](https://commons.wikimedia.org/wiki/File:Mountain_Landscape_near_Nathu_La_Pass,_Sikkim.webm)

The Pexels license permits use on websites and apps, does not require attribution, and prohibits redistributing stock files as standalone stock assets. The page provides creator/source links as a courtesy. The Commons fallback videos are adapted in the visual simulator and remain under CC BY-SA 4.0.

## How the condition and IOL selectors interact

- With **Select Lens** still selected, the scene illustrates the selected eye-condition preset (a simplified pre-IOL view).
- Selecting an IOL switches the view to a simplified post-IOL concept. The cataract haze is removed because cataract surgery replaces the cloudy natural lens.
- The combined astigmatism presets retain mild directional ghosting in this demo. The listed lens selections are not explicitly toric variants; real astigmatism correction depends on the measured cylinder, surgical plan, and an appropriate toric option where indicated.
- Presbyopia mainly softens the Reading scene. A distance-targeted monofocal keeps near work soft; RayOne EMV extends distance toward intermediate; trifocal offers distance/intermediate/near focal points; RayOne Galaxy is designed for a continuous range.
- Night-driving halo overlays are conceptual illustrations of possible photic effects, not expected or guaranteed patient outcomes.

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
