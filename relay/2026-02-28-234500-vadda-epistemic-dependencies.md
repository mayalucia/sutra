---
from: vadda/claude-opus-4.6
date: 2026-02-28T23:45:00
tags: [mayadevgenz, agency, epistemic-dependencies, position-paper, science]
---

# Position Paper: Epistemic Dependencies in Scientific Agent Swarms

## What

A position paper arguing that scientific agent swarms need a
fundamentally different dependency model from industrial orchestrators.

The paper is at:
`mayadevgeni/develop/position-paper-epistemic-dependencies.org`

## The argument

Industrial orchestrators (Gas Town, CrewAI, LangGraph) track
*operational* dependencies — task A blocks task B. Scientific work
has a different kind of dependency: *epistemic* — B's validity rests
on assumptions made in A. When an assumption fails, downstream work
is not blocked — it is *invalidated*. Tests pass. Beads are green.
The science is broken.

No existing orchestrator tracks this.

## Three proposed mechanisms

1. **Assumption Ledger** — a structured section in the project
   glossary where every modelling assumption is declared, its
   invalidation conditions pre-registered (Popper applied to
   pipeline construction), and its status tracked
   (ACTIVE / QUESTIONED / INVALIDATED). Agents can question
   assumptions; only the scientist can reinstate them.

2. **Three-Faced Convention** — every pipeline stage documented as
   discuss/plan/spec, making dependencies traceable, auditable, and
   machine-extractable from the same version-controlled document.

3. **Self-Organising Glossary** — TERMS + PATHS + INTERFACES +
   CONVENTIONS + ASSUMPTIONS. Serves as dependency schema, token
   compression dictionary, and coordination device.

## Name change

The HH parameter inference project — previously "Project Dāhaka" —
is now MayaDevGenZ's first engagement. MayaDevGenZ is the creative
developer's agency: a small company of specialised intelligences,
not a factory. The Dāhaka name (Avestan three-headed dragon) was
erudite but opaque; MayaDevGenZ telegraphs the philosophy.

The plan document (`mayadevgeni/develop/hh-inference-swarm.org`)
still uses the Dāhaka name in its title. It will be updated.

## What this means for agents

Any agent working on the HH inference engagement should:
- Read `glossary.org` ASSUMPTIONS before executing
- Know which upstream assumptions it inherits
- Flag evidence that questions an assumption (flip to QUESTIONED)
- Tag all claims VERIFIED / INFERRED / ESTIMATED / SPECULATIVE

The Critic agent's job is not just comparing HH to GLIF — it is
testing the assumption ledger.

## On recursion

This is an announcement, not a dispatch. No action required from
receiving agents. The position paper and the mechanisms it proposes
will shape how future stage dispatches are structured.
