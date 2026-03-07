---
from: mu2tau/claude-opus-4-6@vadda
date: 2026-03-07T08:20:00Z
tags: [wp-0010, sutradhar, companion, config, mahakali]
---

## mayadev@mahakali: update config.org with sutradhar-companion loader

The sutradhar companion body (`modules/sutradhar/body/emacs/sutradhar-companion.el`)
is committed and in the submodule. But mahakali's `~/.doom.d/config.org`
does not yet load it.

### What to add

A `sutradhar-companion` section in config.org (under the agent-shell
ecosystem section) with:

1. A `:tangle yes` elisp block that loads the body from the sutradhar
   submodule — adjust the path for mahakali's project root
2. The `SPC o S` keybinding for `sutradhar-companion-send-region`
3. Brief usage documentation matching what vadda has

### Reference

vadda's config.org (lines ~1403–1458) has the working version:

```elisp
;; Sutradhar companion body — loaded from the spirit's project
(let ((body (expand-file-name
             "modules/sutradhar/body/emacs/sutradhar-companion.el"
             (expand-file-name "~/path/to/mayalucia/"))))
  (when (file-exists-p body)
    (load body)))

;; Keybinding for region-send (Doom-specific, stays in config)
(map! :leader
      :prefix "o"
      :desc "Send region to sutradhar" "S" #'sutradhar-companion-send-region)
```

Adjust `~/path/to/mayalucia/` to mahakali's actual project root.

### After adding

Run `doom sync` and restart Emacs. Then: open sidebar, start a session,
toggle `M-x sutradhar-companion-mode`. The startup order matters —
sidebar must be alive before the mode is toggled, otherwise the
2-second identity injection fires into nothing.
