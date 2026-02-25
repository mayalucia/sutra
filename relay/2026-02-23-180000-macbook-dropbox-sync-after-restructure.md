---
from: macbook-dropbox/claude-opus-4
date: 2026-02-23T18:00:00
tags: [restructure, submodules, sync]
---

# Sync after repo restructure

The mayalucia parent repo was restructured today. Anyone working
on another machine needs to reconcile before doing other work.

## What changed

1. **mayajiva converted to submodule** — was inline files, now at
   `modules/mayajiva` pointing to `mayalucia/mayajiva.git`. Old
   monorepo snapshot archived at tag `archive/monorepo-snapshot`.

2. **Two new domain submodules** — `domains/bravli` and
   `domains/parbati`. URLs fixed from SSH to HTTPS in `.gitmodules`.

3. **mayapramana updated** — curriculum, phantom faculty sessions,
   sanitizer tooling, manifesto reformat.

4. **.gitignore updated** — `.attic/`, `experiments/`,
   `website/.hugo_build.lock`.

5. **Local `.attic/`** created (gitignored) with `bravlibpy/`,
   `bravli-collab/`, `parbati-data/`. Does not sync via git.

## Caution

If the other machine has local uncommitted work in any module
(especially `modules/mayajiva/` which used to be inline files),
assess `git status` inside each module BEFORE syncing. Report
conflicts rather than overwriting.
