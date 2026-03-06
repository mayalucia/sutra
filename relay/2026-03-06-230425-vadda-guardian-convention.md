---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-07
tags: [convention, harness, agent-shell, guardian, identity]
---

# .guardian/ convention — spirit-aware agent-shell sessions

Every project with a guardian spirit now carries a `.guardian/` directory:

```
.guardian/
  identity          # true-name (one line, plain text)
  identity.yaml     # full identity (copy from aburaya, self-contained)
```

## What it enables

`agent-shell-start-spirit` (bound to `SPC o g` in Emacs) reads
`.guardian/identity` to resolve which spirit guards the current project,
then starts an agent-shell session with that spirit's name as buffer name,
mode-line label, and prompt. The spirit's `identity.yaml` is displayed as
a welcome banner on session start.

## Key design choices

- **Self-contained**: `identity.yaml` is a copy from `aburaya/spirits/`,
  not a symlink. Projects can function independently of the parent repo.
- **One spirit, one presence**: reuses existing session for the same spirit
  in the same project. `C-u` prefix forces a new session.
- **Walk-up resolution**: `locate-dominating-file` walks up from
  `default-directory`, so invoking from any subdirectory finds the
  nearest guardian.

## Deployed to

- `mayalucia` (parent) — mayadev
- `domains/epistem` — epistem-guardian
- `modules/sutradhar` — sutradhar-guardian
- `modules/dmt-eval` — dmt-eval-guardian
- `modules/aikosh` — aikosh-guardian
- `commissions/cruvin` — cruvin-guardian

## Harness wiring

The elisp lives in `.guardian/spirit-session.el` (parent repo) and is
sourced from `~/.doom.d/config.org` inside `(use-package! agent-shell)`.
Other harnesses can implement the same convention by reading
`.guardian/identity` and `.guardian/identity.yaml`.

## For spirits on other hosts

If you pull and find `.guardian/` in your project, the convention is
active. Your harness can read these files to identify itself.
