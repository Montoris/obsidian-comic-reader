# Obsidian Comic Reader — Website

Static pages that satisfy the two URLs App Store Connect requires (Privacy Policy and Support), plus a public copy of the sample comic for the App Review notes.

## Files

- `index.html` — landing page (app overview, branding)
- `privacy.html` — **Privacy Policy** (use this URL in App Store Connect › App Privacy)
- `support.html` — **Support page** (use this URL in App Store Connect › Version › Support URL)
- `sample-comic.cbz` — public-domain-safe test file; link it in the App Review notes
- (fonts are loaded from Google Fonts; everything else is self-contained, no build step)

## Hosting on GitHub Pages (free, ~5 minutes)

1. Create a new GitHub repo, e.g. `obsidian-comic-reader-site`.
2. Upload the contents of this `website/` folder to the repo root (so `index.html` is at the top level).
3. Repo › Settings › Pages › Build and deployment › Source: **Deploy from a branch** › Branch: `main` / root › Save.
4. Wait ~1 minute. GitHub shows the published URL, typically:
   `https://<your-username>.github.io/obsidian-comic-reader-site/`

### URLs to paste into App Store Connect

Replace `<base>` with your published base URL from step 4:

- Privacy Policy URL: `<base>/privacy.html`
- Support URL: `<base>/support.html`
- Sample file (App Review notes): `<base>/sample-comic.cbz`

## Hosting anywhere else

Any static host works (Netlify, Cloudflare Pages, an S3 bucket, your own web server). Just upload the four files together and use the same three paths. Apple requires the Privacy Policy and Support URLs to be reachable over **HTTPS**, which all of the above provide by default.

## Customising

- Colours and fonts live in the `<style>` block at the top of each page (the `:root` variables match the app: magma `#F05A1E`, molten gold `#F7A626`, obsidian black `#0B0B0E`).
- The logo is an inline SVG in `index.html`; the nav badge is a small CSS circle.
- Contact email is `nick.rackham@gmail.com` throughout; change it in all three files if needed.
