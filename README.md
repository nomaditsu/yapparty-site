# yapparty-site

Marketing site for **YapParty** (macOS app). Static HTML/CSS with no build step, served by
GitHub Pages. Mirrors the CutParty site (`nomaditsu/cutparty-site`).

Live at <https://nomaditsu.github.io/yapparty-site/> until the `yapparty.app` domain is set up.

## Structure
- `index.html`: one-pager
- `support.html`: support page (the app links to `/support`)
- `privacy.html`: privacy policy (the app links to `/privacy`)
- `styles.css`: shared styles (Poppins, minimalist, confetti accent, YapParty grape and sky)
- `assets/`: logo, favicon, hero icon
- `assets/vendor/`: canvas-confetti 1.9.3 (ISC, license text alongside)
- `_config.yml`: keeps the repo's own docs off the published site

## Local preview
Run `python3 -m http.server` in this folder and open <http://localhost:8000>.
Opening `index.html` straight from disk also works, but the `./` home links then show a
folder listing.

## Deploy
Pushing to `main` publishes through GitHub Pages (source: `main`, folder `/`). GitHub Pages
serves `support.html` at `/support` and `privacy.html` at `/privacy`, which are the paths the
app uses.

## Custom domain (not set up yet)
When `yapparty.app` is registered:
1. Add a `CNAME` file containing `yapparty.app`.
2. Point DNS at GitHub Pages: apex `A` records to GitHub's Pages IPs and a `www` `CNAME`
   to `nomaditsu.github.io`.
3. Turn on Enforce HTTPS in the repo's Pages settings.

## Before launch
- Replace every `TODO(contact-email)` placeholder with the support address.
- Swap the "Coming soon" download button for the real download link.
- Add the Pro price once it is set.
- Replace the screenshot placeholder with real screenshots.
