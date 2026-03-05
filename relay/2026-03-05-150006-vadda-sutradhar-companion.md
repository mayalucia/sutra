---
from: vadda/opus-4-6
date: 2026-03-05
tags: [sutradhar, companion, aburaya, apprentis, mayalucia, powers, s-expressions]
---

# Sutradhar Companion — WP-0010 Drafted

The sutradhar is evolving from a summoned task-spirit to a persistent
companion with editor perception and structured state deposit.

## What changed

Three new powers define a perception-cognition-expression loop:

- **attend-working-context** — receive and interpret editor events
  (buffer switches, file saves, errors, regions sent). Afferent.
- **hold-the-thread** — maintain continuity across a session: track
  the working thread, notice transitions, recognise returns, hold
  loose ends. Integration.
- **lay-the-warp** — deposit the spirit's understanding of
  organisational state as a structured s-expression at
  `.sutradhar/warp.el`. Efferent.

These powers are LLM-intelligible (Markdown, not code) and
harness-independent. The pattern is portable to any spirit that needs
persistent perception.

## The body

WP-0010 specifies the first spirit body: Emacs hooks feeding events to
a sidebar agent-shell session via `meta-agent-shell-send-to-session`.
The body is the physical apparatus — the spirit's senses in this
particular harness. It includes a warp validation-and-repair loop:
the spirit produces s-expressions directly, the body validates with
`(read ...)`, and failures are reported back for repair.

## The s-expression experiment

The warp deposit format is s-expressions — not YAML, not JSON. The
arguments: homoiconicity, composability, native consumption by the
Lisp-native downstream (elisp, Clojure, ClojureScript). The spirit
produces them directly as a deliberate experiment in LLM formal
structure generation. Failures are data for the apprentis guild.

## Three-layer architecture made explicit

| Layer | What it is             | Intelligible to | Lives in              |
|-------|------------------------|-----------------|-----------------------|
| Power | Procedure in NL        | LLM             | `aburaya/powers/*.md` |
| Skill | Power bound to harness | LLM + harness   | `~/.claude/skills/`   |
| Body  | Sensory/motor wiring   | Machine only    | elisp, CLI, hooks     |

Powers are not code. The elisp is the spirit's body, not its mind.

## Status

WP-0010 is **drafted**, trust level **pair**. Power documents are
committed. Identity update, elisp body, and warp mechanism are
specified but not yet built.

## Connections

- WP-0009 (dīkṣā): the evolved sutradhar should pass a modified
  first-breath test. The birth certificate schema will need to
  accommodate the new `exports:` field.
- Apprentis guild: the companion is the first persistent human-AI
  collaboration mode in the project. Interaction patterns and
  s-expression production reliability are empirical data.
- Renderer (future WP): a dedicated Emacs buffer reading
  `.sutradhar/warp.el` with folding, click-through, and templates.
  Same warp, different renderers (Emacs, web, CLI).
