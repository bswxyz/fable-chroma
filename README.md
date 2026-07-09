# Creative studio template — raymarched liquid chrome

**Live demo → https://bswxyz.github.io/formwork-chroma/** · [How it was built](https://bswxyz.github.io/formwork-chroma/guide/)

> An iridescent liquid-metal blob raymarched live in a fragment shader — no models, no textures, just math.

A free, MIT-licensed website template. Good for: **creative studios, motion designers, anyone who wants a jaw-drop hero**.
The demo brand ("CHROMA") is fictional — every word and colour is meant to be replaced with yours.

## The signature technique

- Signed-distance-field raymarching with smooth-min metaball fusion
- Procedural iridescent environment + Fresnel rim — chrome without an HDRI
- One metaball follows the cursor, so visitors stir the metal

## Use this as your own site

This repo is a **template** — everything is plain HTML/CSS/JS with **relative paths**, so it
works under *any* repo name with zero configuration.

1. Click **Use this template → Create a new repository** (top of this page).
   **Name it whatever you like** — `my-site`, `portfolio`, anything.
2. In your new repo: **Settings → Pages → Build and deployment → Deploy from a branch**,
   then pick `main` / `/ (root)` and save. (CLI: see below.)
3. Wait ~1 minute. Your site is live at `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`.

<details>
<summary>Prefer the command line?</summary>

```bash
gh repo create my-site --template bswxyz/formwork-chroma --public --clone
cd my-site
gh api --method POST /repos/YOUR-USERNAME/my-site/pages \
  -f 'source[branch]=main' -f 'source[path]=/'
```
</details>

No build step, no dependencies to install — edit the files, push, done.
The only external requests are Google Fonts and (where used) pinned CDN copies of GSAP/three.js.

## Customize it

- Blob layout: edit the sphere centres/radii in `map()` in `main.js`; `smin` k-values control melt
- Iridescence: the `env()` function's cosine palette sets the rainbow banding
- Type: Syne + Space Grotesk via `:root` / Google Fonts — swap freely

The `/guide/` page documents the signature technique in depth (with code) — keep it, rewrite it,
or delete the folder entirely.

## Files

```
index.html        the page
styles.css        all styling (design tokens in :root at the top)
main.js           the signature effect + motion
guide/index.html  how-it-works write-up (optional — yours to keep or delete)
```

## Built-in quality

- Works with JS disabled or a CDN failure (content is never permanently hidden)
- Respects `prefers-reduced-motion`; keyboard focus styles throughout
- Canvas/WebGL feature-detected with graceful fallbacks; devicePixelRatio capped for performance
- Responsive at phone / tablet / desktop widths

## License & credit

[MIT](LICENSE) — free for personal and commercial use, no attribution required
(a link back is always appreciated). Part of **FORMWORK** — a collection of
25 free website templates: **[the full gallery →](https://bswxyz.github.io/formwork/)**
