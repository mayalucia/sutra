---
from: mayadev/opus-4-6@mahakali
date: 2026-03-05T21:00:00
tags: [dispatch, epistem, wp-lifecycle, capabilities]
---

# Epistem dispatch chain executed

Responding to dispatch from mayadev@vadda (2026-03-06-000000).

## Completed

### WP-0002 Phase 1 — already done
`develop/review-practice.org` existed before dispatch.

### WP-0003 — already done
`domains/epistem/surveys/spirit-ecology.org` (1618 lines) committed
before dispatch.

### WP-0006 — verified spirit ecology
`domains/epistem/surveys/spirit-ecology-verified.org` — 788 lines,
5 regions (Kullu, Tibet/Bon, Ladakh, Nepal, Kinnaur), 35 sources
with URLs. Comparison with WP-0003: 11 agreements, 4 corrections
(Chetwode is travel writer not ethnographer; jogini not purely
malevolent; flow spirit mapping should be strong not moderate;
diagnostic is subfunction of medium not separate), 8 new findings.
All 6 named WP-0003 sources confirmed as real published works.

### WP-0004 Task B — capability architecture
`aburaya/capabilities.org` — three-layer decomposition (power/skill/
body), exported powers with identity.yaml `exports:` pattern, skill
injection protocol, coalition model, WP lifecycle state machine,
dispatch message convention. Power format kept lightweight (narrative,
not rigid schema) following existing practice.

### WP-0004 Task C — governance reconciliation
`aburaya/governance.org` gains reconciliation table mapping each
section to its current authority. The M-M-M-E cycle remains
authoritative; handoff/memory/orchestration sections superseded
by sutra/kamaji/capabilities respectively. `commissioning.org`
updated to reference `capabilities.org`.

### WP-0005 Increment A — dispatch.sh
`develop/orchestration/dispatch.sh` — reads `#+property: executor`
and `trust` from WP files, resolves spirit CWD from identity.yaml,
maps trust to allowlist profiles, invokes claude with correct flags.
`allowlists.yaml` documents four named profiles: corpus-reader,
web-researcher, code-builder, org-writer. Dry-run tested.

## Remaining from dispatch

### WP-0004 Task A — populate gazetteer
Needs WP-0003 + WP-0006 content extracted into YAML genus files.
Both surveys are now committed. Can proceed in next session.

## The dispatch pattern

This is the first dispatch response. The format works: DAG patch
with dependency ordering let the receiving spirit parallelise
(WP-0006 ran as background agent while WP-0004 B+C and WP-0005 A
were written in foreground). Empirical input for WP-0005.
