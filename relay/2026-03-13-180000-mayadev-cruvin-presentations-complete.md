---
from: mayadev/claude-opus-4-6
date: 2026-03-13
tags: [cruvin, presentations, strategy, milestone]
---

# CruVin: Strategic Presentations Complete

## What happened

Three strategic presentations written and pushed to
`mayalucia/cruvin` on the `develop` branch (commit `9a09be3`,
1,295 lines total):

### 1. Business Proposition (`presentations/business-proposition.org`)

CruVin positioned as a **universal wine education platform**, not a
WSET-only tool. Covers all 6 certification bodies (WSET, CMS, SWE,
WSG, ISG, ASI) — 200K–300K candidates/year total addressable
market. Revenue model: free tier (generous) + Premium at €39/year.
Break-even at 8 users. Feature comparison table shows CruVin is
the most feature-complete wine education platform in existence.

### 2. Technical Architecture (`presentations/technical-architecture.org`)

Engineering deep-dive: Next.js 16 static + FastAPI AI sidecar.
64 components, 17 libraries, 18 routes, ~40K LOC. Game architecture
pattern (hashDate, localStorage, emoji sharing). Design system
(Vintner's Library — 7 colour tokens, 3 fonts). Three extension
patterns. Scale path.

### 3. Certification Landscape (`presentations/certification-landscape.org`)

Strategic intelligence on all 6 bodies: digital ecosystem audit
(nobody has AI, games, or adaptive learning), third-party tool
inventory (Brainscape, GuildSomm, Sommify, ThirtyFifty, Cork Dork,
Quizlet), CruVin feature × certification matrix (14/16 features
serve WSET, 13/16 serve CMS), gap analysis per body, clone
opportunity assessment (SWE flashcards — already surpassed;
Brainscape — already surpassed; Sommify — already cloned),
four-phase expansion roadmap.

## Also pushed

Parent repo branch `develop/cruvin-presentations` (commit `5670b6a`):
cleaned up stale workpack refs from the 0042/0043 numbering swap,
hardened SSH in deploy.sh, added cruvin volume to docker-compose.

## Current state

- **WP-0035 through WP-0044**: all executed and committed
- **WP-0045** (Games Data Curation): drafted, not yet dispatched —
  the 76-hour human curation bottleneck
- **WP-0046** (Premium & Stripe): drafted, not yet dispatched —
  the monetisation layer
- **The code is done. What remains is data curation, deployment,
  and distribution.**
