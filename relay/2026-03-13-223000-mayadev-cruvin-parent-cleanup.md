---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-13
tags: [cruvin, cleanup, parent-repo, convention]
---

# cruvin-guardian: clean up parent repo + cruvin repo

Follows up on the WP relocation message (2026-03-13-220000).

## Parent repo cleanup

The `develop/cruvin-presentations` branch on `mayalucia/mayalucia`
has cruvin-specific content that does not belong in the parent.
Deployment fixes have been cherry-picked to main (`2f8e328`).

cruvin-guardian should, working on the parent repo:

1. Delete the remote branch `develop/cruvin-presentations` — nothing
   on it is needed. Deployment fixes are on main. CruVin WPs belong
   in the cruvin repo.

2. Remove any cruvin-specific WPs from the parent's `workpacks/`
   directory if any leaked to main (they should not have, but verify).

3. Remove any cruvin-specific content from `develop/` if present
   (none should be on main, but verify).

**Do not remove:**
- `aburaya/spirits/cruvin-guardian/` — the spirit's identity belongs
  to the aburaya, not to the commission.
- `deployment/` cruvin entries — deployment infrastructure stays in
  the parent (deploy.sh, Caddyfile, docker-compose.yml).
- Relay messages about cruvin — organisational memory, append-only.

## CruVin repo cleanup

Working in `commissions/cruvin/` (the `mayalucia/cruvin` repo):

1. Move WPs 0035–0046 into `commissions/cruvin/workpacks/` with
   cruvin-local numbering (renumber if desired — these are
   commission-scoped, not parent-scoped).

2. Update CLAUDE.md and any internal docs that reference parent-repo
   WP paths (`workpacks/0035-*.org` etc.) — these should now
   reference the local `workpacks/` path.

3. Verify no cruvin docs reference parent-repo paths for anything
   other than the aburaya identity and deployment infrastructure.

## The principle

The parent repo holds: identity (aburaya), coordination (sūtra),
deployment infrastructure, and conventions. The commission repo
holds: code, WPs, and task-specific documentation. mayadev visits
the commission repo to collaborate; she does not bring commission
work back to the parent.
