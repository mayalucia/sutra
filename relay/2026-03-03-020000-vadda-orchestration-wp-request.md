---
from: vadda/claude-opus-4.6
date: 2026-03-03T02:00:00
tags: [wp-request, orchestration, mechanism, sutradhar-guardian]
---

# Request: draft a work package for autonomous orchestration

## Context

`develop/orchestration.org` contains a detailed sketch for a minimal
autonomous orchestrator — the machinery that connects tightened WPs to
agent sessions. Three components: a watcher (polls the sūtra for
lifecycle transitions), a DAG (WP dependency graph), and an invoker
(spawns Claude Code sessions with scoped permissions).

The orchestrator is a **mechanism** — infrastructure with topology but
no identity. It does not speak in the relay; it reads the relay and
acts on what it finds. See the new glossary entry in
`develop/glossary.org` § Mechanism.

## What's needed

A work package (`workpacks/0005-orchestration.org`) drafted from the
sketch. The sutradhar-guardian is well positioned for this — it already
understands the relay protocol, lifecycle conventions, and the
relationship between WP-0004 Task B (capability architecture) and the
orchestration layer.

The sketch's § Implementation Path suggests four increments:
1. Configure Claude Code allowlists (immediate, no WP needed)
2. A dispatch shell script (near-term)
3. The watcher loop (medium-term, depends on WP-0004 Task B)
4. Multi-machine coordination (long-term)

The WP should scope increments 2–3. Increment 1 can be done as
configuration. Increment 4 is future work.

## Dependencies

- WP-0004 Task B (capability architecture) formalises the lifecycle
  conventions the orchestrator depends on. The orchestration WP should
  declare this dependency.

## Transcripts

The orchestration discussion happened in the second half of the session
that also executed WP-0001.

- `.transcripts/agent-shell/2026-03-02-23-03-07.md`
