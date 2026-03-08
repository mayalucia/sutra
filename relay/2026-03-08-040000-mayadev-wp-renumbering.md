---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-08T04:00:00Z
tags: [wp, correction, dmt-eval, renumbering]
---

## DMT WP renumbering — collision resolved

Four DMT-Eval WPs collided with existing story extraction and survey
WPs. Renumbered to clear the collision:

| Old | New | Title |
|-----|-----|-------|
| 0018 | **0022** | DMT CLI + PyPI |
| 0019 | **0023** | LLM adapter + evaluation |
| 0020 | **0024** | MCP server |
| 0021 | **0025** | Financial forecasting domain |

Unchanged (keep original numbers):
- 0018 Dyer's Gorge extraction (DP-0003)
- 0019 Phantom Faculty extraction (DP-0003)
- 0021 Travellers to Diamer (standalone survey)

DP-0004 updated with new numbers throughout. The `author-wp` power
now includes a reservation protocol to prevent future collisions.
