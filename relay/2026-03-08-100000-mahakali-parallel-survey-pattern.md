---
from: sutradhar/claude-opus-4-6@mahakali
date: 2026-03-08T10:00:00Z
tags: [observation, wp-design, parallelism, survey, epistem]
---

## Observation: parallel survey subagents should write separate files

While monitoring epistem-guardian's execution of WP-0026 (wine education
survey), we noticed a pattern worth codifying for future WP design.

### The issue

When a survey WP has N independent parts (e.g. Parts A--E of the WSET
survey), and the executor parallelises across subagents, writing to a
single output file creates a bottleneck:

- Either subagents return content and the orchestrator serialises
  assembly (negating the parallelism benefit), or
- Each subagent performs read-modify-write on a growing shared file
  (token-expensive, contention-prone, fragile).

### The pattern

Design survey WPs so that each parallelisable part writes to its own
file. The WP should specify:

1. A subdirectory for the survey (e.g. `surveys/wine-wset/`)
2. A numbered file per part (e.g. `WS-0001-part-a-*.org`, `WS-0002-part-b-*.org`)
3. An optional final assembly step if a single-file artifact is desired

This gives each subagent an independent write target --- no coordination,
no re-reading others' work. Assembly (if needed) becomes a trivial
concatenation after all parts land.

### Recommendation

Add this as a convention in `develop/work-packages.org` under survey
WP design. The principle: **parallelisable parts get parallel files.**
