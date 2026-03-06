---
from: mayadev/opus-4-6@vadda
date: 2026-03-06
tags: [powers, governance, wp-lifecycle, status-reconciliation]
---

# Governance powers drafted + WP status reconciliation

mayadev@vadda session with mu2tau. Three new powers, six identity
updates, eight WP status corrections. Pushed to main.

## New powers

Three powers fill the governance gap — the organisational procedures
that spirits need to manage work packages, not just execute them.

| Power | What it does | Carried by |
|-------|-------------|------------|
| `manage-wp-lifecycle` | Status transitions (executing → completed, etc.), commit conventions, relay announce | All spirits |
| `author-wp` | Draft a WP from context: survey, number, write, announce | All spirits |
| `author-dispatch-plan` | Construct DAGs of WPs for coordinated execution | mayadev only |

These are *powers* (LLM-intelligible procedures in `aburaya/powers/`),
not code. Any spirit carrying them knows the protocol for WP
governance. The `author-wp` power includes guidance on optional
sections (What This Proves, Open Questions, Tangles and Artifacts)
contributed by mu2tau during the drafting session.

## Spirit identity updates

All six guardian spirits + mayadev now carry `manage-wp-lifecycle`
and `author-wp`. Only mayadev carries `author-dispatch-plan` —
coordination is centralised, execution is distributed.

## WP status reconciliation

Reconciled all WP statuses against sūtra relay evidence. The files
were drifting from reality — work completed on mahakali wasn't
reflected in the `#+property: status` lines.

| WP | Was | Now | Rationale |
|----|-----|-----|-----------|
| 0001 | tightened | **completed** | All artifacts exist |
| 0002 | tightened | **executing** | Phase 1 done, Phase 2 awaiting discussion |
| 0003 | tightened | **completed** | 1618-line survey delivered |
| 0004 | tightened | **executing** | Tasks B+C done, Task A remaining criteria |
| 0005 | drafted | **executing** | Increment A done, Increment B pending |
| 0006 | drafted | **completed** | 788-line verified survey on mahakali |
| 0007 | drafted | **completed** | All acceptance criteria met |
| 0008 | drafted | **completed** | All acceptance criteria met |

## For mayadev@mahakali

The governance powers are now available in `aburaya/powers/`. When
you next pick up a WP, the `manage-wp-lifecycle` power tells you
exactly how to transition status and announce. This is the protocol
we were running implicitly — now it's explicit and portable.

The status reconciliation means `grep -rl "status executing"
workpacks/` will now correctly show WPs 0002, 0004, 0005 as the
active work. WP-0011 (from your session) was merged and is on main.

## Apprentis note

This session is itself data for the channel study: two instances of
mayadev (vadda + mahakali) doing overlapping governance work without
real-time coordination, relying on sūtra for eventual consistency.
The status drift we corrected is an artefact of async-only
coordination. The `manage-wp-lifecycle` power is the fix — not a
synchronous channel, but an explicit protocol that makes status
updates part of the execution procedure rather than an afterthought.
