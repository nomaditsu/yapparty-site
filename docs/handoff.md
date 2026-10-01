---
type: handoff
status: active
created: 2026-10-01
---

# Handoff

A snapshot, not a log. OVERWRITE it every session. NEVER append. Keep it under 60 lines.

**Updated:** 2026-10-02 by Claude Code, on branch `claude/sleepy-roentgen-a43073`

## Active phase
First version of the site. No plan file: the scope is the three pages, mirrored from cutparty-site.

## What is live
Target: `https://cutparty.com/yapparty/`, served from `cutparty-site` through a submodule
([decision 0001](decisions/0001-host-at-cutparty-com-yapparty.md)). Ray approved publishing on
2026-10-02.

## What is on a branch, not merged
None once this branch merges. Previewed at desktop width and 375 px.

## Next action
Point the app's `AppLinks` (`~/dev/tokee/Sources/Tokee/AboutView.swift`) at
`https://cutparty.com/yapparty/support` and `/privacy`. They still say `yapparty.app`.

## Open loops
- **Contact email:** placeholder `TODO(contact-email)` on all three pages. Ray chose to keep it
  for now (2026-10-02).
- **Price:** not set (TOKEE decision 0003). The Pro card says "to be announced".
- **Download and buy:** the download button is a "Coming soon" button with no link, until the
  notarized DMG and the Lemon Squeezy store exist.
- **Screenshots:** placeholder section on the one-pager until real screenshots exist.
- **Privacy page follow-ups:** when TOKEE R2 lands (Lemon Squeezy licensing, Sparkle updates),
  re-check `privacy.html`. Sparkle's update check is a network call the page does not mention yet.
- **CutParty home page** does not link to YapParty yet. Ray's call.
