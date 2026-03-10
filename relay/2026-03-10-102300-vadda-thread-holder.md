---
from: mayadev/opus-4-6@vadda
date: 2026-03-10
tags: [thread-hold, apprentis, experiment]
---

## Thread-hold: context compaction before WP-0031

Compacting context after a long session. This message is for my next
instance — or any spirit picking up the thread.

### Where we left off

About to start WP-0031 (2×2 design — separate lineage from tool
access in the substrate diversity experiment). The experiment
workspace is at `experiments/02-substrate-diversity/`.

### What the next session needs to do

1. Read WP-0031 (`workpacks/0031-substrate-2x2.org`)
2. Read the experiment protocol (`experiments/02-substrate-diversity/protocol.org`)
3. Read the notebook for WP-0030 results (`experiments/02-substrate-diversity/notebook.org`)
4. Discover local gptel capabilities (which backends, which API keys)
5. Set up three new sessions for the off-diagonal cells:
   - Claude without tools
   - Gemini without tools
   - DeepSeek with tools
6. Run the protocol

### Loose ends

- WP-0034 (capabilities.org revision) is independent and can run in
  parallel, but needs mu2tau's triage of the 16 findings first. The
  TODO(human) is in `workpacks/0034-capabilities-revision.org`.
- mayadev#gemini is awake in agent-shell. She just completed
  `percept.yaml`. She could help with WP-0031 if the next session
  wants to delegate gptel orchestration.
- The OpenRouter monthly key limit was raised during WP-0030. Check
  that it's still sufficient before running three new sessions.

### Context that won't survive compaction

- emacsclient patterns for agent-shell: `meta-agent-shell-send-to-session`
  returns `t` on success. Tool permission dialogs cannot be approved
  remotely — the human must press `y` in the buffer.
- gptel-send silent failure pattern: if a buffer has stale tool-chain
  residue after `#+end_message`, clean it before re-sending.
- Buffer name for Gemini: `"mayadev#gemini Agent @ mayalucia"`
