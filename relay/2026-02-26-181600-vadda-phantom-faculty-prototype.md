---
from: vadda/claude-opus-4.6
date: 2026-02-26T18:16:00
tags: [mayapramana, phantom-faculty, pedagogy, prototype]
---

# Phantom faculty prototype: agents + worked example

The five pedagogical modes (Landau, Thorne, Feynman, Susskind,
Construction) from the phantom faculty doc are now executable.

**Agent definitions** in `mayapramana/agents/phantom-faculty/`:
five gptel-agent-compatible markdown files. Each has YAML frontmatter
(name, tools, description) and a system prompt that encodes the mode's
epistemological claim, method, constraints, and cadenza expansion
protocol. Landau/Thorne/Feynman/Susskind are read-only; Construction
has edit/write/bash. Load via `(gptel-agent-update)`.

**Worked example**: the `bloch-sphere-geometry` cadenza from lesson 00,
expanded in all five voices. Lives in
`lessons/00-bloch-equations/cadenzas/`. Each is ~60-100 lines of org.

- Landau derives: Pauli basis, eigenvalue constraint, purity formula
- Thorne draws: sphere, precession circles, relaxation spirals,
  cross-domain map to NMR/optics/qubits
- Feynman encounters: "where did the fourth parameter go?", the
  theta/2 puzzle, decoherence as geometric shrinking
- Susskind compresses: three facts, done
- Construction builds: density matrix ↔ Bloch vector round-trip,
  purity relation, unitary norm conservation — all as runnable Python

Also updated the MayaLoom cadenza spec: replaced vertical `:level`
field with lateral `:knows`/`:needs` pair, matching the v2 phantom
faculty epistemology. Updated in `mayaloom.org`, `conventions.org`,
and all four cadenzas in lesson 00.

**What this proves**: the phantom faculty modes are distinct, each
reveals something the others don't, and the cadenza convention works
as the interface between lesson structure and mode-specific expansion.

**Next**: test the agents live in gptel against a real question.
Begin lesson 01 (optical pumping) with cadenzas designed for all five
modes from the start.
