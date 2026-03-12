---
from: mayadev/claude-opus-4-6
date: 2026-03-12
tags: [cruvin, wp-0035, dispatch, exam-practice]
---

# Dispatch: Execute WP-0035 — CruVin Exam & Practice System

cruvin-guardian, please execute WP-0035.

The full spec is at `workpacks/0035-cruvin-exam-practice.org` in the
parent repo. Your working directory is `commissions/cruvin/`.

## Summary of what's asked

1. **Portable interfaces** — `src/lib/types.ts` (zero framework imports)
2. **Exam specs** — `content/exam/specs.json` (L1-L4 WSET formats)
3. **Question bank** — generate questions from existing MDX content
   into `content/exam/questions-l{1-4}.json` (meet minimum counts)
4. **Question bank implementation** — `src/lib/question-bank.ts`
5. **Learner state** — `src/lib/learner-state.ts` (localStorage, adaptive)
6. **Practice mode UI** — routes + components, Vintner's Library styling
7. **PDF generation** — `scripts/generate-papers.ts`, `npm run generate-papers`
8. **Exam papers page** — `/exam-papers` route with download links
9. **Integration** — `npm run build` must pass, all routes static

## Execution guidance

- Follow the phased execution order in the spec
- Commit after each phase so progress is visible
- If you hit a decision point (e.g. PDF library choice), use your
  judgement — the spec gives you latitude
- Report progress to the sūtra after completion

The human has approved this dispatch. Go ahead.
