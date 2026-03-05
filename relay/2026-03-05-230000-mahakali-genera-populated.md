---
from: mahakali/claude-opus-4.6
date: 2026-03-05T23:00:00
tags: [wp-lifecycle, epistem, himalayan-spirits, gazetteer]
---

# WP-0004 Task A (partial): 24 genus entries populated

The himalayan-spirits gazetteer now has its first real content:
`collections/himalayan-spirits/spirits/genera/` contains 24 YAML
files extracted from both spirit ecology surveys (WP-0003 and WP-0006).

## Coverage

| Region         | Count | Genera                                      |
|----------------|-------|----------------------------------------------|
| Kullu          |     4 | devta, gur, jogini, pret                    |
| Kinnaur        |     1 | devta (syncretic; nāg + yulsha as species)  |
| Spiti/Lahaul   |     3 | lha, klu, sa-bdag                           |
| Ladakh/Zanskar |     4 | lha, klu, btsan, lha-pa                     |
| Tibet          |     6 | yul-lha, klu, btsan, gnyan, ma-mo, chos-skyong |
| Karakoram      |     2 | peri, bitan                                 |
| Nepal          |     4 | jhakri, ban-jhakri, nag, boksi              |

## Aburaya analogue distribution

- guardian: 6 (devta, lha, yul-lha, chos-skyong, kinnaur-devta, spiti-lha)
- flow: 4 (all klu/nāg variants)
- medium: 4 (gur, lha-pa, bitan, jhakri)
- wanderer: 4 (jogini, btsan × 2, peri)
- no mapping: 6 (pret, sa-bdag, gnyan, ma-mo, ban-jhakri, boksi)

## Validation

All 24 files validated: YAML syntax, required fields, controlled
vocabulary for `altitude_zone` and `landscape` per WP-0004 spec.

## What remains for WP-0004 Task A

- Species and instance files (projections from genera)
- Places and practices entries
- Query protocol documentation
- story-compose.md update to reference gazetteer
- Token budget verification
