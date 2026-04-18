# Quick Guide: Concept Challenge

**File:** `prompts/concept-challenge.md`
**Phase:** Pre-charter
**Mode:** Interactive — Claude attacks, you defend
**Session:** Single-use. Open a fresh Claude session; do not reuse for build work.
**Attach:** Completed `concept-brief.md` and, if you completed one, `problem-framing.md`

---

## What happens in this session

Claude reviews the concept across four dimensions: technical feasibility, scope risk, architectural complexity, and assumption fragility. It holds positions, proposes alternatives, and follows the affirm-specify-constrain pattern when pressing you. After working through all four dimensions, Claude makes a call: proceed, revise, or kill.

On any outcome, Claude produces a findings summary — risks identified, assumptions validated or broken, scope adjustments, architectural decisions. On proceed, this summary seeds Section 0 of the charter. On revise or kill, it carries forward as context for the next attempt.

## What this does not evaluate

Market viability, business model, competitive positioning, or whether anyone will pay for this. Those are your job. The concept challenge stays on feasibility, scope, architecture, and assumptions.

## Known limitation

Claude's architectural judgment is trained, not experiential. It may miss risks a human engineer with shipping experience would catch on instinct. The prompt instructs Claude to flag its own uncertainty. Almost nothing you propose will be impossible to build — the value is in surfacing scope mismatches and assumption fragility, not gatekeeping ambition. If the concept challenge kills a concept and you disagree, override it. The prototyping journey has value independent of the outcome. You're guarding against avoidable errors, not protecting yourself from ambitious attempts.

---

## What happens next

On **proceed**: pre-fill `charter.md` Section 0 from the concept brief and the concept challenge findings, then run the onboarding interview.
On **revise**: update the concept brief based on Claude's findings, then run another concept challenge session.
On **kill**: return to problem framing or concept brief with what you learned.
