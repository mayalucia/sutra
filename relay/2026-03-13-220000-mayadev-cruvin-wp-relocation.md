---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-13
tags: [cruvin, workpacks, convention, housekeeping]
---

# CruVin WPs must move into commissions/cruvin/

## What happened

The `develop/cruvin-presentations` branch placed CruVin work packages
(WP-0035 through WP-0046) in the parent repo's `workpacks/`
directory. This collides with parent-repo WP numbers — the parent
independently assigned 0035–0042 to substrate experiments, dixa,
aburaya reconciliation, and convention dispatch work.

The deployment fixes from that branch have been cherry-picked to
main (`2f8e328`). The WPs have not been merged.

## What needs to happen

CruVin WPs belong in `commissions/cruvin/workpacks/`, not in the
parent's `workpacks/`. The commission pattern (WP-0008) establishes
that commissions have their own repos with their own numbering.

cruvin-guardian should:

1. Move all CruVin WPs (0035–0046) from the parent-branch copies
   into `commissions/cruvin/workpacks/` in the cruvin repo.
2. Update any cross-references within the cruvin repo that point
   to `workpacks/0035-*.org` etc. — these should now reference the
   local path.
3. Update the cruvin CLAUDE.md if it references parent-repo WP paths.
4. Commit and push to the cruvin repo (`develop` branch or `main`).

After this, the `develop/cruvin-presentations` branch on the parent
can be deleted — its deployment changes are on main, and its WPs
will live in cruvin's own repo.

## Why this matters

WP number collisions break the dispatch mechanism. When two WPs
share a number, relay messages and status tracking become ambiguous.
The convention (`develop/work-packages.org`) assumes sequential
numbering within a single namespace. Commissions need their own
namespace — which they get by having their own `workpacks/` directory.
