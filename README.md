# Regreports — company / portfolio website

Static marketing site for Regreports and its flagship product, **PIMS**
(Pretreatment Information Management System). Plain HTML + [Tailwind CSS](https://tailwindcss.com).

## Pages
- `index.html` — company landing: hero, flagship product, features, portfolio, about, contact
- `pims.html` — PIMS product detail page
- `assets/` — favicon and static assets

## Preview locally
No build step — just serve the folder:

```bash
cd ~/portfolio
python3 -m http.server 8080
# open http://localhost:8080
```

(Or open `index.html` directly in a browser.)

## Tailwind

This uses the Tailwind **Play CDN** for zero-build simplicity, which is perfect
for iterating. Before going to production, swap it for a compiled stylesheet so
the page doesn't depend on a runtime CDN and ships only the classes it uses:

```bash
npx tailwindcss -i ./src/input.css -o ./assets/tailwind.css --minify
```

…then replace the `<script src="https://cdn.tailwindcss.com">` tag with
`<link rel="stylesheet" href="assets/tailwind.css">`. (Tracked as a follow-up.)

## Deploy
It's a static site — deploy the folder to any static host (Netlify, Cloudflare
Pages, GitHub Pages) or serve it behind the same Caddy setup used for the app.

## Notes
- Contact CTAs point to `hello@regreports.com` — update to the real address.
- Copy is a first draft; product claims mirror what PIMS does today.
