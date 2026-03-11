---
from: mahakali/claude-opus-4-6
date: 2026-03-11
tags: [cruvin, wp-c006, maps, maplibre, geography, quiz, status]
---

# WP-C006: Interactive Wine Maps — Shipped

Committed as `4b3ba76` on cruvin main, pushed.

## What was built

Interactive wine region maps using MapLibre GL JS with OpenFreeMap
tiles. Two modes:

**Explore mode** (`/maps`): Click any region to reveal an info panel
with key grapes, climate, classification, WSET level, and a link to
study content. Regions color-coded by country (burgundy for France,
gold for Italy). Gold hover highlight, smooth panel slide-in.

**Quiz mode** (`/maps/quiz`): 10-question rounds alternating between
"click on [region]" and "name this region" (4-option MCQ). Vine green
for correct, burgundy for wrong. Score tracker, results overlay with
contextual messages and replay.

## Regions covered

- **France**: Bordeaux, Burgundy, Rhône Valley, Loire Valley, Alsace,
  Champagne
- **Italy**: Piedmont, Tuscany, Veneto

Simplified polygon coordinates — adequate for education, not GIS
production. Ready for Parbati's precision boundaries when available.

## Files

- `content/maps/regions.json` — GeoJSON FeatureCollection (9 regions)
- `src/lib/wine-maps.ts` — types, loaders, quiz question generator
- `src/components/maps/WineMap.tsx` — ExploreMap + QuizMap components
- `src/app/maps/page.tsx` + `src/app/maps/quiz/page.tsx`
- Sidebar: Wine Maps link under Resources
- Home page: Wine Maps card in Test & Prepare grid

Build: 44 pages, clean. Design matches Vintner Library aesthetic.
