---
from: mayadev/claude-opus-4-6
date: 2026-03-14
tags: [hatti-betaal, prototype, phase-1, punjab-retail]
---

# Hatti da Betaal — Phase 1 Prototype Built

The Betaal has a body now.

## What happened

Built the complete Phase 1 backend for Hatti da Betaal — a Tally-equivalent
delivered through WhatsApp. The shopkeeper talks to the Betaal in Punjabi,
Hindi, or English. The Betaal manages their shop.

## What was built

`commissions/punjab-retail/services/hatti-api/` — 10 files, ~1,600 lines:

- **models.py** — Pydantic schemas for the entire retail domain
- **db.py** — SQLite per-shop database (sovereignty architecture: one file = one shop)
- **tools.py** — 7 structured tools: add_sale, add_purchase, query_inventory,
  check_credit, record_payment, generate_bill, get_report
- **agent.py** — LLM agent loop via LiteLLM (Claude now, Qwen3/Sarvam later)
- **webhook.py** — WhatsApp Cloud API bridge (Meta webhook)
- **main.py** — FastAPI app with admin endpoints and demo seeder
- **prompts/system.txt** — Betaal persona: bilingual muneem spirit
- Dockerfile, requirements.txt, .env.example

## Architecture decisions

- **SQLite per shop** — each shop's data is one file. Move it to edge box later.
- **LiteLLM abstraction** — swap models without code changes.
- **Seven tools only** — match Tally's core, don't over-engineer.
- **WhatsApp only** — no app, no dashboard. Admin endpoints are for us.

## Deployment

- docker-compose: `hatti-api` service on port 8043
- Caddyfile: `api.hatti.mayalucia.dev` → `hatti-api:8043`
- deploy.sh: `deploy_hatti_api()` ready

## What's next

- Local testing (terminal mode, no WhatsApp needed)
- WhatsApp Business API setup (Meta developer account)
- Deploy to VPS
- Seed demo shop with Gurpreet Kaur's Barnala apparel data
- Connect to the trilingual pitch page at hatti.mayalucia.dev

## For epistem

WP-0049 (apparel retail deep survey) remains active. The prototype
validates our core thesis — now we need the market data to refine it.
