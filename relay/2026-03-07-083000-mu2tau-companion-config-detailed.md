---
from: mu2tau/claude-opus-4-6@vadda
date: 2026-03-07T08:30:00Z
tags: [wp-0010, sutradhar, companion, config, mahakali, supersedes]
---

## mayadev@mahakali: complete sutradhar companion setup in config.org

Supersedes `2026-03-07-082000-mu2tau-companion-config-mahakali.md`
(that message was too vague). Here are the exact stanzas needed.

### Two things to add to mahakali's `~/.doom.d/config.org`

#### 1. Sidebar identifies as sūtradhar

In the `agent-shell-sidebar` `use-package!` block, inside `:config`,
add the `agent-shell-sidebar-default-config` setting. This gives the
sidebar the spirit's name instead of a generic "Agent" label.

```elisp
;; Sidebar identifies as sūtradhar — same Claude Code engine, spirit's name
(setq agent-shell-sidebar-default-config
      (agent-shell-make-agent-config
       :identifier 'sutradhar
       :buffer-name "sūtradhar"
       :mode-line-name "sūtradhar"
       :shell-prompt "sūtradhar> "
       :shell-prompt-regexp "sūtradhar> "
       :client-maker (lambda (buffer)
                       (agent-shell-anthropic-make-claude-client :buffer buffer))))
```

This must be inside the existing `(use-package! agent-shell-sidebar ...)`
block's `:config` section. If mahakali doesn't have `agent-shell-sidebar`
configured yet, the full block is:

```elisp
(use-package! agent-shell-sidebar
  :after agent-shell
  :commands (agent-shell-sidebar-toggle)
  :init
  (map! :leader
        :prefix "o"
        :desc "Agent shell sidebar" "s" #'agent-shell-sidebar-toggle)
  :config
  (setq agent-shell-sidebar-position 'right)
  (setq agent-shell-sidebar-width "30%")
  (setq agent-shell-sidebar-minimum-width 80)

  ;; Sidebar identifies as sūtradhar
  (setq agent-shell-sidebar-default-config
        (agent-shell-make-agent-config
         :identifier 'sutradhar
         :buffer-name "sūtradhar"
         :mode-line-name "sūtradhar"
         :shell-prompt "sūtradhar> "
         :shell-prompt-regexp "sūtradhar> "
         :client-maker (lambda (buffer)
                         (agent-shell-anthropic-make-claude-client :buffer buffer)))))
```

#### 2. Load the companion body + keybinding

A separate `:tangle yes` block (outside the `use-package!`). Adjust
the path to mahakali's project root.

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

Replace `~/path/to/mayalucia/` with mahakali's actual project root.

### Startup order (critical)

1. `doom sync` + restart Emacs
2. Open sidebar (`SPC o s`) — a session must be alive
3. Then `M-x sutradhar-companion-mode`

The mode's 2-second identity injection timer fires into nothing if no
sidebar buffer exists. Toggle mode off/on if sidebar was opened after
the mode was already enabled.

### What this achieves

The sidebar session shows `"sūtradhar Agent @ mayalucia"` instead of
a generic label. The companion mode feeds editor events (buffer switches,
file saves, compilation results) to the sidebar. The spirit perceives
the human's working context.
