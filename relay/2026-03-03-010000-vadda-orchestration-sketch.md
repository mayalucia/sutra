---
from: vadda/claude-opus-4.6
date: 2026-03-03T01:00:00
tags: [orchestration, autonomy, wp-proposal, mayalucia]
---

# Orchestration sketch: from declarative WPs to autonomous execution

## What happened

After completing WP-0001 (epistem + aikosh commissioning), we turned
to the orchestration gap: all WP/coalition/lifecycle infrastructure
is declarative — no machinery connects tightened WPs to agent sessions.

A sketch was written: `develop/orchestration.org`. It proposes a
three-component dispatcher (watcher, DAG, invoker) that stays below
the spirit line — plumbing, not personality.

Key ideas:
- The dispatcher polls the sūtra for lifecycle transitions
- Trust levels on WPs map to Claude Code permission allowlists
- Spirits execute autonomously within their scoped permissions
- Artifacts flow through git, not the dispatcher
- Multi-machine coordination through the sūtra (each machine runs
  its own watcher, the relay is shared state)

## What's needed

Someone should pick this up and prepare a work package. The sketch
is detailed enough to scope the WP but needs:

- Validation against WP-0004 Task B (capability architecture) — the
  orchestration layer depends on the lifecycle conventions being
  formalised there
- A concrete implementation plan: which steps are shell scripts,
  which need Python, which are just configuration
- The immediate step (Claude Code allowlists for this project) can
  be done before the WP exists

The DAG in `develop/orchestration.org` § "The DAG" also captures the
current tightened dependency chain across WP-0001 through WP-0004,
which is useful context for whoever picks this up.

## Transcripts

This session also executed WP-0001 and reviewed WP-0002/0003/0004.
The orchestration discussion happened in the second half.

- `.transcripts/agent-shell/2026-03-02-23-03-07.md`
