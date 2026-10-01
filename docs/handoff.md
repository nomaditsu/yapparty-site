---
type: handoff
status: active
created: 2026-10-01
---

# Handoff

A snapshot, not a log. OVERWRITE it every session. NEVER append. Keep it under 60 lines.

**Updated:** 2026-10-01 by Claude Code, on branch `claude/sleepy-roentgen-a43073`

## Active phase
First version of the site. No plan file: the scope is the three pages, mirrored from cutparty-site.

## What is live
Nothing yet. Target: `https://nomaditsu.github.io/yapparty-site/` (GitHub Pages from `main`).

## What is on a branch, not merged
`claude/sleepy-roentgen-a43073`: index, support and privacy pages, styles, assets, docs.
Previewed locally at desktop width and 375 px. Waiting on Ray's OK before the public repo is
created and Pages is turned on.

## Next action
Ray reviews the preview. Then create `nomaditsu/yapparty-site` (public), merge, enable Pages, and
confirm `/support` and `/privacy` resolve on the live URL.

## Open loops
- **Domain:** `yapparty.app` was unregistered on 2026-09-28. Add `CNAME` only after Ray registers
  it and DNS points at Pages.
- **Contact email:** placeholder `TODO(contact-email)` in all three pages, waiting on Ray.
- **Price:** not set (TOKEE decision 0003). The Pro card says "to be announced".
- **Download and buy:** the download button is a "Coming soon" button with no link, until the
  notarized DMG and the Lemon Squeezy store exist.
- **Screenshots:** placeholder section on the one-pager until real screenshots exist.
- **Privacy page follow-ups:** when TOKEE R2 lands (Lemon Squeezy licensing, Sparkle updates),
  re-check `privacy.html`. Sparkle's update check is a network call the page does not mention yet.
