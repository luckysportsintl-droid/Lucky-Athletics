# GitHub setup

1. Extract this ZIP. Open the Lucky-Athletics-GitHub folder.
2. Create a GitHub repository named lucky-athletics (or use your existing project repository).
3. Add the extracted folder contents to that repository. package.json and netlify.toml must be at the repository root, not inside an extra folder. Upload the files, not the ZIP. Include .github and .gitignore when uploading through a browser.
4. In GitHub Copilot, select this repository and use the prompt from COPILOT-PROMPT.md. Agent availability depends on your account.
5. To retain luckyathletics.netlify.app, link the repository to the EXISTING luckyathletics project in Netlify. Use pnpm run build and publish dist; netlify.toml already records these settings. Review the deployment before treating the live site as updated.

For Git users, after creating an empty remote repository, run these commands from the extracted project folder:

```bash
git init -b main
git add .
git commit -m "Add Lucky Athletics product mockup catalog"
git remote add origin <YOUR_REPOSITORY_URL>
git push -u origin main
```

Replace the URL placeholder with your actual repository URL. If working in an existing Git checkout, use its existing remote and history instead of initializing again.

## Local preview

Use Node.js 24:

```bash
npm install -g pnpm@11.25.0
pnpm install --frozen-lockfile
pnpm build
pnpm check
pnpm verify:mockups
pnpm verify:interactions
pnpm preview
```

Generated mockups and dist are deliberately excluded from this source package and Git tracking. The included PNG masters and build scripts regenerate them. No extra image-generation service or 3D hosting service is required.

This package is ready to upload; it has not created a remote GitHub repository or published a Netlify deployment.
