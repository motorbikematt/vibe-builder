# Quick Guide: Concept Brief

**File:** `prompts/concept-brief.md`
**Phase:** Pre-charter (minimum entry point for any new project)
**Mode:** Solo fill — do not open a Claude session for this
**When to use:** Always, for any new project. Skip only if entering a project that already has a charter.

---

## Fields

**The problem** — One paragraph. Who has it, what it is, why it matters to them. If you completed problem framing, distill the strongest version here. If you skipped problem framing, write this fresh.

**Proposed direction** — What you want to build and how it addresses the problem. Stay at the level of "a mobile app that does X" — not feature lists, not architecture. Two to three sentences.

**Key assumptions** — The things that must be true for this direction to work. Format each as: what you believe → what breaks if you're wrong. An assumption should be specific enough to be wrong. "Users will want this" is a wish. "Users currently solve this with spreadsheets and will switch to a dedicated tool if it saves them >2 hours/week" is an assumption.

**Screening criteria** — Observable conditions that tell you whether to proceed to the charter, revise the concept, or kill it. These are decision criteria for investing in the build, not success metrics for the finished product. Structure as proceed-if / revise-if / kill-if.

**Open questions** — Anything unresolved that the concept challenge should pressure-test. These become the first items Claude attacks.

---

## What happens next

Open a fresh Claude session. Paste `concept-challenge.md`. Attach this completed concept brief (and the completed problem framing, if you wrote one). Claude runs an adversarial review and produces a go/revise/kill decision with a findings summary. On proceed, the findings seed Section 0 of the charter.
