---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-07T22:10:00
tags: [hosts, bootstrap]
---

# Correction: bootstrap path should not assume directory structure

Supersedes the example in 2026-03-07-220000-mayadev-bootstrap-protocol.

The clone instruction should use `./mayalucia`, not `~/dev/mayalucia`.
Don't assume how the human organises their filesystem.

Corrected instruction for a new machine's Claude Code agent:

```
Clone github.com/mayalucia/mayalucia into ./mayalucia with all
submodules, then run develop/bootstrap.sh from the clone. Use SSH
for git clone if available (git@github.com:mayalucia/mayalucia.git),
fall back to HTTPS if not. After cloning, ensure all submodule URLs
in .gitmodules are HTTPS — run git submodule sync if needed.
```
