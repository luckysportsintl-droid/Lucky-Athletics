# Lucky Athletics — GitHub-ready project

Start with **GITHUB-SETUP.md** to upload this project and connect your existing Netlify site. **COPILOT-PROMPT.md** contains a ready-to-paste task; `.github/copilot-instructions.md` provides repository guidance.

This source ZIP contains the complete editable React + TypeScript + Vite project. The ready-to-upload website is supplied in the separate **Lucky-Athletics-Deploy.zip**. Generated mockups and dist are omitted from the source ZIP to keep each download under 10 MB; `pnpm build` regenerates both automatically. Hosting remains Netlify. No account keys, paid viewer, database, server, or image-generation service is needed to run this site.

## Publish the update to your existing Netlify website

1. Extract **Lucky-Athletics-Deploy.zip**.
2. Open your existing **luckyathletics** project in Netlify, then its Deploys area.
3. Upload the extracted folder containing **index.html** as the new manual production deployment.
4. Open the website on desktop and a phone and check Collections, a design preview, color choices and the email button.

Use the existing Netlify project to retain luckyathletics.netlify.app. Uploading to a new Netlify Drop project creates a separate site. The updated code has not been deployed to your account by this handoff.

## What changed

- All 24 collections show patterns on realistic, shaded product templates.
- 24 existing designs per collection: **576 unique finished-product mockups**.
- Mobile and desktop image variants: **1,152 AVIF files** with lazy loading and responsive `srcSet`.
- Category cards use larger product photography, clear category titles, an individual tagline and an “Explore designs” action, in Lucky’s existing red/black/white styling.
- Original/color preview controls, design codes, previous/next controls and email/phone enquiry links remain available. Color choices now change the product itself.
- The “Contour” pattern’s existing canvas direction error is corrected.

See **CHANGES.md** for the file list, **ADDING-DESIGNS.md** for instructions and **VALIDATION.md** for checks and limits. Running `pnpm verify:mockups` creates product contact sheets in `review/`.

## Run and edit

Use Node.js 24 and pnpm 11.25.0, matching the existing deployment configuration:

```bash
npm install -g pnpm@11.25.0
pnpm install --frozen-lockfile
pnpm dev
```

After changing a pattern or product template:

```bash
pnpm mockups
pnpm check
pnpm verify:mockups
pnpm verify:interactions
pnpm build
pnpm preview
```

Upload the rebuilt **dist/** folder. `pnpm build` regenerates product images, prerenders the page, builds the site and removes build-only atlases from dist. Run `pnpm check` after the first build. Git deployments continue using the existing `netlify.toml` settings; the build regenerates `public/mockups/` and the cropped templates from the included source atlases.

## Why this approach fits Netlify

These are rendered 3D-style images made from realistic transparent product templates, with pattern mapping, fold displacement and fabric shading. They are not rotatable 3D models. Netlify serves the pre-rendered AVIF files as ordinary static assets. There is no Three.js/WebGL runtime in the public catalog bundle.

The gallery needs no canvas rendering. A small, separately loaded Canvas 2D module updates a selected product only when a visitor tries a different color. Each such preview uses a single small template. Original product images remain available if the color renderer cannot load.

No additional assets are required for the included catalog. For precise manufacturing silhouettes, higher-resolution output or exact panel placement, supply your own neutral transparent product photographs/templates and original artwork. Current templates are AI-generated visualizations based on the supplied reference atlases; confirm production colors, logos and panel layout in final artwork approval.
