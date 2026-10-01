# yapparty-site

Marketing site for **YapParty** (macOS app), a CutParty sub product. Static HTML/CSS with no
build step. Mirrors the CutParty site (`nomaditsu/cutparty-site`).

Live at <https://cutparty.com/yapparty/>. This repo is the source. `nomaditsu/cutparty-site`
mounts it as a git submodule at `yapparty/`, and GitHub Pages serves it from there.

## Structure
- `index.html`: one-pager
- `support.html`: support page (the app links to `/support`)
- `privacy.html`: privacy policy (the app links to `/privacy`)
- `styles.css`: shared styles (Poppins, minimalist, confetti accent, YapParty grape and sky)
- `assets/`: logo, favicon, hero icon
- `assets/vendor/`: canvas-confetti 1.9.3 (ISC, license text alongside)
- `_config.yml`: only used if this repo is ever served on its own. On cutparty.com, the
  `cutparty-site` root `_config.yml` keeps this repo's docs off the site

## Local preview
Run `python3 -m http.server` in this folder and open <http://localhost:8000>.
Opening `index.html` straight from disk also works, but the `./` home links then show a
folder listing. Keep every link relative: the site lives under `/yapparty/`.

## Deploy
1. Merge the change into `main` here.
2. In a `cutparty-site` worktree or branch:
   `git submodule update --remote yapparty`, then commit the new pointer and merge it.
3. GitHub Pages rebuilds `cutparty.com`. Check `https://cutparty.com/yapparty/`.

GitHub Pages is off for this repo on purpose, so there is no duplicate copy on github.io.
Pages serves `support.html` at `/yapparty/support` and `privacy.html` at `/yapparty/privacy`.
Why it is set up this way: `docs/decisions/0001-host-at-cutparty-com-yapparty.md`.

## Before launch
- Replace every `TODO(contact-email)` placeholder with the support address.
- Point the app's `AppLinks` at `cutparty.com/yapparty` (they still say `yapparty.app`).
- Swap the "Coming soon" download button for the real download link.
- Add the Pro price once it is set.
- Replace the screenshot placeholder with real screenshots.
