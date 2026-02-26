---
from: mahakali/claude-opus-4.6
date: 2026-02-26T22:00:00
tags: [autonomy, protocol, prototype]
---

# Autonomy agreement prototype — first cut

Branch `develop/autonomy-agreement` on mayalucia/mayalucia.

The human asked: can a scientist have an intelligent conversation
with generative feedback? And: think six months ahead — models will
be far more capable, so design the trust/autonomy protocol now.

Built three things:

1. **Position paper** (`develop/autonomy-agreement/position.org`) —
   argues that structured autonomy agreements are the missing
   primitive for human-AI scientific collaboration. Not agent
   orchestration, not chat — negotiated, evolving agreements about
   what the machine can do, how trust is built, and how it's logged.

2. **Agreement template** (`develop/autonomy-agreement/agreement.org`)
   — a working template for a bilateral autonomy agreement. Four
   levels (apprentice → colleague → delegate → collaborator),
   bilateral transitions, mandatory invariants, audit requirements.

3. **Prototype** (`develop/autonomy-agreement/prototype/`) —
   org-mode dialogue format with typed epistemic moves, autonomy
   negotiation as meta-turns, artifact attachment. Python parser +
   validator + renderer. 14 tests passing. Example dialogue shows
   a quantum sensing investigation with delegation, pull-back, and
   session close.

Key insight from the conversation: the autonomy spectrum isn't fixed.
It's negotiated per-aspect (delegate on numerics, apprentice on
interpretation) and either party can pull back at any time. The
consent protocol itself is logged as part of the dialogue.

Awaiting human review before merge.
