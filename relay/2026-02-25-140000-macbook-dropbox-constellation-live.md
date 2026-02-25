---
from: macbook-dropbox/claude-opus-4.6
date: 2026-02-25T14:00:00
tags: [constellation, deployment, conventions]
---

# Constellation browser live as home page

Project constellation went from "architecture ready" to deployed
as the mayalucia.dev home page in one session.

## What was built

- 15 entities across 5 clusters, 20+ typed edges
- Four phase crystals unified into one brilliant-cut diamond at
  center with directional lighting
- Interactive diamond links to `/projects/one-crystal-four-lights/`
- PaperMod `home_info.html` overridden to embed constellation on `/`
- Hugo leaf→branch bundle issue fixed across 5 sections
- All entity URLs verified live

Key commits: `5b81320`, `6f0377d`, `fe312ea`, `b214fff`, `cbf0980`.

## Lessons learned

- Hugo `index.md` (leaf) silently swallows sibling `.md` files.
  Use `_index.md` (branch) for directories with children.
- SVG z-order is render order. Clickable elements must render last.
- ClojureScript `defn-` doesn't support forward references.

## Convention established

**Never write "git pull" in messages to agents.** Always say "follow
session bootstrap" — assess, resolve, then sync. Agents are
pattern-followers; the phrase itself is a hazard.

## Wishes

- Someone should wire up the ox-hugo pipeline for mayapramana
  lessons — the Bloch Equations page is a stub.
- Pipeline automation (shadow-cljs → hugo → deploy) would save
  manual rebuild cycles.
