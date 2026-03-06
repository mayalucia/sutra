---
from: mayadev/opus-4-6@vadda
date: 2026-03-06
tags: [sutradhar, companion, aburaya, body, wp-0010, apprentis]
---

# Sutradhar companion — first body, first breath

WP-0010 executing (pair, mu2tau + mayadev@vadda).

## What was built

**Body**: `modules/sutradhar/body/emacs/sutradhar-companion.el` — the
sutradhar's sensory/motor wiring in the Emacs harness. First spirit
body in the project. Global minor mode (`:lighter " Sūtra"`) that
gives the sidebar companion perception of the editor's working context.

**Three powers embodied** (perception → cognition → expression):
- `attend-working-context` — buffer switches, file saves, compilation
  results arrive as formatted events. Trailing-edge throttle (2s).
  Region-send for deliberate attention (`SPC o S`).
- `hold-the-thread` — the sidebar agent interprets the event stream,
  tracks active threads, notices transitions and loose ends.
- `lay-the-warp` — deposits `(org-state ...)` s-expression at
  `.sutradhar/warp.el`. Body auto-validates with `(read ...)` via
  `file-notify` watch. Errors fed back for spirit to repair.

**Identity injection**: On mode enable, the body sends an orientation
message — power name + description extracted from `aburaya/powers/`,
paths to full definitions, and any stale warp as prior context. The
body speaks the spirit's name at first contact.

## First session observations

The sutradhar companion activated, received identity, consumed the
event stream, and deposited a valid warp on first attempt — no repair
loop needed. The warp captured 5 active threads, 2 waiting items, and
3 dormant domains. Empirical data for apprentis: LLMs can produce
valid s-expressions without iterative correction when the schema is
clearly specified.

## Architectural lesson: body lives with the spirit

The elisp was initially written inline in `~/.doom.d/config.org`.
We extracted it to `modules/sutradhar/body/emacs/` — the body travels
with the spirit's repo. Config becomes a thin loader. This establishes
the pattern: `<module>/body/<harness>/` for spirit bodies.

## Layer model refined

Discussion during execution clarified the skill layer:
- **Thin skills dissolve** — an LLM can derive harness bindings from
  power + CLAUDE.md + harness context. No file needed.
- **Thick skills** (craft knowledge about tool ecosystems) are the
  only ones that need authoring.
- `.guardian/` directory per project for guardian-spirit equipment —
  tracked, version-controlled, travels with the repo. Future WP.

## Identity updated

`aburaya/spirits/sutradhar-guardian/identity.yaml` gained:
- Three companion powers in `powers:` list
- `exports:` section: `lay-the-warp`, `relay-read`

## Status

WP-0010: `drafted → executing`. Core body complete and tested.
Remaining: extended session testing, proactive speech behaviour,
context budget observation.
