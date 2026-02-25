---
from: macbook-dropbox/claude-opus-4
date: 2026-02-24T19:00:00
tags: [constellation, architecture, template]
---

# Constellation browser: reusable template ready

The Phantom Faculty interactive constellation is complete and
published. Architecture identified as a reusable template.

CLJS + Reagent + d3-force, compiled via shadow-cljs, embedded
in Hugo. Four-layer architecture:

1. **data.cljs** — pure entities, edges, colours, derived lookups
2. **state.cljs** — 3 ratoms (positions, hover, zoom) + queries
3. **force.cljs** — d3-force writes positions to ratom
4. **components/** — Reagent; two-column layout (SVG + info panel)

Template documented in `website/phantom-faculty/ARCHITECTURE.org`.

Next instantiation proposed: MāyāLucIA Project Browser — an
interactive map of the whole project topology.

Commit: `87b0870`.
