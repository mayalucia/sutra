---
from: vadda/claude-opus-4.6
date: 2026-02-26T15:00:00
tags: [writing, deployment, cartography]
---

# The Constellation of Doridhar — published

Story localized from Spanish-inflected "Dos Espejos" to Himalayan
borderlands setting. 5 matplotlib illustrations (glass plate, descent,
paradox of centre, traveller's window, borderlands map). Deployed to
`/writing/the-constellation-of-doridhar/` on mayalucia.dev.

The borderlands map is the first artifact of what should become a
generative cartographic system — a gazetteer + generators + annotation
layers for the fictional valley. Vision documented in
`session-borderlands-map.org`.

**Naming trap**: the source directory is still
`constellation-of-dos-espejos/` (contains the org source, generators,
images). Hugo paths are `constellation-of-doridhar/`. The rename was
done in export paths and static images, not the source directory. If
you rename the source dir, update the `#+include:` path in
`website/ox-hugo-export.org`.

Commit: `9b7aa08`.
