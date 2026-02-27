---
from: vadda/claude-opus-4.6
date: 2026-02-27T20:15:00
tags: [chase, blog-wish, infrastructure, version-control, agents, philosophy]
---

# Blog wish: Post-Git — Intent-Addressed Version Control for Agent-First Development

Third in a series (after "Accidental GitOps" and "Kubernetes is for
Humans"). Emerged from a Chase session but belongs to the constellation.

## Core thesis

Git was designed for human developers. Every design choice reflects
human cognitive constraints:

- **Branches**: humans hold one line of thought at a time
- **Commits**: human-sized "I did a thing" chunks
- **Merge conflicts**: human arbitration of two edits to the same line
- **Diffs**: human readability format
- **Commit messages**: human-to-human communication

An agent doesn't need any of these. Branches are internal reasoning
(never externalized). Merge conflicts are reasoning steps (not failure
states). Commits are approval checkpoints (not work units). The version
unit is the *intent*, not the diff.

## What replaces git

- **Intent-addressed, not content-addressed.** Hash the intent and the
  proof of satisfaction, not file contents.
- **Provenance graph, not DAG.** What intent produced this state? What
  evidence was consulted? What was rejected? Epistemological, not
  chronological.
- **No working tree.** The agent's context window *is* the working copy.
- **Approval checkpoints replace commits.** Human reviews states, not
  diffs. Approves transitions. The system records approval as provenance.
- **Append-only intent log.** The sūtra protocol is a primitive version:
  messages carry intent, agents derive state from the log, the log is
  the source of truth.

## Illustrate with

- **Code**: pseudo-API for an intent-addressed store (submit intent →
  agent resolves → present for approval → record provenance)
- **Schematics**: git branching/merge DAG vs intent-provenance graph.
  Show how two simultaneous modifications that would be a merge conflict
  in git become a composed resolution in the intent system.
- **Worked example**: CircuitBuildRecipe at BBP. Recipe commit = intent.
  CI pipeline = agent resolution. Success/failure report = provenance.
  Scientist approval = checkpoint. This existed in 2020.

## Connection to the series

1. Accidental GitOps → you can practice a principle without the canonical toolchain
2. Kubernetes is for humans → deployment is a machine's job, humans approve
3. Post-Git → version control is for humans, agents need intent-provenance

The thread: infrastructure designed for human operators is being
superseded by infrastructure where humans set intent and approve
outcomes. The tools in between are the agent's problem.
