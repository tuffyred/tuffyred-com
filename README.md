# Tuffyred.com

Static website for Tuffyred LLC, built locally and deployed via GitHub Pages.

## Structure

```
.
├── index.html              # Home page (tuffyred.com)
├── verbi-brutali/
│   └── index.html          # Verbi Brutali app page + Privacy / Terms (tuffyred.com/verbi-brutali)
├── assets/
│   └── images/
│       ├── tuffyred-can-logo.jpg
│       └── verbi-brutali-icon.png
├── .nojekyll               # Tell GitHub Pages to serve files as-is (no Jekyll build)
└── README.md
```

Plain static HTML/CSS. No build step, no dependencies. Each page has its own inline styles.

## Preview locally

Because the pages use root-relative-friendly relative paths, serve the folder rather than opening the files directly:

```bash
# From the project root — pick whichever you have:
python3 -m http.server 8000
#   then open http://localhost:8000

# or, with Node:
npx serve .
```

## Edit → publish workflow

1. Edit the HTML/CSS locally and preview with the command above.
2. Commit and push:
   ```bash
   git add -A
   git commit -m "Describe the change"
   git push
   ```
3. GitHub Pages redeploys automatically within a minute or two.

## Deployment (GitHub Pages)

This repo is served by GitHub Pages from the `main` branch, root folder.
Configure once under **Settings → Pages → Build and deployment → Source: Deploy from a branch → `main` / `(root)`**.

### Custom domain (tuffyred.com)

When ready to port the domain:

1. Add a file named `CNAME` in the project root containing a single line:
   ```
   tuffyred.com
   ```
2. In your DNS provider, point the domain at GitHub Pages:
   - `A` records for the apex `tuffyred.com` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` record for `www` → `<your-github-username>.github.io`
3. In **Settings → Pages**, set the custom domain to `tuffyred.com` and enable **Enforce HTTPS** once the certificate is issued.

## Notes

- The App Store / Google Play links on the Verbi Brutali page are placeholders
  (`YOUR_APP_STORE_URL`, `YOUR_GOOGLE_PLAY_URL`) — replace them with the live store URLs when available.
