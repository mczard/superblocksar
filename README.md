# Super Blocks AR - marketing site

Small static site (plain HTML and CSS, no build step, no JavaScript, no external requests) for the Meta Quest game
"Super Blocks AR". Status: coming soon to Meta Quest 3 and 3S.

## Preview
    python3 -m http.server 8765
Open http://localhost:8765/ (English) and http://localhost:8765/pl/ (Polish).

## Layout
- `index.html`, `press.html` - English game page and press kit. `pl/index.html`, `pl/press.html` - Polish versions.
  All links are relative so the site works under `/superblocksar/`.
- `assets/style.css` - the stylesheet. `assets/fonts/` - Rajdhani Bold (woff2 subset) and its OFL licence.
- `assets/` - web-optimized images (hero art without title text, four real gameplay screenshots, favicon, `og.jpg`).
- `assets/press/` - full-size downloads for the press kit (icon, cover art, wordmark, screenshots); `assets/press/thumbs/` are the previews.
- `.nojekyll` - tells GitHub Pages to serve files as they are. `preview/` - local screenshots, git-ignored.
- Pages are edited by hand in all four HTML files; keep EN and PL in sync.

## Publishing
Published via GitHub Pages from `main` (project site, served under `/superblocksar/`). The Open Graph image uses the
absolute URL `https://mczard.github.io/superblocksar/assets/og.jpg`.

## On launch day
1. In `index.html` and `pl/index.html`, find `<!-- LAUNCH: replace the badge with the store button -->` and replace the
   `<p class="badge launch-badge">` line under it with a link button to the store page (for example
   `<a class="btn" href="STORE_URL">Get it on Meta Quest</a>`; the `.btn` class exists in `assets/style.css`). Add price or rating next to it only if wanted.
2. Update the FAQ entry "When is it out, and how much is it?" (EN and PL) with the release date and price, and the
   "coming soon" wording in the `<title>`-adjacent texts: `<meta name="description">` and `og:description` in all four pages
   (they end with "Coming soon to Meta Quest 3 and 3S"), the factsheet "Status" row in both `press.html` files.
3. Fill the Support section (`#support`) and the press factsheet "Contact" row once support details exist with the store listing.
4. Update Open Graph tags if the share text or image should change (`og:description`, `og:image`; replace `assets/og.jpg`, 1200x630).
5. Commit and push to `main`.

## Rules
No analytics, cookies or third-party requests. The only outbound links are the two privacy-policy URLs. No e-mail address on the site
until one is published with the store listing. Do not compare the game to other games or brands anywhere (text, alt text, meta tags).
