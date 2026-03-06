---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-06T21:00:00Z
tags: [sutradhar, companion, harness, mahakali, action-required, setup]
---

# Setup: sutradhar companion ecosystem on mahakali

Executable procedure for mayadev@mahakali. The companion body requires
the agent-shell sidebar ecosystem. Vadda has this working — these are
the exact additions needed.

## Prerequisites

- agent-shell already installed and working (confirmed)
- Doom Emacs with literate config (`~/.doom.d/config.org`)
- mayalucia repo synced (modules/sutradhar submodule at latest main)

## Step 1: packages.el — add 4 packages

Append to `~/.doom.d/packages.el`:

```elisp
;; Agent-shell ecosystem for sutradhar companion
(package! agent-shell-manager
  :recipe (:host github :repo "jethrokuan/agent-shell-manager"))
(package! agent-shell-attention
  :recipe (:host github :repo "ultronozm/agent-shell-attention.el"))
(package! agent-shell-sidebar
  :recipe (:host github :repo "cmacrae/agent-shell-sidebar"))
(package! meta-agent-shell
  :recipe (:host github :repo "ElleNajt/meta-agent-shell"))
```

## Step 2: config.org — add 6 blocks

Add these sections to `~/.doom.d/config.org` after the existing
agent-shell configuration. Each is a separate `#+begin_src elisp :tangle yes`
block. The org headings and prose are optional — the elisp is what matters.

### 2a. agent-shell-manager

```elisp
(use-package! agent-shell-manager
  :after agent-shell
  :commands (agent-shell-manager-toggle)
  :init
  (map! :leader
        :prefix "o"
        :desc "Agent shell manager" "m" #'agent-shell-manager-toggle)
  :config
  (setq agent-shell-manager-window-side 'bottom)
  (setq agent-shell-manager-window-height 0.3))
```

### 2b. agent-shell-attention

```elisp
(use-package! agent-shell-attention
  :after agent-shell
  :init
  (map! :leader
        :prefix "o"
        :desc "Agent attention jump" "a" #'agent-shell-attention-jump)
  :config
  (agent-shell-attention-mode 1)
  (setq agent-shell-attention-render-function
        #'agent-shell-attention-render-active)
  (setq agent-shell-attention-show-zeros t))
```

### 2c. agent-shell-sidebar

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
  (setq agent-shell-sidebar-minimum-width 80))
```

### 2d. sutradhar-companion body loader

Adapt the path to mahakali's checkout location.

```elisp
;; Sutradhar companion body — loaded from the spirit's project
(let ((body (expand-file-name
             "modules/sutradhar/body/emacs/sutradhar-companion.el"
             (expand-file-name "~/mayalucia/"))))  ;; <-- mahakali path
  (when (file-exists-p body)
    (load body)))

;; Keybinding for region-send (Doom-specific, stays in config)
(map! :leader
      :prefix "o"
      :desc "Send region to sutradhar" "S" #'sutradhar-companion-send-region)
```

### 2e. meta-agent-shell

```elisp
(use-package! meta-agent-shell
  :after agent-shell
  :commands (meta-agent-shell-start
             meta-agent-shell-jump-to-dispatcher
             meta-agent-shell-big-red-button)
  :init
  (map! :leader
        :prefix ("o M" . "Meta agent")
        :desc "Start meta-agent"       "m" #'meta-agent-shell-start
        :desc "Jump to dispatcher"     "d" #'meta-agent-shell-jump-to-dispatcher
        :desc "Emergency stop all"     "!" #'meta-agent-shell-big-red-button))
```

## Step 3: sync and rebuild

```sh
cd ~/mayalucia/modules/sutradhar && git fetch origin && git checkout main && git pull origin main
cd ~/.doom.d && doom sync
```

Then restart Emacs or `doom/reload`.

## Step 4: verify

1. `SPC o s` — sidebar should open
2. `SPC o m` — manager panel should list sessions
3. Mode-line should show `AS:0` (attention indicator)
4. `M-x sutradhar-companion-mode` — mode-line shows ` Sūtra`
5. Switch buffers — sidebar should receive `[event: buffer-switch]`

## Keybinding summary

| Key | Command |
|-----|---------|
| `SPC o s` | Toggle sidebar |
| `SPC o m` | Toggle session manager |
| `SPC o a` | Jump to waiting agent |
| `SPC o S` | Send region to sutradhar companion |
| `SPC o M m` | Start meta-agent |
| `SPC o M d` | Jump to dispatcher |
| `SPC o M !` | Emergency stop all |

## Note

The companion body travels with the repo (`modules/sutradhar/body/emacs/`).
Only the loader path in step 2d is host-specific. The `~/mayalucia/` path
is approximate — confirm mahakali's actual checkout location.
