# Changed files

| File/path | Change |
| --- | --- |
| `components/catalog-experience.tsx` | New product-focused category cards; actual patterned product previews; product color changes; stable design IDs and array-based previous/next navigation. Existing tabs, dialog and contact links retained. |
| `components/mockup-image.tsx` | New responsive, lazy-loaded images and on-demand Canvas 2D color preview with loading/error status and original-image fallback. |
| `app/globals.css` | Scoped collection/gallery/card/modal styles, responsive layouts, keyboard focus and reduced-motion handling. |
| `lib/mockup-renderer.ts` | Shared offline/browser template mapping, fabric shading, alpha cleanup, panel mapping and fold displacement. |
| `lib/mockup-paths.ts` | Central generated asset paths. |
| `lib/catalog.ts` | Optional artwork-file field and cycling palettes for additional designs. Original category/design IDs retained. |
| `lib/design-texture.ts` | Fixed inward-facing curves in the Contour layout. |
| `scripts/render-mockups.cjs` | Regenerates all category templates and 1,152 responsive AVIF product images without a browser/API key. |
| `scripts/verify-mockups.cjs` | Checks complete coverage, distinct previews, color changes and generates visual contact sheets. |
| `scripts/verify-interactions.cjs` | DOM tests for categories, modal navigation, palette enquiry, closing, focus restoration and bag filtering. |
| `scripts/verify-content.cjs` | Product asset coverage and responsive-image checks; allows adding more design entries. |
| `package.json`, `pnpm-lock.yaml` | Build-time Canvas package, DOM test package and mockup/test commands. |
| `public/templates/` | Two generated neutral source atlases and 24 derived category templates. |
| `public/mockups/` | 576 finished product previews in two sizes. |
| `index.html`, `dist/` | Regenerated prerendered page and complete production build. |
| `README.md`, `ADDING-DESIGNS.md`, `CHANGES.md`, `VALIDATION.md`, `TEMPLATE-PROMPTS.md`, `review/` | Updated handoff, maintenance and review material. |

The React/TypeScript/Vite stack, Netlify configuration, phone/email addresses, opening banner, other landing sections, category IDs and catalog design IDs are retained from the uploaded ZIP. The public live site used some different design names; this update follows the supplied editable source as requested. The old unused Three.js source remains available but is not imported into the public catalog.
