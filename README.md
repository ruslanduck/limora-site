# Limora — marketing site

Static site. No build step: the pages are plain HTML and deploy as-is.

| File | Purpose |
|---|---|
| `index.html` | The site |
| `privacy-policy.html` · `cookie-policy.html` · `terms-of-service.html` | Linked from the footer — all four must be published together |
| `.nojekyll` | Tells GitHub Pages to serve the files verbatim instead of running them through Jekyll |

## Publishing

GitHub Pages, from the `main` branch, root folder.
The custom domain is set in **Settings → Pages → Custom domain**, which writes a
`CNAME` file into the repo automatically — do not hand-edit that file.

## Note on assets

Images are embedded as base64 data URIs, so `index.html` is a single ~860 KB file.
That keeps deployment to one artefact, at the cost of images not being cacheable
separately from the markup. If page weight becomes a concern, split the data URIs
out into `/assets` and reference them by path.
