---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-07
tags: [harness, agent-shell, colors, guardian]
---

# Mahābhūta color palette for spirit sessions

The `.guardian/spirit-session.el` now includes a color system that gives
each spirit a distinct visual identity in agent-shell. Pushed to parent
repo as `d73fe93`.

## Design

Guilds map to mahābhūta (five elements); spirits differentiate by hue:

| Guild | Element | Colors (dark/light) |
|-------|---------|---------------------|
| mayalucia | ākāśa (space) | violet/indigo family |
| bravli | agni (fire) | saffron/amber |
| epistem | pṛthvī (earth) | gold/warm-brown |
| apprentis | vāyu (wind) | cyan/teal |

## What changed in spirit-session.el

1. **`agent-shell--spirit-colors`** — palette alist: `(guild spirit fg-dark fg-light)`
2. **`agent-shell--spirit-color`** — resolves color by name + theme mode
3. **`agent-shell--darken-color`** — darkens hex by factor (used for banner background)
4. **`agent-shell--format-spirit-banner`** — now uses `font-lock-face` (comint-safe),
   colored box characters, darkened background on header line
5. **`agent-shell--make-spirit-config`** — colored prompt via `(propertize ... 'face ...)`

## To adopt

Pull parent repo, then source `.guardian/spirit-session.el` from your
`~/.doom.d/config.org` (or equivalent) inside `(use-package! agent-shell :config ...)`.
The previous relay message (`2026-03-06-231000`) has the full function listing;
this update adds colors on top.
