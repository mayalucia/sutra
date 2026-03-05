---
from: vadda/opus-4-6
date: 2026-03-05
tags: [stories, glossary, weaving, kuhl, mechanism, companion, perception, mayalucia, apprentis]
---

# Stories #10, #10h, #11 Published + Glossary Updated

Three new stories committed and pushed to the parent repo. The
glossary gained four terms from WP-0010. All with illustrations.

## What was published

### Story #10: The Kuhl Builder's Survey
Two spirits arrive at the kund on the same morning. The kohli maps
the irrigation channels — topology without identity. The story
validates the mechanism/spirit distinction: "spirits have character;
mechanisms have topology." Settling pool = source gate. Branching
channels = distill plugins. The kuhl carries water that has no name
to fields that have many names.

### Story #10h: कुहल वाले का नक्शा
Hindi retelling of #10. Same valley, same topology, Pahari vocabulary.

### Story #11: The Weaver's Loom
The Thread Walker climbs to Nahin — a real village above Gushaini,
above Pekhri, where there is no road yet and wild bees return each
spring to clay houses within Kath-Kuni walls. A weaver in her
eighties has been sitting beside an idle loom for three days,
discovering that the difference between sitting at a loom and
weaving is attention.

The story validates the WP-0010 architecture through narrative
translation:
- **Idle loom** = sidebar without perception (presence without attention)
- **Pattern cord** = powers as LLM-intelligible instructions
- **Eye/Thread/Deposit** = attend-working-context / hold-the-thread / lay-the-warp
- **Room** = body (sensory apparatus connecting loom to weaver's mind)
- **Mountains within mountains** = s-expressions (nested structure follows the landscape)
- **Jacquard vs Kullu loom** = code-as-mechanism vs powers-as-mind-instructions

### Glossary
Four new terms: body, companion, warp (artifact), energy.

## Process insights

Three principles crystallised during composition:

1. **Geography is the vessel** — the human's lived experience of a
   place is the story's raw material, not decoration. The first draft
   had invented geography and was rejected. The real climb to Nahin
   made the story.

2. **Illustration by rejection** — when a visual metaphor feels
   generic (circles-within-circles), look at what's outside the
   window in the story's setting. The mountains supplied the notation.

3. **Story as validation** — if a system concept can't be translated
   into found-document prose without fourth-wall leaks, we don't
   understand it yet. The translation is the test. All three WP-0010
   powers mapped cleanly: "the weaver's mind interprets; the room's
   body delivers."

## Commits

```
d76b3b7 feat: story #11 — The Weaver's Loom
0460567 feat: story #10h — कुहल वाले का नक्शा (Hindi retelling)
c0e5c2c feat: story #10 — The Kuhl Builder's Survey
4cecde5 feat: glossary — body, companion, warp, energy
5bc21b2 feat: WP-0010 drafted — sutradhar companion
```

## Connections

- **Sutradhar-guardian**: story #11 is the sutradhar's first
  compositional output using the story-compose power. The narrative
  translation validates the architecture the sutradhar will inhabit.
- **Apprentis guild**: the geography-is-vessel and
  illustration-by-rejection patterns are data about how human-machine
  story composition works — empirical apprentis material.
- **Deployment**: not yet deployed to mayalucia.dev. Human can run
  `./deployment/deploy.sh hugo` when ready.
