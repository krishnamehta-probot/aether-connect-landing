# Aether Connect · paid-ads landing page

Live: https://aether-connect-landing.vercel.app

`index.html` is the whole site in one self-contained file: the landing page and its Thank You page (`#thank-you`), with fonts, images and scripts inlined. A successful form submit switches to the Thank You page.

## Updating

`index.html` is a build output, so don't edit it by hand. The source is in the UMM Aether Connect project folder:

- `07_website/landing-ads_vNN.html` and `thank-you_vNN.html` (built on `design-system_vNN/`)
- rebuild with `python 07_website/_tools/build_share.py landing-ads_vNN.html landing-ads_final.html --with thank-you_vNN.html`
- copy the result over `index.html`, commit, push, then deploy:
  `npx vercel@latest deploy --prod --yes --global-config %USERPROFILE%\.vercel-umm --scope krishna-probot`

Vercel account: krishna.mehta@umm.digital (team krishna_probot, project `aether-connect-landing`).
