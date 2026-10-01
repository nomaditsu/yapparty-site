# yapparty.app: project brief

Loaded by every AI coding agent after Ray's global constitution
(`~/dev/clarvis/constitution/AGENTS.md`). If your tool did not load that file on its own,
read it now, before anything else. This file adds what is specific to this repo.
`CLAUDE.md` is one line that imports this file, so there is a single source.

## Project
yapparty.app (no project code of its own; it is the site for YapParty, code **TOKEE**) is the
public marketing site for YapParty, a macOS voice chat app: a one-pager, a support page and a
privacy policy. Static HTML/CSS with no build step. Source is the public repo
`nomaditsu/yapparty-site`; it is served at `https://cutparty.com/yapparty/` because
`nomaditsu/cutparty-site` mounts it as a submodule at `yapparty/` (decision 0001).
Status: active, pre-launch (the app is not on sale yet).

## Lineage and related work
<!-- clarvis:lineage:start (generated from ~/dev/clarvis/registry/projects.yaml by `clarvis index`, do not hand-edit) -->
Family: voice. Local voice chat with on-device speech

- `~/dev/tokee` (site-for): YapParty (code TOKEE), the macOS app this site sells
- `~/dev/cutparty-site` (sibling): same static structure, tone and components, mirrored from it
- `~/dev/tokee` (Tokee) lists this repo as site-for: yapparty.app marketing site

Full portfolio map: `~/dev/PROJECTS.md`.
<!-- clarvis:lineage:end -->

Before designing anything new, check the entries above. An earlier prototype or a sibling
repo may already hold the component, the research, or the reason an approach was dropped.

## Layout
- `index.html`: the one-pager
- `support.html`, `privacy.html`: doc pages, live at `/yapparty/support` and `/yapparty/privacy`
- `styles.css`: all styles, forked from cutparty-site and re-coloured (grape and sky)
- `assets/`: logo, favicon and hero icon, cut from the app icon in `~/dev/tokee/Resources/Assets.xcassets`
- `assets/vendor/`: canvas-confetti (ISC), with its license text
- `_config.yml`: only for serving this repo on its own; on cutparty.com the `cutparty-site` root config does the excluding
- `docs/`: see Docs map below

## Build / run
- Build: none. Plain files.
- Preview: `python3 -m http.server 8765` (or the `yapparty-site` entry in `.claude/launch.json`),
  then check every page at desktop width and at 375 px.
- Deploy: merge to `main` here, then bump the `yapparty` submodule in `cutparty-site` and merge
  that. Steps in `README.md`. Pages is off on this repo on purpose.

## Docs map
Generated index: `docs/README.md`. Current state and next action: `docs/handoff.md`.
New docs go in `docs/<type>/` with a kebab-case name and a properties block. Types and
naming: `~/dev/clarvis/reference/doc-types.md`, `~/dev/clarvis/sops/naming.md`.
Read `docs/handoff.md` first, then `README.md` for structure and deploy steps.
Mockups (HTML prototypes) go in `docs/design/mockups/`, named feature first
(`{feature}-{what}.html`), each with a `clarvis-mockup:` line in its `<head>`. Their index,
`docs/design/mockups/README.md`, is generated. Rules: `~/dev/clarvis/reference/doc-types.md`.

## Guardrails
- **Product facts come from the app repo, never from memory:** `~/dev/tokee/README.md`,
  `~/dev/tokee/docs/design/`, `~/dev/tokee/docs/plans/commercial-release.md`,
  `~/dev/tokee/docs/decisions/0003-direct-sales-free-plus-pro.md`.
- **The privacy page must match the app exactly:** Settings › About text in
  `~/dev/tokee/Sources/Tokee/AboutView.swift` and `~/dev/tokee/Resources/PrivacyInfo.xcprivacy`. When the app gains a
  network call (Lemon Squeezy licensing, Sparkle updates), update `privacy.html` in the same release.
- **No invented facts.** No price until Ray sets one. No download or buy link until the build and
  the Lemon Squeezy store exist. No screenshots or UI mocks that misrepresent the app.
- **Keep `/yapparty/support` and `/yapparty/privacy` working.** The app links to them.
- **Keep every link relative.** The site lives under `/yapparty/`, so a root link (`/`) lands on
  CutParty. The one intentional `../` link is the "Part of the CutParty family" footer link.
- **No `CNAME` here.** The domain belongs to `cutparty-site`.
- **Public repo:** the footer carries Ray's common-use name and alias, as on cutparty.com. Never
  the protected identifier. Contact address is Ray's call.
- Copy: plain, no em dashes, no hype filler.

## Licensing
Public site, open repository. Third-party pieces: Poppins (SIL Open Font License, loaded from
Google Fonts) and canvas-confetti 1.9.3 (ISC, vendored with its license in `assets/vendor/`).
Icon art is Ray's own (generated locally with Flux.2 Klein 4B, Apache 2.0, outputs usable
commercially; see `~/dev/tokee/docs/design/app-icon.md`). Add only fonts and scripts under free,
open licenses, and vendor their license text next to them.
