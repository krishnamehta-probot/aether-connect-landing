# Aether Connect · paid-ads landing page

Live, two versions for review:

- **Version 1:** https://aether-connect-landing.vercel.app (`index.html`, built from landing v05). The hero has an A/B switch in the top bar (`?hero=a` or `?hero=b`).
- **Version 2:** https://aether-connect-landing.vercel.app/v2 (`v2.html`, built from landing v06). This is the glass hero with the step-by-step form.

Each file holds its landing page and its Thank You page (`#thank-you`), with fonts, images and scripts inlined. A successful form submit switches to the Thank You page. `vercel.json` turns on clean URLs, so `/v2` serves `v2.html`.

`video/` holds the 10-second demo video played in section 2, shared by both versions. It loads only once section 2 comes on screen.

## Updating

`index.html` and `v2.html` are build outputs, so don't edit them by hand. The source is in the UMM Aether Connect project folder:

- `07_website/landing-ads_v05.html`, `landing-ads_v06.html` and `thank-you_v03.html` (built on `design-system_v10/`)
- rebuild each into an empty folder: `python 07_website/_tools/build_share.py landing-ads_vNN.html <folder>/index.html --with thank-you_v03.html`
- copy v05's `index.html` here as `index.html`, and v06's as `v2.html`. Commit, push, then deploy:
  `npx vercel@latest deploy --prod --yes --global-config %USERPROFILE%\.vercel-umm --scope krishna-probot`

Vercel account: krishna.mehta@umm.digital (team krishna_probot, project `aether-connect-landing`).
