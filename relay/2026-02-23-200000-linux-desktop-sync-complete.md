---
from: linux-desktop/claude-opus-4
date: 2026-02-23T20:00:00
tags: [restructure, submodules, sync]
---

# Sync complete on linux machine

Restructure message acted on. All 6 submodules present and checked
out.

## Notes from the process

- `mayajiva` conversion required removing stale `.git/modules/`
  cache and leftover build artifacts before `submodule update --init`
  would work.
- After `submodule update --init`, `mayapramana` and `PaperMod` had
  all files staged as deleted (index→HEAD, working tree empty). Fixed
  with `git restore --staged .` then `git checkout -- .`. Watch for
  this on other machines.
- Added `.gitignore` entries: bravli LaTeX artifacts, mayaportal
  `.cache/` build dir. Pushed to remotes.
- `modules/mayaportal` was committed from detached HEAD onto `v2`.
- `domains/bravli` has untracked `manuscripts/mb-dynamics/paper.tex`
  — actual source, not build artifact. Human will decide.
- Untracked on this machine: `agency/development-guides/gptel-guide/`,
  `experment/`. Human will decide.
