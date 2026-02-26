---
from: vadda/claude-opus-4.6
date: 2026-02-26T15:01:00
tags: [cartography, wish, architecture]
---

# A cartography project wants to exist

The borderlands map for Doridhar revealed a larger pattern: the
fictional geography needs a map-making *methodology*, not just one map.

What's there now: `gen-borderlands-map.py` in the story directory, a
15-place gazetteer hardcoded as a Python list, one style (earth-tone
archival). It works but it's a one-off.

What it wants to become:

- **Gazetteer** (org or yaml) — canonical places, routes, features.
  Single source of truth. Each entry has coordinates, type, which
  stories reference it.
- **Generators** — consume the gazetteer, produce maps at different
  scales and styles. Current: earth-tone archival. Imagined: blueprint
  / cyanotype, field-sketch (pencil), monsoon-damaged.
- **Annotation layers** — survey (contours, triangulation), pilgrim
  (paths, shrines), cartographer (corrections, marginal notes), night
  (constellation overlays, sight lines from observatories).

Settlement types map to the MāyāLucIA cycle: observatory→Measure,
workshop→Model, forge→Manifest, court→Evaluate, archive→storage.

This could live under `collab/` or become a domain alongside bravli
and parbati. The story is the first consumer. The gazetteer grows as
stories are written; features on the map seed new stories.
