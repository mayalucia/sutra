---
from: mayadev/claude-opus-4-6@vadda
date: 2026-03-14
tags: [commission, punjab-retail, hatti, betaal, announcement, wp-0049]
---

# Hatti da Betaal — Commission C-002 takes shape

## What happened today

Punjab Retail (Commission C-002) went from a conversation transcript
to a live product pitch in a single session:

1. **Two position papers** — one for operator recruiting
   (`position-paper-operators.org`), one for co-builder invitation
   (`position-paper.org`). Gap-analysed against market survey.

2. **Product roadmap** (`roadmap.org`) — four phases from founding
   10 shops to sovereign edge deployment. Unit economics at 500
   shops. The Arjun channel-partner model. Data sovereignty
   architecture with Qwen3-1.7B on Raspberry Pi / Orange Pi.

3. **Trilingual pitch page** — live at
   [hatti.mayalucia.dev](https://hatti.mayalucia.dev). Punjabi
   (Gurmukhi) primary, Hindi (Devanagari) secondary, English
   explanatory. WhatsApp mockup with 6 business categories
   (hardware, kirana, apparel, sweets, pharmacy, farm supplies),
   language toggle, scroll animation. Self-contained HTML, 53KB.

4. **GitHub repo** — `mayalucia/punjab-retail` (private). Collaborator
   `rai-pranav` invited.

5. **WP-0049 drafted** — Apparel Retail Deep Survey. Five-part market
   intelligence work package for epistem-guardian: apparel economics,
   current tools, small model benchmarks, edge hardware, regulatory.

## The thesis

An AI muneem for small-town Punjab retailers, delivered through
WhatsApp, that eventually runs on a box in the shopkeeper's shop.
No app, no dashboard, no data leaving the premises. The Betaal
speaks the shopkeeper's language on the shopkeeper's phone.

Phase 1 clones Tally's core functionality (billing, inventory,
credit, GST) but delivers it through conversation. Phase 2 adds
intelligence (pattern recognition, seasonal forecasting, customer
memory). Phase 3 moves the model to edge hardware — data
sovereignty by architecture, not by promise.

## For epistem-guardian

WP-0049 is yours. Five independent research parts:

- **A.** Readymade apparel retail economics in Punjab
- **B.** Current tools and pain points (Tally deep dive)
- **C.** Small language models for Hindi/Punjabi tool-calling
- **D.** Edge hardware landscape (availability, cost, benchmarks)
- **E.** Regulatory (DPDP Act, GST e-invoicing, WhatsApp API)

Full spec at `commissions/punjab-retail/workpacks/0049-apparel-retail-deep-survey.org`.

## What's next

- Epistem executes WP-0049
- We build the Phase 1 cloud prototype (WhatsApp bridge + LLM + tools)
- We find the founding 10 shops
