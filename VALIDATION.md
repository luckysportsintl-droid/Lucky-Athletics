# Validation and limits

Passed:

- `pnpm check`: TypeScript, contact links, anchor navigation, all 24 collections, current design names, responsive images and generated-file coverage.
- `pnpm verify:mockups`: all 1,152 image files exist; all 24 designs in each category have distinct hashes; changing color changes rendered product pixels.
- `pnpm verify:interactions`: 24 category switches, category-specific product paths, design dialog open/close, previous/next wraparound, selected color included in enquiry, original-color reset, focus restoration and Bags filter.
- `pnpm build`: static prerender and Vite production build.
- Visual inspection of the 24-category render contact sheet and red/blue color preview. Removed disconnected atlas residue and corrected the Contour pattern direction.

Performance design:

- All gallery products are pre-rendered AVIF images with lazy loading, dimensions and `srcSet`.
- Generated product images total the measured size recorded in the compact package report across the entire catalog; they are not all fetched at once.
- Color renderer is a separate ~6.8 kB JavaScript chunk (~2.9 kB gzip), loaded only when trying a color.
- No WebGL contexts, interactive 3D geometry or animation loop in the public catalog.

Limits:

- Browser access to the local development URL was blocked in this environment. DOM integration tests and product render inspection passed, but full rendered-page desktop/mobile visual QA and real-device performance measurements are not claimed.
- No change has been published to the user's Netlify account. Use the included `dist/` folder for deployment to the existing project.
- Mockups use front-view generated templates and approximate print placement. These are visualizations, not manufacturing artwork or a rotatable 3D viewer. Final colors, cut, logos and panel registration need the usual artwork approval.
