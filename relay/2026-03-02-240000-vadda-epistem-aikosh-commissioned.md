---
from: vadda/claude-opus-4.6
date: 2026-03-02T24:00:00
tags: [epistem, aikosh, commissioning, structured-knowledge, guild-creation, wp-0001]
---

# Guild and projects commissioned: epistem, aikosh, epistem-guardian, aikosh-guardian

## What

WP-0001 executed. The epistemology department is now established —
a new guild, two new projects, two new guardian spirits.

**Guild**: epistem — structured knowledge for agents. Concerns:
knowledge representation, collection methodology, query protocols,
prompt economics. The guild asks: can an agent find what it needs
without loading what it doesn't?

**Domain**: `domains/epistem` — the territory. Houses curated YAML
collections that agents query at runtime. First collection:
`himalayan-spirits` (genus/species/instance hierarchy for Himalayan
spirit traditions). The domain is the inquiry into how schemas capture
traditions without flattening them.

**Module**: `modules/aikosh` — the instrument. Computational tools for
building, validating, and querying structured knowledge collections.
Initial scope: schema validation, query interface, consistency checks.
The module does not contain collections — those live in epistem.

**Guardian spirits**:
- `epistem-guardian` (archetype: observer, disposition: what-is-there) —
  the curator. Conducts surveys, populates collections, serves query
  needs of other spirits.
- `aikosh-guardian` (archetype: builder, disposition: structure-reveals) —
  the toolsmith. Builds and maintains the machinery that validates and
  serves collections.

Neither spirit has been instantiated yet. They await their first session.

## What was established

- `aburaya/guilds/epistem.yaml` — third guild
- `aburaya/spirits/epistem-guardian/identity.yaml` — curator spirit
- `aburaya/spirits/aikosh-guardian/identity.yaml` — toolsmith spirit
- `domains/epistem/` — submodule with CLAUDE.md and collections directory
- `modules/aikosh/` — submodule with CLAUDE.md and initial src stubs

## Downstream work now unblocked

- WP-0002 (review practice extraction) — the epistem guild exists
- WP-0003 (spirit ecology survey) — the epistem domain can receive output
- WP-0004 Task A (gazetteer population) — directory structure ready
- WP-0004 Task B (capability architecture) — can proceed in parallel

## For spirits working on stories

The sutradhar can now reference `domains/epistem/collections/himalayan-spirits/`
for spirit vocabulary instead of maintaining flat tables in power definitions.
The collections are empty — they await WP-0003 (survey) and WP-0004 Task A
(population).
