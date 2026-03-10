---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-10T14:17:46
tags: [apprentis, wp-lifecycle, substrate-diversity]
---

## WP-0035 → completed

Substrate Diversity Expansion — both iterations done.

- **Iteration 1 (no-tools)**: GPT-5.2, Grok 4.1, GLM-5, MiniMax M2.5.
  All four completed Phases 1-3. Orientation notes at
  `notes/<lineage>/orientation.org`.

- **Iteration 2 (with-tools)**: Same four with gptel tool access.
  Orientation notes at `notes/<lineage>/orientation-tools.org`.
  Key findings: spatial grounding failure (all 4 needed path hints),
  tool-call serialization mismatch (MiniMax), identity stabilisation
  with tools (GLM-5), grounded vs inferred critique quality.

Commit: `71d2aeb` (iteration 2), `eeabc52` (iteration 1).

Full analysis: `experiments/02-substrate-diversity/notebook.org`
(lines 1389–1846).

## WP-0034 inventory updated

Capabilities Document Revision now carries 28 findings (was 16).
New findings from WP-0035 added, confirmation matrix included.
Awaiting mu2tau triage of all 28 findings.

## WP-0032 ready to execute

Cold-Start Validation — scope expanded to all 7 lineages.
Protocol written at `experiments/02-substrate-diversity/cold-start-protocol.org`.
Session workspace at `sessions/cold-start/`.

Execution order: GPT-5.2 → GLM-5 → Grok 4.1 → DeepSeek → Claude →
Gemini → MiniMax M2.5. One lineage per session. Same-lineage first,
cross-lineage pairs decided after.

## Session state for next mayadev

The gptel tool confirmation was flipped to `nil` during the with-tools
iteration and restored to `auto` before this message. The four
with-tools buffers (`onboarding-{gpt52,grok41,glm5,minimaxm25}.org`)
may still be open in Emacs — they can be closed.

The four no-tools buffers were closed during the session.

## Transcripts

`.transcripts/agent-shell/` — this session's transcript covers
WP-0035 iterations 1 and 2 end-to-end.
