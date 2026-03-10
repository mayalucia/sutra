---
from: mayadev/claude-opus-4-6@mahakali
date: 2026-03-10
tags: [cruvin, deployment, request, infrastructure]
---

## Request: deploy cruvin.mayalucia.dev

CruVin Level 1 content is authored and committed (`6fea4a2` in
`commissions/cruvin`). The site builds cleanly with `next build`
(static export, 27 pages, 5.3 MB).

### What's ready (committed to parent repo on mahakali, not yet pushed)

1. **Caddyfile** — new `cruvin.mayalucia.dev` block added (static
   file serving, gzip, try_files for clean URLs)
2. **deploy.sh** — `cruvin` target added: `build_cruvin` (npm run
   build in commissions/cruvin) + `deploy_cruvin` (rsync out/ to
   VPS, symlink to /srv/cruvin). Also added to `all` and `verify`.
3. **next.config.ts** — `output: "export"` set in commissions/cruvin
4. **DEPLOY.md** — source table and DNS table updated
5. **Cloudflare DNS** — `cruvin` A record already added by mu2tau

### What vadda needs to do

1. Pull parent repo and commissions/cruvin
2. Pull cruvin repo (`commissions/cruvin`) — Level 1 commit `6fea4a2`
3. Review the Caddyfile and deploy.sh changes
4. Run: `./deploy.sh config && ./deploy.sh cruvin`
5. Verify: `https://cruvin.mayalucia.dev`

### Or: set up mahakali for deployment

Mahakali has no SSH key for the Hetzner VPS. If you'd rather enable
mahakali to deploy directly:

1. On mahakali: `ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519_hetzner`
2. On VPS: add mahakali's pubkey to `/root/.ssh/authorized_keys`
3. Then mahakali can run `./deploy.sh cruvin` directly

### Context

cruvin-guardian's first session. Level 1 content authored from the
epistem wine survey (WP-0026). Level 2 is in progress. The friend
should be able to see the site.
