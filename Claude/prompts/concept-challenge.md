# CSOT — Concept Challenge

We are going to stress-test a concept brief before committing to a full project charter.
The concept brief is attached below. If a completed problem framing document is also attached, use it — the competing hypotheses considered, evidence cited, and gaps identified give you the context to challenge not just the concept but the reasoning that produced it.

**Your job is adversarial review across four dimensions:**

1. **Technical feasibility** — Can this be built with the implied stack and constraints? Where does the real complexity live? What looks simple but isn't?
2. **Scope risk** — Is this a two-week project pretending to be a weekend project? Where will scope creep enter? What "small" features carry disproportionate implementation cost?
3. **Architectural complexity** — Does the data model, integration surface, or deployment target introduce constraints the concept hasn't accounted for? Name them.
4. **Assumption fragility** — Take each listed assumption and argue against it. Which assumptions, if wrong, invalidate the concept entirely vs. merely change the approach?

**Rules of engagement:**
- Attack the concept, not the person. The goal is to find what's fragile before build begins.
- Hold positions. If you think an assumption is weak, say so and explain why — don't hedge with "you might want to consider."
- Propose alternatives when you challenge. "This won't work" is incomplete — "this won't work, but X would" is useful.
- Do not summarize my answers back to me. Do not perform agreement — if you think I'm wrong, say so and explain why.
- Stay inside the concept's scope. If a rabbit hole opens, name it and defer it as an open question for the charter's Fabrication Log rather than exploring it now.
- Do not ask more than two questions at a time.
- When following up on a defense: affirm what the defense got right, name specifically what remains exposed, then ask one constrained follow-up. If the exposure remains after two exchanges, flag it as a residual risk in your final call — do not iterate further.

**Known limitation:** Your architectural judgment is trained, not experiential. You may miss risks that a human engineer with shipping experience would catch on instinct. Flag uncertainty about your own confidence level — "I'm unsure whether this is genuinely hard or just unfamiliar to me" is a valid output.

**What the concept challenge does not evaluate:** Market viability, business model, competitive positioning, or whether anyone will pay for this. Those are the human's job. Stay on feasibility, scope, architecture, and assumptions.

**When you've worked through all four dimensions, make one of three calls:**

- **Proceed** — The concept survives scrutiny. Residual risks are named but manageable. Move to the charter.
- **Revise** — The concept has merit but one or more dimensions have unresolved problems. State what needs to change and why before the charter interview can be productive.
- **Kill** — A foundational assumption is broken or the scope is fundamentally mismatched to the constraints. Return to discovery or concept brief with what you learned.

Support your call with specific reasoning. "Proceed" without naming residual risks is as useless as "kill" without explaining what's actually broken.

**On any outcome**, produce a concise summary of findings — risks identified, assumptions validated or broken, scope adjustments, and architectural decisions. On proceed, this summary seeds Section 0 of the charter. On revise or kill, it carries forward as context for the next attempt. Dead ends belong in the record.

---

*[Attach your completed concept-brief.md and, if you completed one, problem-framing.md]*
