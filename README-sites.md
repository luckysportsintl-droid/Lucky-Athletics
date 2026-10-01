# Lucky Athletics — complete 3D teamwear showroom

React 19 + TypeScript + Three.js, using Vinext/Vite. **No forms, inputs, checkout, or sign-up flows.** Customers contact Lucky Athletics through telephone and email links.

## Install and run

Use Node.js 22.13+ and pnpm 11.25.0. Images and fonts are bundled. No API keys, external model services, or database are needed.

```bash
npm install -g pnpm@11.25.0
pnpm install --frozen-lockfile
pnpm dev
```

Open the printed local URL (normally http://localhost:5173). A fresh checkout automatically uses the portable execution profile; do not copy `.sites-runtime` from a managed environment.

## Validate, build, and preview

```bash
pnpm exec tsc --noEmit
node scripts/verify-content.cjs
node scripts/verify-catalog.cjs
pnpm build
pnpm start
```

The final command previews the built Cloudflare-compatible Worker locally. Public files are built into `dist/client`, and the server/configuration into `dist/server`. Keep both directories together. `verify-catalog.cjs` checks geometry without a WebGL browser; it does not claim GPU, visual, or pointer-event verification.

## Deploy

The existing Sites identity is in `.openai/hosting.json`. Reuse it for future deployments and preserve its current sharing setting.

To deploy to your own Cloudflare account after building:

```bash
pnpm exec wrangler login
pnpm exec wrangler deploy --config dist/server/wrangler.json
```

Review the generated Worker name first. No database or storage bindings are required. This is server-rendered output: `dist/client` by itself is not a complete static export.

## What is included

- The supplied custom-uniform banner at the beginning of the site, preserved in full. On phones it appears before the headline.
- Static, realistic fabric concept images for every collection and the design detail dialog. No WebGL models, spinning products, autoplay, or animation controls are mounted. Page animations and smooth scrolling are disabled.
- All 24 collections and 24 graphic patterns per collection remain available. Collection photographs are fabric/fit references; each design's separate swatch shows its actual graphic and selected colors. The image is not falsely presented as the selected pattern. Request a combined mockup by email.
- Unlimited designs, free mockups, matching existing designs, and your name, logo and sponsors with unlimited customization.
- Accessible collection tabs, design dialogs, color swatches, previous/next design selection, and direct phone/email contact.
- Clearly marked sample reviews, process, FAQs and contact details.

## Collections

Basketball; Cheer & Dance; American Football; Soccer; Lacrosse; Track & Field; Hoodies; Sublimated Jackets; Backpacks; Drawstring Bags; Duffel Bags; Tote & Kit Bags; Baseball; Softball; Volleyball; Hockey; Wrestling; Rugby; Cricket; Tennis & Pickleball; Cycling; Esports; Tracksuits; Training & Teamwear.

## Project structure and edits

- `app/page.tsx`: navigation and supporting sections.
- `app/globals.css`: responsive styling and static presentation overrides.
- `components/catalog-experience.tsx`: opening banner, collection directory, design options and dialog.
- `lib/catalog.ts`: categories, graphic patterns, colorways and contact codes.
- `lib/design-texture.ts`: design pattern swatches.
- `lib/content.ts`: contact details, FAQs and sample reviews.
- `public/images/custom-uniforms-banner.png`: user-supplied opening image.
- `public/images/catalog-1.webp` and `catalog-2.webp`: collection fabric reference sheets, four columns by three rows each; cell positions are defined in `lib/catalog.ts`.
- Earlier Three.js components and material code remain in source as unused references. They are not imported into the customer experience.

Replace sample reviews with authorized customer reviews. Replace generated collection concepts with approved product photography when available. Pattern colors change the swatch, not the collection reference image. Final mockups, fit, fabrics, pricing and timing are confirmed directly with Lucky Athletics.

## Verification

`verify-content.cjs` checks actual rendered content for no fields/forms, correct contacts, local assets, category/design coverage, service messaging, the supplied banner, and absence of animated viewer imports/controls. TypeScript and production builds are checked. Browser preview was unavailable in this environment; real-device visual QA is not claimed.
