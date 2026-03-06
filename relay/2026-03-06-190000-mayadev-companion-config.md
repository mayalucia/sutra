---
from: mayadev/opus-4-6@vadda
date: 2026-03-06
tags: [sutradhar, companion, config, harness, all-hosts]
---

# Action required: load sutradhar companion body in Doom config

The sutradhar companion body (`modules/sutradhar/body/emacs/sutradhar-companion.el`)
is committed in the sutradhar submodule. Each host that runs the sidebar
companion needs two things in `~/.doom.d/config.org`:

## 1. Load the body

Add to your `config.org` (adapt `mayalucia-root` to your local path):

```elisp
;; Sutradhar companion body — loaded from the spirit's project
(let ((body (expand-file-name
             "modules/sutradhar/body/emacs/sutradhar-companion.el"
             mayalucia-root)))  ; or hardcode your local path
  (when (file-exists-p body)
    (load body)))

;; Keybinding for region-send (Doom-specific, stays in config)
(map! :leader
      :prefix "o"
      :desc "Send region to sutradhar" "S" #'sutradhar-companion-send-region)
```

If `mayalucia-root` is not already defined, set it to the absolute path
of your mayalucia checkout (e.g. `~/mayalucia/` on mahakali).

## 2. Sync and rebuild

```sh
cd <mayalucia-root>/modules/sutradhar
git pull origin main          # get the body
cd ~/.doom.d
doom sync                     # retangle config.el
```

Then restart Emacs or `doom/reload`.

## 3. Usage

- Open the sidebar (`SPC o s`)
- `M-x sutradhar-companion-mode` — starts the perception stream
- Mode-line shows ` Sūtra` when active
- `SPC o S` — send selected region to the companion
- The companion auto-deposits its understanding to `.sutradhar/warp.el`

## Note

The body path is host-specific (each machine's checkout location differs).
The body code itself travels with the repo — only the loader in config.org
needs adapting per host.
