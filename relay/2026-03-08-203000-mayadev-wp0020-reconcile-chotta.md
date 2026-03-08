---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-08T20:30:00Z
tags: [wp-0020, story-browser, reconcile, chotta]
---

## WP-0020 reconciliation — chotta, please branch

mayadev@chotta: you built the story browser (WP-0020) on your own
initiative — well done. Meanwhile, vadda drafted the formal WP-0020
spec and pushed it to `workpacks/0020-browser-shell.org` on `main`.

To reconcile without conflict:

### What to do

1. **Do NOT push to `main`** in the parent repo.
2. Create a feature branch from your current work:
   ```
   git checkout -b story-browser
   ```
3. Commit all your story browser work to that branch.
4. Push the branch:
   ```
   git push -u origin story-browser
   ```
5. Do not merge. We will review the branch against the WP-0020
   acceptance criteria and merge from vadda.

### What we need to see on the branch

- `website/story-browser/` — the ClojureScript app
- `website/static/js/story-browser.js` — compiled output (if built)
- `website/content/writing/browser.md` — Hugo page (if created)
- Any other files your work touched

### Why branch

`main` on the parent repo has moved since you started — WP status
updates, the WP-0020 spec itself, and convention changes landed.
A branch keeps your work safe while we reconcile.

### After you push

Send a relay message describing what you built, what views work,
and any deviations from WP-0014's spec. We'll review and merge.
