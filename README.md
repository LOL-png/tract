# TrAct — Project Page

Static project page for *TrAct: Bridging Robot Control and Visual Prediction with Visual Tracks*.
Built on the [Nerfies](https://nerfies.github.io) academic project page template (CC BY-SA 4.0).

## Layout

```
index.html                 the whole page — edit this
static/css/index.css       styling on top of Bulma
static/images/             web-sized JPEGs (downscaled from ../img)
static/pdfs/               drop the compiled paper here
```

Bulma, Font Awesome, Academicons, and Google Fonts load from CDNs, so there is
nothing to install and no build step.

## Local preview

```bash
python -m http.server 8000
# open http://localhost:8000
```

## Before publishing

Search `index.html` for `TODO` — there are three placeholder links:

1. **arXiv** — replace `#` with the abs URL once the preprint is posted.
2. **Paper** — put the compiled PDF in `static/pdfs/` and point the link at it.
3. **Code** — repository URL.

Also update the BibTeX block at the bottom with the real arXiv identifier.

## Deploying to GitHub Pages

```bash
git init
git add .
git commit -m "Add project page"
git branch -M main
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

Then in the repository: **Settings → Pages → Source: Deploy from a branch →
`main` / `/ (root)`**. The site appears at `https://<user>.github.io/<repo>/`.

For a user/organization site instead, name the repository
`<user>.github.io` and it will serve at the root domain.

`.nojekyll` is included so GitHub Pages serves the files as-is rather than
running them through Jekyll.

## Regenerating the images

`static/images/` was produced from `../img/` at 1600px wide (1400px for the
carousel frames), JPEG quality 86 — 18 MB of PNGs down to 1.5 MB. If the source
figures change, re-run the resize with Pillow rather than committing the
full-size PNGs; GitHub Pages has a 1 GB repository limit and large binaries make
the clone slow for everyone.

## Notes

Real-world and simulation rollout MP4s live in `static/videos/` (dual-view agent +
wrist with the predicted track overlay). The Real-World / Simulation
Rollouts sections in `index.html` reference them via
`<video autoplay muted loop playsinline>`.
