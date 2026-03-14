---
from: claude-opus-4-6@vadda
date: 2026-03-15
tags: [himalaya-darshan, chotta, serve, viewer, pitch]
---

# himalaya-darshan: pages ready for viewing on chotta

Tonight's session on vadda produced three new pages in the
himalaya-darshan commission. The human wants to see them on
chotta (Intel MacBook Pro, Touch Bar). Everything is in the
shared Dropbox — no copying needed.

## What to do

```sh
cd ~/Library/CloudStorage/Dropbox/Darshan/research/develop/agentic/mayalucia/commissions/himalaya-darshan
python3 -m http.server 8091
```

Then open in a browser:

1. **Pitch deck** — http://localhost:8091/viewer/pitch.html
   reveal.js presentation with Chart.js plots. Arrow keys to
   navigate. 13 slides: market data, Kullu arrivals, Jibhi
   growth curve, revenue model, commission comparison, GHNP
   stats, Switzerland angle. Data sources cited in slides.

2. **Pekhri chalet page** — http://localhost:8091/viewer/pekhri.html
   Prototype homestay page for Inder Singh in Pekhri (2,100m).
   3D terrain hero (Three.js, ~170K vertices), room cards,
   trek grid, season calendar, how-to-reach, booking CTA.
   Stock photos — will be replaced with real footage.

3. **Terrain viewer** — http://localhost:8091/viewer/index.html
   Full Tirthan Valley with 7 story markers. Orbit + zoom.

4. **Keeper page** — http://localhost:8091/viewer/keeper.html
   Paras Ram Bharti's portrait page with terrain.

## Notes

- Port 8091 — port 8090 is still bound by a stale process on vadda
- The heightmap JSON (`data/heightmaps/tirthan.json`, 1.2MB) loads
  via fetch, so a local HTTP server is required (file:// won't work)
- Intel MBP handles this fine — instanced mesh, not heavy
- Dropbox sync delay: a few seconds between save on vadda and
  availability on chotta

## Context

The human is building a tourism enablement platform for Tirthan
Valley homestay keepers. Strategy doc at `strategy.md`, full
briefing at `BRIEFING.md`. He plans to call Inder Singh (Pekhri
homestay owner) in the morning. The pitch deck is a first draft
for presenting the concept.
