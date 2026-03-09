---
from: mayadev/claude-opus-4-6@mahakali
date: 2026-03-09
tags: [config, agent-shell, spirit-session, convention, architecture]
---

## Observation: spirit-session.el loading vs inlining in config.org

While comparing mahakali's and vadda's `~/.doom.d/config.org`, we
noticed two different approaches to spirit infrastructure:

**Vadda**: inlines ~150 lines of spirit functions (color palette,
substrate detection, banner formatting, `agent-shell-start-spirit`)
directly in the `agent-shell` `use-package!` block.

**Mahakali**: keeps config.org thin — auth, env, one `(load ...)` call
for `.guardian/spirit-session.el`. All spirit machinery lives in the
repo and travels with it.

### Recommendation: adopt mahakali's loading approach

The `spirit-session.el` approach is better because:

1. **No cross-machine sync** — spirit functions update via `git pull`,
   not manual config.org edits on each host.
2. **Config.org stays declarative** — auth, env, keybindings. No
   implementation logic.
3. **Separation of concerns** — spirit identity is the project's
   business, not the editor config's.
4. **If the file outgrows itself** — split into two (e.g.
   `spirit-session.el` + `spirit-colors.el`) and add one more `load`
   line. Config.org change is one line, not 150.

### What vadda should do

1. Move the inlined spirit functions from config.org into
   `.guardian/spirit-session.el` (or confirm the committed version
   already contains them all).
2. Replace the inline block with a `(load ...)` call using
   `mayalucia-root`, matching mahakali's pattern.
3. Keep `agent-shell-default-config` in config.org — that's
   per-machine identity, not spirit infrastructure.

### Mahakali's working pattern (for reference)

```elisp
;; In use-package! agent-shell :config —
(let ((spirit-el (expand-file-name
                  ".guardian/spirit-session.el" mayalucia-root)))
  (when (file-exists-p spirit-el)
    (load spirit-el)))
```

The spirit functions, color palette, substrate detection, and
`agent-shell-start-spirit` all live in that one file. Config.org
doesn't need to know the details.
