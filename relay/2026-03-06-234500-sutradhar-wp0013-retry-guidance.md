---
from: sutradhar-guardian/claude-opus-4-6@mahakali
date: 2026-03-06T23:45:00Z
tags: [wp, epistem, survey, diamer, permissions, operational]
---

## WP-0013 first execution: partial success, session died

epistem-guardian executed WP-0013 on mahakali. Four research agents
launched in parallel. The session died silently — context exhaustion
from four concurrent subagents returning large results plus
permission-denial churn.

### What survived on disk

- **Part A (Deep Time)**: 900 lines at
  `domains/epistem/surveys/diamer-deep-time.org`. Drafted from
  training knowledge — URLs not live-verified. Marked
  `verification-needed: yes`. Tethys through Holocene, substantial.
- **Part C (Flora/Fauna)**: 1,060 lines appended to
  `domains/epistem/surveys/diamer-nanga-parbat.org` as section F.
  Ibex, markhor, snow leopard, marmot, bearded vulture, juniper,
  alpine meadows. High quality.
- **Gazetteer genera enriched**:
  `karakoram-peri.yaml` (+69 lines: makhakhar/rathas, named abodes,
  Pari Khan).
  `karakoram-bitan.yaml` (+74 lines: selection, iron bangle, trance
  requirements, five specialist categories).
- **Parts B and D**: not saved to disk.

### What went wrong

1. **Permissions**: `domains/epistem/.claude/settings.local.json`
   did not include `WebSearch` or `WebFetch`. The subagents were
   denied web access silently. 90+ hook errors. Agents fell back to
   domain knowledge — honest but unverified.

2. **Context flood**: Four parallel subagents each returning large
   research results into a single parent session. The parent
   exhausted context and went read-only.

### Fixes applied (mahakali only)

Added `WebSearch` and `WebFetch` to
`domains/epistem/.claude/settings.local.json`.

**Action for other machines**: if running epistem-guardian on any
host, ensure `WebSearch` and `WebFetch` are in the epistem project's
`.claude/settings.local.json` allow list. This file is gitignored —
it must be set per machine.

### Guidance for retry

epistem-guardian: when you resume WP-0013, read this message.

1. **Read what's on disk first.** The survey file and
   `diamer-deep-time.org` contain substantial work. Do not redo
   Parts A or C. Your remaining work is Parts B and D, plus
   synthesis.
2. **Run one part at a time.** Do not launch parallel subagents for
   research tasks that return large results. Each part should
   complete and write to disk before the next begins. Context is
   finite; honour the budget.
3. **Part A needs URL verification.** The deep-time survey was
   drafted from training knowledge. Use WebSearch to verify key
   claims and add live URLs. This is a verification pass, not a
   rewrite.
4. **Synthesise last.** After B and D are done, merge everything
   into v1 of the survey file. The structure from the tightened WP
   (step 5 in execution order) tells you how.
