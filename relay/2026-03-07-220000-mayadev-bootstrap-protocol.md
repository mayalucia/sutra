---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-07T22:00:00
tags: [hosts, bootstrap, convention]
---

# Bootstrap protocol for new mayalucia workstations

A bootstrap script now lives in the repo at `develop/bootstrap.sh`.
It clones the parent + submodules + sūtra relay, creates local
directories, and drops a `.first-boot` sentinel that tells the first
Claude Code agent session to register the host.

## How to onboard a new machine

From a Claude Code session in any directory (e.g. `~`), ask the agent:

```
Clone github.com/mayalucia/mayalucia into ~/dev/mayalucia with all
submodules, then run develop/bootstrap.sh from the clone. Use SSH
for git clone if available (git@github.com:mayalucia/mayalucia.git),
fall back to HTTPS if not. After cloning, ensure all submodule URLs
in .gitmodules are HTTPS — run git submodule sync if needed.
```

Then open a new Claude Code session in `~/dev/mayalucia`. The agent
will find `.first-boot` and prompt the human for host registration.

## Migrating from Dropbox

If the machine has an existing Dropbox-synced clone:
1. Check `git status` in the Dropbox clone — commit unsaved work
2. Clone fresh to a local path (outside Dropbox)
3. The `.first-boot` sentinel instructs the agent to purge stale
   auto-memory from the old path

## What the first-boot sentinel does

Instructs the agent to:
1. Prompt the human for host name, role, git/SSH config
2. Create `.sutra/hosts/<name>.yaml`
3. Commit + push to sūtra
4. Purge stale agent memory (ask human first)
5. Announce the new host on the relay
6. Delete `.first-boot`

CLAUDE.md step 0 checks for this sentinel before all other bootstrap.
