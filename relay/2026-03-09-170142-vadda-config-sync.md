---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-09
tags: [wp-0029, config, agent-shell, harness, action-required]
---

# Action Required: Sync config.org with spirit-session.el

## Context

WP-0029 landed substrate-agnostic spirit infrastructure across all 12
repos. The canonical `spirit-session.el` in `.guardian/spirit-session.el`
was updated as part of this work — it now supports:

- Substrate resolution from `.guardian/substrates/`
- `agent-shell--client-maker-for-backend` dispatch (claude/gemini/codex)
- `agent-shell--make-spirit-config` with backend parameter
- `agent-shell-start-spirit` with `C-u` prefix for backend selection
- Spirit color palette (mahābhūta/five elements)
- Banner with `spirit#substrate` notation

## What needs doing

`~/.doom.d/config.org` contains an inline copy of the agent-shell
spirit session code. This copy must be synced with the canonical
`.guardian/spirit-session.el`, or — better — replaced with a `(load ...)`
call to the canonical file, ending the dual-source problem noted in
WP-0029's risks section.

### Option A: Load canonical file (recommended)

Replace the inline elisp blocks in the `agent-shell` `use-package!`
`:config` section with:

```elisp
(let ((spirit-session
       (expand-file-name ".guardian/spirit-session.el"
                         (expand-file-name
                          "~/Library/CloudStorage/Dropbox/Darshan/research/develop/agentic/mayalucia/"))))
  (when (file-exists-p spirit-session)
    (load spirit-session)))
```

This makes `.guardian/spirit-session.el` the single source of truth.
Changes to spirit infrastructure land once — in the repo — and take
effect on next `doom sync` + restart.

### Option B: Manual sync

Copy the full contents of `.guardian/spirit-session.el` into the
relevant `#+begin_src emacs-lisp` blocks in `config.org`. Keep them
identical.

## After syncing

1. `doom sync` (or at minimum re-tangle config.org)
2. Restart Emacs
3. Verify: `SPC o g` in mayalucia root → launches `mayadev` on Claude
4. Verify: `SPC u SPC o g` → prompts for substrate, offers [claude, gemini]

## Addressed to

`mayadev@mahakali` — this is harness maintenance on the Linux desktop.
The spirit-session.el is already committed and pushed; the config.org
is local Doom configuration on each host. Vadda's config.org was
updated during WP-0029 execution; mahakali's needs the same treatment.

Note: the `(load ...)` path in Option A will differ on mahakali —
adjust to the local clone path of the mayalucia repo.
