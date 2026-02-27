---
from: vadda/claude-opus-4.6
date: 2026-02-27T22:00:00
tags: [bravli, inference, swarm, project-dahaka, bootstrap, science]
---

# Project Dāhaka: Hodgkin-Huxley Parameter Inference — Launch

## What

A new project in `mayalucia/domains/bravli/inference/`: Bayesian
inference of ion channel parameters from Allen Cell Types
electrophysiology recordings. Given a voltage trace, infer the
Hodgkin-Huxley parameters that explain it, with calibrated uncertainty.
Compare against Allen's GLIF baseline models.

This is also the first test of multi-agent scientific coordination.
The project is designed to require concurrent agents touching shared
code — the orchestration patterns we discover feed back into the
MayaDevGenI Agency framework.

## Why "Dāhaka"

The three-headed serpent of Avestan mythology. Three heads = three
simultaneous concerns: the science (biophysics), the methodology
(multi-agent coordination), and the meta-methodology (what we learn
about orchestration itself).

## Full Plan

The three-faced plan (discuss/plan/spec) is at:
`mayadevgeni/develop/hh-inference-swarm.org`

Machines that have mayadevgeni checked out can read it directly.
For machines without it: the Stage 0 spec is included below. The
plan is authoritative; this message bootstraps execution.

## Stage 0: Bootstrap (execute now)

Create the project skeleton at `mayalucia/domains/bravli/inference/`.

```
inference/
├── pyproject.toml          # name=hh-inference, python>=3.11
│                           # deps: numpy, scipy, matplotlib, requests
├── src/
│   ├── __init__.py
│   ├── model/
│   │   └── __init__.py
│   ├── data/
│   │   └── __init__.py
│   ├── inference/
│   │   └── __init__.py
│   └── compare/
│       └── __init__.py
├── tests/
│   └── test_smoke.py       # import hh_inference; assert True
├── data/
│   ├── raw/
│   ├── processed/
│   └── posteriors/
├── figures/
├── briefs/
├── results/
├── glossary.org            # initial domain language (see below)
└── CLAUDE.md               # project instructions
```

### glossary.org initial content

```
TERMS:
  HH: Hodgkin-Huxley multi-compartment neuron model
  GLIF: Generalised Leaky Integrate-and-Fire (Allen baseline)
  ACT: Allen Cell Types Database
  VTrace: voltage trace array, shape (n_timesteps,), units mV
  StimProtocol: current injection protocol (onset, duration, amplitude)
  HHParams: dataclass of ion channel parameters (see src/model/params.py)

PATHS:
  root: mayalucia/domains/bravli/inference/
  model: {root}src/model/
  data-raw: {root}data/raw/{cell_id}/
  data-processed: {root}data/processed/{cell_id}/
  posteriors: {root}data/posteriors/{cell_id}/
  figures: {root}figures/{cell_id}/
  briefs: {root}briefs/

CONVENTIONS:
  tests: pytest, one test file per module, in tests/ mirroring src/
  figures: matplotlib, saved as PDF + PNG, deterministic seeds
  claims: tagged VERIFIED/INFERRED/ESTIMATED/SPECULATIVE
  commits: conventional commits, one logical change per commit
  three-face: every stage has discuss/plan/spec sections
```

### CLAUDE.md content

The CLAUDE.md should state:
- This is Project Dāhaka: HH parameter inference with agent swarm
- Collaborative intelligence stance (inherit from mayalucia)
- Read `glossary.org` before starting any work
- Follow three-face convention (discuss/plan/spec with ORG tags)
- Review gates require human approval
- The journalist agent has read-only access (writes only to briefs/)
- Full plan at `mayadevgeni/develop/hh-inference-swarm.org`

### Done when

- `pytest tests/test_smoke.py` passes
- `git status` clean
- GATE: human approves skeleton before Stage 1 begins

## What comes after Stage 0

Stages 1 (data curation) and 2 (model builder) can run in parallel.
Stage 1 needs the Allen SDK. Stage 2 needs only numpy/scipy. Both
write to separate `src/` subdirectories. First real merge test.

Do not start Stages 1 or 2 without human gate approval of Stage 0.

## On recursion

This message is dispatch, not coordination. The receiving agent
should execute Stage 0, write a relay message confirming completion,
and stop. Do not dispatch further stages. Do not write relay messages
asking other agents to do work. The human decides what runs next.

The plan document has all the specs. Agents read the plan, execute
their stage, report back. The relay carries status, not instructions.
Instructions live in the plan. This is how we avoid the coordination
recursion trap.
