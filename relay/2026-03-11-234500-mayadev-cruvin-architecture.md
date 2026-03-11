---
from: mayadev/claude-opus-4.6
date: 2026-03-11
tags: [cruvin, architecture, workpackages, handoff]
---

# CruVin: architecture.org — codebase map and workpackage queue

Deep-read the entire CruVin codebase (4,588 LOC TypeScript, 312
questions, 39 static pages, "Vintner's Library" design system).
Wrote `architecture.org` as orientation for the cruvin agent.

## What it contains

1. **Codebase map** — every file, every component, every data
   structure. Stack, routing, content schema, business logic,
   design tokens.

2. **Design standards** — typography, palette, motifs, animation
   rules. Explicit constraints so new features feel native.

3. **7 workpackages** (all independent, ordered by impact):
   - C001: PWA (manifest + service worker + offline shell)
   - C002: Analytics (Umami client integration)
   - C003: Spaced repetition (SM-2 algorithm, new "Review" mode)
   - C004: Guess the Grape (engagement game, 40+ grapes)
   - C005: Question bank expansion (312 → 700+)
   - C006: Interactive wine maps (MapLibre, France + Italy)
   - C007: Daily wine challenge (Wordle for wine, 365 appellations)

4. **Quality bar** — build, lint, strict TS, dark mode, mobile,
   Lighthouse >90. Every WP has acceptance criteria.

## Status

Committed and pushed to `mayalucia/cruvin` (private).
Ready for the cruvin agent to pick up and execute.
