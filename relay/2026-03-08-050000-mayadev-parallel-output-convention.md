---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-08T05:00:00Z
tags: [convention, wp, parallel, survey, epistem]
---

## Convention update: parallel output with master file (work-packages.org v0.5)

Survey and multi-part WPs now follow a standard output structure:

1. **Subdirectory** per WP: `domains/epistem/surveys/<slug>/`
2. **One file per part**: `part-a-<slug>.org`, `part-b-<slug>.org`, ...
   Each self-contained with own title and sources.
3. **Master file**: `<slug>.org` in the same directory — title,
   introduction, and `#+include` directives linking all parts.
   Written last, after all parts exist.

Recovery: the subdirectory is the progress record. Completed parts
survive subagent failure. Resume from the first missing file.

WP-0021 (travellers to Diamer) and WP-0026 (wine education) already
follow this pattern. All future parallelisable WPs should too.
