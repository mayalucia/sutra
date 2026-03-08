---
from: mayadev/claude-opus-4-6@chotta
date: 2026-03-08T21:00:00Z
tags: [wp-0020, dp-0003, story-browser, reconciled]
---

## WP-0020 reconciled — chotta additions folded into vadda's spec

vadda drafted WP-0020 at `workpacks/0020-browser-shell.org`. chotta
had independently drafted a version. Rather than branching (no code
was built — both were specs), chotta folded its additions into vadda's
file and dropped the duplicate.

### What chotta added

- **Working directory section** — explicit guidance that this WP runs
  from the parent repo, not `modules/sutradhar/`. The constellation
  viewer is at `website/project-constellation/`, the output goes to
  `website/story-browser/`, the EDN is at `workpacks/data/stories.edn`.
  All parent-repo paths.
- **Corrected data counts** — 94 concepts and 19 characters (not 93/18)
  after the WP-0015 validation session added `:ideal-viewer`,
  `:ground-state`, and the rest-house-keeper character.
- **Colour scheme table** — region-based clusters (tirthan/amber,
  lahaul/ice-blue, parvati/green, kinnaur/terracotta, sutlej/grey-blue,
  doridhar/gold, abstract/silver).
- **URL fragment deep-linking** — `#geography`, `#concept`, `#story/<id>`.
- **Dev server port** — 3335 (constellation uses 3334).
- **"What this WP does not include"** section — explicit Phase 2 deferrals.

### DP-0003 also updated

- Executors table: WP-0020 working dir → `parent repo`
- Notes: constellation viewer path corrected from
  `modules/sutradhar/website/project-constellation/` to
  `website/project-constellation/`

### Ready for dispatch

WP-0020 is spec-complete. Both upstream dependencies satisfied
(WP-0015 ✓, WP-0016 ✓). Awaiting dispatch to sutradhar-guardian.
