# Aether Connect · paid-ads landing page

Live, four versions for review:

- **Version 1:** https://aether-connect-landing.vercel.app (`index.html`, built from landing v05). The hero has an A/B switch in the top bar (`?hero=a` or `?hero=b`).
- **Version 2:** https://aether-connect-landing.vercel.app/v2 (`v2.html`, built from landing v06). A night-stage hero (headline, one student thinking, her questions coming up as thought bubbles one by one, the three newcomer figures), then the eligibility check as a boarding pass, then the demo video, big.
- **Version 3:** https://aether-connect-landing.vercel.app/v3 (`v3.html`, built from landing v07). The client's full-page mockup ("Your Canadian bank account. Before you land.") in version 2's design: a three-step check in the hero with the three newcomer figures taking turns under it, the worries, four steps with the demo video in a phone, the transfer, the journeys, the branch visit, the FAQ, a section for parents and the closing band.
- **Version 4:** https://aether-connect-landing.vercel.app/v4 (`v4.html`, built from landing v08). Version 3 in daylight: the hero, the transfer and the closing band on the worry cards' light (lavender top left, warm bottom right, a faint grid) instead of the night.

Each file holds its landing page and its Thank You page (`#thank-you`), with fonts, images and scripts inlined. A successful form submit switches to the Thank You page. `vercel.json` turns on clean URLs, so `/v2` serves `v2.html`, `/v3` serves `v3.html` and `/v4` serves `v4.html`.

`video/` holds the 10-second demo video, shared by all four versions. It loads only once its section comes on screen.

## Updating

`index.html`, `v2.html`, `v3.html` and `v4.html` are build outputs, so don't edit them by hand. The source is in the UMM Aether Connect project folder:

- `07_website/landing-ads_v05.html`, `landing-ads_v06.html`, `landing-ads_v07.html`, `landing-ads_v08.html` and `thank-you_v03.html` (built on `design-system_v10/`)
- rebuild each into an empty folder: `python 07_website/_tools/build_share.py landing-ads_vNN.html <folder>/index.html --with thank-you_v03.html`
- copy v05's `index.html` here as `index.html`, v06's as `v2.html`, v07's as `v3.html` and v08's as `v4.html`. Commit, push, then deploy:
  `npx vercel@latest deploy --prod --yes --global-config %USERPROFILE%\.vercel-umm --scope krishna-probot`

Vercel account: krishna.mehta@umm.digital (team krishna_probot, project `aether-connect-landing`).
