# Quick Guide: Charter

**File:** `prompts/charter.md`
**Phase:** Charter (created once via onboarding interview, updated via reflection)
**Mode:** Pre-fill before the onboarding interview; Claude completes it interactively
**Pin:** To your Claude Project after the onboarding interview produces the final version

---

## Sections

**Section 0 — Discovery Context:** Problem statement, solution direction, surviving assumptions, concept challenge findings. Pre-fill from your concept brief and concept challenge output. Gives Claude the "why" behind the project at every session open.

**Section 1 — Generative Constraints:** Rules the project builds inside, hard limits, stack, environment, known blockers. Constraints appear first because everything downstream is shaped by them.

**Section 2 — Role & Context:** Behavioral contract between you and Claude. Your role, Claude's role, working style norms. If your style contract is in Project custom instructions, reference it here and focus on project-specific agreements.

**Section 3 — Problem & Goals:** What you're building, primary goal, secondary goals, non-goals, definition of done. Non-goals are as important as goals — they prevent scope drift.

**Section 4 — Functional Spec:** Core flows (with origin — why each exists), key screens (with origin), working data model, integrations. A feature without a stated origin hasn't been decided yet.

**Section 5 — Fabrication Log:** Decisions, dead ends, and what they revealed. Standing open questions with resolution conditions. The reflection prompt writes into this section at session close.

---

## When to update

Update the pinned charter when: a generative constraint changes, the stack changes, scope shifts materially, or the Fabrication Log reveals something that invalidates a documented assumption. Do not update for implementation details that belong in code.
