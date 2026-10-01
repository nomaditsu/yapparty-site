---
type: decision
status: active
created: 2026-10-02
project: TOKEE
---

# 0001. Host the site at cutparty.com/yapparty, mounted as a submodule

## Context and problem
The plan was a site on its own domain, `yapparty.app`, which is not registered. On 2026-10-02 Ray
chose to present YapParty as a sub product of CutParty, served at `cutparty.com/yapparty`.
`cutparty.com` is the custom domain of the `nomaditsu/cutparty-site` Pages site, not of the
`nomaditsu.github.io` user site, so another repo's Pages site cannot appear under it on its own.

## Options considered
- **Copy the files into `cutparty-site/yapparty/`**: one repo. Good: simplest. Bad: this repo stops
  being the source, and the two copies drift.
- **GitHub Action in this repo that pushes into `cutparty-site`**: Good: automatic. Bad: needs a
  personal access token stored as a secret.
- **Give the user site the `cutparty.com` domain**: Good: every project site appears at
  `cutparty.com/<repo>`. Bad: moves a live production domain, and puts unrelated project sites under it.
- **Mount this repo in `cutparty-site` as a git submodule at `yapparty/`**: Good: this repo stays
  the only source, no secrets, GitHub Pages checks out public submodules when it builds. Bad: each
  update needs a pointer bump in `cutparty-site`.

## Decision
Chosen: **submodule**, because it keeps one source of truth with no secrets and no change to how
`cutparty.com` itself is served.

## Consequences
- Live URLs: `https://cutparty.com/yapparty/`, `/yapparty/support`, `/yapparty/privacy`.
- To publish a change: merge here, then in `cutparty-site` run
  `git submodule update --remote yapparty`, commit and merge there. The README has the steps.
- GitHub Pages stays off on this repo, so there is no second copy at `nomaditsu.github.io/yapparty-site`.
- `cutparty-site/_config.yml` keeps this repo's docs (`AGENTS.md`, `docs/`, `README.md` and so on)
  off the published site.
- All links inside the site stay relative, so it works under any path.
- The app's `AppLinks` (`~/dev/tokee/Sources/Tokee/AboutView.swift`) still point at
  `yapparty.app`. They must move to `cutparty.com/yapparty` before release.
- `yapparty.app` is dropped for now. If it is registered later, it can redirect here.

## Evidence
GitHub Pages API on 2026-10-02: `cutparty-site` has `cname: cutparty.com`; `nomaditsu.github.io`
has `cname: null`.
