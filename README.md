# Aether Connect · paid-ads landing page

Live, seven versions for review:

- **Version 1:** https://aether-connect-landing.vercel.app (`index.html`, built from landing v05). The hero has an A/B switch in the top bar (`?hero=a` or `?hero=b`).
- **Version 2:** https://aether-connect-landing.vercel.app/v2 (`v2.html`, built from landing v06). A night-stage hero (headline, one student thinking, her questions coming up as thought bubbles one by one, the three newcomer figures), then the eligibility check as a boarding pass, then the demo video, big.
- **Version 3:** https://aether-connect-landing.vercel.app/v3 (`v3.html`, built from landing v07). The client's full-page mockup ("Your Canadian bank account. Before you land.") in version 2's design: a three-step check in the hero with the three newcomer figures taking turns under it, the worries, four steps with the demo video in a phone, the transfer, the journeys, the branch visit, the FAQ, a section for parents and the closing band.
- **Version 4:** https://aether-connect-landing.vercel.app/v4 (`v4.html`, built from landing v08). Version 3 in daylight: the hero, the transfer and the closing band on the worry cards' light (lavender top left, warm bottom right, a faint grid) instead of the night.
- **Version 5:** https://aether-connect-landing.vercel.app/v5 (`v5.html`, built from landing v10 in BMO colours). The all-persona page for students, workers and new permanent residents, after the client's rounds 3 to 5 (23 Nov). The hero: the headline, the form, and a student looking up at her worries, which come up two at a time as white thought clouds over a giant BMO-red maple leaf. The form asks for name, phone and country first, then the pathway and email, then the pathway's questions. Then six things newcomers wish they knew, one card for the three pathways, the four steps as clickable cards beside a canvas where each step plays as a small animation (they advance every 9 seconds), newcomers from the eligible countries with a ribbon of all 13 flags, what to bring to the branch, the FAQ and a section for loved ones. Parts the client set aside for now are hidden in the page, not deleted. Its Thank You page uses the same night stage, with a tick on the maple leaf.
- **Version 6:** https://aether-connect-landing.vercel.app/v6 (`v6.html`, built from the same landing v10). Version 5 in BMO's flat colours: BMO blue and BMO red as solid fills, no gradients, glows or glass, with its own hero since 23 Nov (the client's pick, "Arrivals"): on white, the words on the left (the second line in BMO blue), a tall arch photo of a student who has just landed in a bright arrivals hall under a Canadian flag, the worries floating over the arch four at a time, and the eligibility check on the right as a plain card (the same three steps). Everything below the hero is version 5's, and it has its own flat Thank You page.
- **Version 7:** https://aether-connect-landing.vercel.app/v7 (`v7.html`, built from `hero-before-you-land_v01.html`). A hero on its own, after the client's reference: "Your Canadian bank account ready before you land", three tabs (coming to study / to work / becoming a permanent resident) that each show their own person, all looking into the page, name and phone, country, and a BMO-blue button. The picked tab is remembered and sent with the form. Its Thank You page is version 6's.

Each file holds its landing page and its Thank You page (`#thank-you`), with fonts, images and scripts inlined. A successful form submit switches to the Thank You page. `vercel.json` turns on clean URLs, so `/v2` serves `v2.html`, `/v3` serves `v3.html`, `/v4` serves `v4.html`, `/v5` serves `v5.html`, `/v6` serves `v6.html` and `/v7` serves `v7.html`.

`video/` holds the 10-second demo video, shared by all the versions. It loads only once its section comes on screen.

## Updating

`index.html` and `v2.html` to `v7.html` are build outputs, so don't edit them by hand. The source is in the UMM Aether Connect project folder:

- `07_website/landing-ads_v05.html`, `landing-ads_v06.html`, `landing-ads_v07.html`, `landing-ads_v08.html` and `thank-you_v03.html` (built on `design-system_v10/`)
- rebuild each into an empty folder: `python 07_website/_tools/build_share.py landing-ads_vNN.html <folder>/index.html --with thank-you_v03.html`
- copy v05's `index.html` here as `index.html`, v06's as `v2.html`, v07's as `v3.html` and v08's as `v4.html`
- version 5 is built from the BMO copy and its own Thank You page: `python 07_website/_tools/theme_copy.py landing-ads_v10.html landing-ads_v10-bmo.html bmo thank-you_v10.html=thank-you_v10-bmo.html`, `python 07_website/_tools/theme_copy.py thank-you_v10.html thank-you_v10-bmo.html bmo landing-ads_v10.html=landing-ads_v10-bmo.html`, then `python 07_website/_tools/build_share.py landing-ads_v10-bmo.html <folder>/index.html --with thank-you_v10-bmo.html`, copied here as `v5.html`
- version 6 is the same with the theme `bmo-flat`: `python 07_website/_tools/theme_copy.py landing-ads_v10.html landing-ads_v10-bmo-flat.html bmo-flat thank-you_v10.html=thank-you_v10-bmo-flat.html`, `python 07_website/_tools/theme_copy.py thank-you_v10.html thank-you_v10-bmo-flat.html bmo-flat landing-ads_v10.html=landing-ads_v10-bmo-flat.html`, then `build_share.py landing-ads_v10-bmo-flat.html <folder>/index.html --with thank-you_v10-bmo-flat.html`, copied here as `v6.html` (the bmo-flat theme also switches on the Arrivals hero: `data-hero="arrivals"`)
- version 7: `python 07_website/_tools/build_share.py hero-before-you-land_v01.html <folder>/v7.html --with thank-you_v10-bmo-flat.html`, copied here as `v7.html`
- commit, push, then deploy:
  `npx vercel@latest deploy --prod --yes --global-config %USERPROFILE%\.vercel-umm --scope krishna-probot`

Vercel account: krishna.mehta@umm.digital (team krishna_probot, project `aether-connect-landing`).
