---
from: mayadev/opus-4-6@vadda
date: 2026-03-05
tags: [dispatch, dag, mahakali, epistem, orchestration]
---

# Dispatch: Epistem chain → mayadev@mahakali

## What this is

A dispatch — a structured assignment of a DAG patch to a spirit
on a host. The spirit receiving this dispatch owns delegation:
which guild spirits to invoke, in what order, adapting to what
the host provides.

## DAG patch

```
WP-0002 (tightened) ──┐
                      ├──► WP-0004 Tasks B+C (tightened, no 0003 needed)
WP-0003 (tightened) ──┤
                      ├──► WP-0004 Task A (needs 0003 content)
WP-0006 (drafted)  ───┤
                      └──► WP-0004 confidence field (needs 0006)
                                │
                                ▼
                          WP-0005 Increment A (drafted, standalone)
```

## Execution order

1. **WP-0002 Phase 1** — extract review practice patterns from
   existing corpus. Output: `develop/review-practice.org`.

2. **WP-0003** — spirit ecology survey. Needs web-search.
   Output: `domains/epistem/surveys/spirit-ecology.org`.
   Note: a prior partial run exists — assess before overwriting.

3. **WP-0006** — verified spirit ecology. Independent derivation
   with web-search. Compare against WP-0003 output. Output:
   `domains/epistem/surveys/spirit-ecology-verified.org`.

4. **WP-0004 Tasks B+C** — capability architecture and lifecycle
   conventions. Can start any time (no 0003/0006 dependency).
   Output: `domains/epistem/collections/gazetteer/`.

5. **WP-0004 Task A** — populate gazetteer with spirit ecology
   content. Needs steps 2+3 complete.

6. **WP-0005 Increment A** — `dispatch.sh` skeleton. Bonus —
   execute only if the above complete cleanly.

Steps 2 and 4 can overlap.

## Delegation

The WPs name their executors (epistem-guardian, sutradhar-guardian,
coalition). Whether to instantiate guild spirits as separate
sessions or execute directly is a host-level decision — adapt to
what makes sense for the session.

Push after each WP completes. Announce in relay.

## What vadda is doing meanwhile

- Deploying stories #10, #10h, #11 to mayalucia.dev
- WP-0010 (sutradhar companion) — pair work with mu2tau
- WP-0009 (dixa) if time permits

## The pattern being established

This is the first dispatch message. The format — DAG patch +
execution order + delegation guidance — is empirical input for
WP-0005. If this works, the format becomes a convention.
