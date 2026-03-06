---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-06T22:00:00Z
tags: [convention, stories, develop, all-spirits]
---

# New convention: story development workspaces

`develop/story-development.org` v0.1 is committed. This formalizes
how stories are developed — the same kind of convention document as
`develop/work-packages.org`.

## What changed

**Story workspaces** now live at `stories/<slug>/` (top-level, parallel
to `workpacks/`). Each workspace has:

- `notes.org` — development record (origin, plan, voice refs, continuity)
- `keys.org` — translation keys introduced by that story
- `generate_images.py` — PEP 723 illustration script

Optional: `research.org` (links to epistem surveys), `draft.org`.

**The global translation table** — 40+ keys across 12 stories, organized
by story of origin with provenance — is now version-controlled in the
convention document. Previously lived only in agent memory. The inline
table in `story-compose.md` has been replaced with a pointer.

**Published artifacts stay in Hugo** — `website/content/writing/<slug>.md`
and `website/static/images/writing/<slug>/`. The workspace is the
development record; Hugo is the deployable.

## What this means for spirits

- `story-compose` power now references `develop/story-development.org`
  for the translation table (not its own inline copy)
- `bedtime-story` skill paths updated from the old deep location to
  `stories/<slug>/`
- Historical stories (1–12) remain in `collab/sessions/devprocess/sutra-genesis/`
  — not migrated

## For mahakali

The sidebar config now supports naming the sidebar as "sūtradhar"
instead of "Claude Code". The `agent-shell-sidebar-default-config`
customization is in vadda's config.org — add the equivalent to
mahakali's. See the `agent-shell-sidebar` block: it uses
`agent-shell-make-agent-config` with `:buffer-name "sūtradhar"`.

## First use

Story #13 (Diamer / Nanga Parbat) will be the first story developed
under this convention. WP-0013 (deep survey) is the research phase;
the story WP follows after the homework.
