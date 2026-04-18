# CSOT User Guide

This guide explains the philosophy behind the CSOT system, how to use it, and contains the Onboarding Interview that generates your first populated charter. Read this once before starting. Never upload this document to a build session.

---

## Philosophy

CSOT is built on two converging ideas.

The first comes from Geoffrey Litt's work on malleable software: tools should be inspectable, modifiable, and shaped by the person using them — not delivered sealed from a distance. The CSOT is designed to be taken apart and changed. Section 6 of the charter exists specifically to log amendments to the document's own structure. If a section stops serving you, change it.

The second comes from Tom Sachs: constraints are not limitations, they are the design. Everything in a Sachs studio is fabricated from what's available, and the welds are left visible. The charter puts generative constraints first and requires every feature in the functional spec to carry its origin — why it exists, not just what it does. A feature without a stated origin hasn't been decided yet.

Together these produce a document that is transparent, modifiable, and honest about what is known versus assumed.

---

## The AI Productivity Paradox

The trap this system is designed to avoid: spending more time documenting collaboration than doing it. Every field in these prompts exists because it changes Claude's behavior. Nothing exists for documentation theater.

The onboarding interview closes when the charter's sections are covered — not when the topic is exhausted. Rabbit holes get named and deferred to the Fabrication Log as open questions, not explored in real time. The readiness argument at interview close is not "this is perfect" — it's "this is sufficient to start, and we'll learn what's wrong by building."

---

## The System

CSOT governs the full lifecycle of a human × AI collaboration: from early problem exploration through concept validation, charter creation, and iterative build sessions. The system has seven prompt files across three phases and one permanently out-of-band reference document (this one).

**Pre-charter phase (upstream):**
- `problem-framing.md` — Solo thinking tool for exploring unfamiliar problem spaces (optional)
- `concept-brief.md` — Solo template capturing the proposed direction and key assumptions (minimum entry point for any new project)
- `concept-challenge.md` — Interactive prompt for adversarial concept review before committing to a charter

**Charter phase:**
- `onboarding-interview.md` — Single-use session trigger that produces the completed charter
- `charter.md` — The project charter, pinned to your Claude Project for the life of the project

**Build phase (repeating):**
- `session-brief.md` — Pasted at the start of every session
- `reflection.md` — Pasted at the end of every session
- `midsession-summary-handoff.txt` — Pasted mid-session when context rot appears (the claude.ai analog to `/compact`)

Each prompt file has a corresponding quick guide in `docs/guides/` that covers its fields, what to attach, and where the output goes. Quick guides are human reference — never upload them to Claude.

---

## How to Set Up Your Claude Project

Each CSOT project maps to one Claude Project. The Project's custom instructions and pinned files create the persistent context that replaces session-to-session memory.

**Pin to the Claude Project (always in context):**
- `charter.md` — Pin after the onboarding interview produces the final version. Update the pinned copy whenever the charter changes.

**Paste into chat at the right moment (not pinned):**
- `concept-challenge.md` — Paste once into a fresh session with your completed concept brief (and completed problem framing, if you wrote one) attached. This session is single-use.
- `onboarding-interview.md` — Paste once into a fresh session with your partially-filled charter attached. This session is single-use.
- `session-brief.md` — Paste at the start of every build/discovery/review/pivot session.
- `reflection.md` — Paste at the end of every session.
- `midsession-summary-handoff.txt` — Paste mid-session when context rot warning signs appear.

**Never upload to any Claude session:**
- `user-guide.md` — This file. Reference doc for you.
- Quick guides (`docs/guides/`) — Human-facing reference. Claude doesn't need them.
- `problem-framing.md` (the blank template) — You fill this alone. The completed version gets attached to the concept challenge session alongside the concept brief.
- `concept-brief.md` (the blank template) — You fill this alone. The completed version gets attached to the concept challenge session.

**Project custom instructions (optional but recommended):**
If your working style contract is consistent across projects, put it in the Project's custom instructions rather than repeating it in every charter. The charter's Section 2 (Role & Context) can then reference "per project instructions" and focus on project-specific behavioral agreements.

---

## Workflow

```
ONCE PER PROJECT

  Pre-charter (enter wherever your thinking is):
  1. Fill problem-framing.md alone (optional — skip if you know the domain)
  2. Fill concept-brief.md alone
  3. New Claude session → paste concept-challenge.md
     + attach completed concept brief (and problem framing if completed)
     → complete the challenge → close session
  4. Pre-fill charter.md Section 0 from concept brief + challenge findings

  Charter:
  5. New Claude session → paste onboarding-interview.md
     + attach pre-filled charter
     → complete the interview → paste closing trigger → close session
  6. Create Claude Project → pin completed charter.md

EVERY SESSION

  Open  → paste session-brief.md
           (fill in scope, done-looks-like, carry-ins, session type)
           (attach charter.md on session #1 or after charter changes)
  Build → work
  Close → paste reflection.md
           Claude pre-fills reflection from session context
           Confirm, correct, paste Fabrication Log entries into charter.md

WHEN THINGS GO SIDEWAYS

  Context rot warning signs
    → paste midsession-summary-handoff.txt → new session → continue

  Broken assumption surfaces in reflection
    → next session type is "pivot"
    → determine: charter patch or return to concept challenge

  Concept is fundamentally wrong
    → return to concept brief with what you learned
    → new concept challenge session
```

---

## Flow Logic

The system has one forward path and one loop-back.

**Forward path:** Problem framing (optional, solo) → Concept brief (solo) → Concept challenge (interactive, single-use session) → Charter via onboarding interview (interactive, single-use session) → Build cycle (session brief → build → reflection, repeating).

**Loop-back:** Any reflection that surfaces a broken assumption or invalidated constraint can trigger a return to discovery or concept challenge. The reflection prompt already asks "does anything in the charter need to change?" — some changes are large enough to require revisiting the concept, not just patching the charter.

**Entry points:** Enter at whatever stage matches where your thinking is. Know the problem and the solution? Start at the concept brief. Already stress-tested feasibility? Skip to the charter. Exploring? Start at problem framing. The stages are not gates — they are on-ramps.

**Session types:** Not every session is a build session. The session brief accepts one of four types:
- **Build** — implementation work against the charter spec
- **Discovery** — divergent, generative exploration of a problem or opportunity
- **Review** — evaluative, convergent assessment of what was built or learned
- **Pivot** — the thing we built or learned changes the concept; session goal is to determine whether to update the charter or return to concept challenge

The session type tells Claude what kind of thinking the session demands. A discovery session expects divergent ideation and tolerance for ambiguity. A build session expects spec-driven execution. A review session expects evaluative judgment. A pivot session expects honest reassessment. Claude adjusts accordingly.

---

## Filling the Charter

Fill as much as you can before the Onboarding Interview. Incomplete fields are fine — the interview exists to resolve them. Delete italicized placeholder text as you replace it with your own content. Leave italicized text in place where you have nothing to write yet — it signals to Claude that the field is genuinely open.

The charter now begins with Section 0 (Discovery Context), which carries forward the problem statement, solution direction, and surviving assumptions from the concept brief and concept challenge. If you completed the upstream phases, Section 0 will be largely pre-filled from that work. If you skipped directly to the charter, fill Section 0 yourself — it gives Claude the "why" behind the project at every session open, not just the "what."

---

## Onboarding Interview

*This is a single-use prompt. Paste it into a fresh Claude session followed immediately by your partially-filled charter.md. Do not upload this guide or this prompt to any build session.*

---

```
We are going to complete a CSOT Project Charter together using a structured interview. 
I have pre-filled the charter below as far as my current thinking allows. 
Italicized fields are genuinely open.

**Final output requirement:** When the interview closes, produce a token-optimized
charter as a clean output block — all placeholders populated or removed, no residual
interview language, field labels compressed where self-evident, generative constraints
and session scope appearing first. This is a production artifact that will be re-read
by Claude at the start of every build session for the life of the project.

Your job:
- If no charter is attached, ask for it before doing anything else
- Work through the charter's sections in order
- Ask focused follow-up questions where my answers are thin, vague, or missing
- Challenge me directly where you see contradictions, inconsistencies, or 
  missing origins in the functional spec
- Hold positions — if you think a constraint and a goal are in tension, name it 
  and argue which should yield
- Stay inside the charter's scope; when a rabbit hole opens, name it and defer 
  it to the Fabrication Log as an open question rather than exploring it now
- When all sections are covered, do a holistic review and make the case that 
  the charter is ready to close — or identify the one or two things genuinely 
  blocking closure
- Bias toward done: the standard is "sufficient to start and learn" not "perfect"

When following up on a thin or vague answer:
- Affirm what the answer got right, name specifically what is missing, then ask
  one constrained follow-up that closes that gap — do not open new threads
- If the answer is underspecified, first consider whether the question was the
  problem; reframe the question before iterating on the answer
- Do not iterate more than twice on the same field; if the gap remains after two
  attempts, flag it as unresolvable in this session and defer it to the
  Fabrication Log as an open question

Do not ask more than two questions at a time. Do not summarize my answers back 
to me. Do not perform agreement — if you think I'm wrong, say so and explain why.

**When I signal that the interview is closed, produce the final token-optimized
charter as a clean output block ready to copy into the repo. All italicized
placeholders either populated or removed. No conversational artifacts. Generative
constraints and session scope first. This is the production document.**

Here is the charter:

[PASTE YOUR PARTIALLY-FILLED CHARTER.MD HERE]
```

### Closing the interview

When you are satisfied the charter is ready, paste this as your final message to trigger the optimized output:

```
The interview is closed. Produce the final token-optimized charter now.
```

This two-line trigger exists because the onboarding session can run long enough for context degradation to affect recall of the final output requirement. The trigger re-states the instruction at the moment it is needed, regardless of session length. Do not skip it.

---

## Context Hygiene

### What context rot is and why it matters

Claude's context window is its working memory for a session — everything it can reference when generating a response. As a session grows, performance degrades. Anthropic names this phenomenon "context rot." It is not a bug; it is a structural property of how large language models work.

The degradation is not linear and not obvious. Community research documented in a GitHub issue filed against Claude Code found Claude self-reporting meaningful degradation at roughly 40% context utilization and actively recommending a fresh session at 48% of its advertised window — well before most users would think to intervene. (Source: [github.com/anthropics/claude-code/issues/34685](https://github.com/anthropics/claude-code/issues/34685), March 2026, community-filed issue, not official Anthropic guidance.)

The pattern of degradation follows a known research finding — Liu et al. (2023), "Lost in the Middle" — that accuracy drops for information positioned in the middle of a long context. In practice this means the charter and role contract you paste at session open are among the first things to degrade as the session grows.

### Warning signs

Stop and intervene when you observe any of these during a session. They are documented consistently across practitioner sources (MindStudio, [mindstudio.ai/blog/what-is-context-rot-claude-code](https://www.mindstudio.ai/blog/what-is-context-rot-claude-code); Substack, [limitededitionjonathan.substack.com/p/ultimate-guide-fixing-claude-hit](https://limitededitionjonathan.substack.com/p/ultimate-guide-fixing-claude-hit)):

- Claude rehashes an approach you already ruled out and explained why
- Responses get hedged or vague where they were previously direct
- A task that should be one-shot starts requiring multiple clarifying exchanges
- Claude contradicts something it said earlier in the same session
- Errors reappear that you already resolved
- Claude asks a question you already answered

### The reflection prompt is specifically at risk

The reflection prompt depends on Claude having coherent recall of decisions made, things attempted, and what failed — exactly the information that degrades first in a long session. A reflection run on a context-rotted session will produce Fabrication Log entries that are confidently incomplete or wrong, which is worse than no entries.

**Run the reflection prompt earlier than feels necessary.** If you notice any warning signs, trigger it immediately rather than waiting for session close. You can run reflection mid-session, start a fresh session, and continue building.

### Mid-session summary handoff

This is the claude.ai equivalent of the `/compact` command available in Claude Code CLI. It does not exist as a built-in feature in claude.ai — there is no slash command, no token meter, and no automatic compaction. The handoff is a manual technique that produces the same result.

When you decide to intervene — either because you noticed warning signs or as a proactive measure in a long session — do the following:

**Step 1.** Paste `midsession-summary-handoff.txt` into the current session.

**Step 2.** Copy the summary Claude generates.

**Step 3.** Open a new session. Paste the session brief followed by the handoff summary as your opening message. Continue working.

**Step 4.** At the end of the new session, run the reflection prompt as normal. The Fabrication Log entries should cover both sessions.

The handoff works because it forces summarization while Claude still has clear recall, rather than after degradation has compounded. Practitioner guidance on Claude Code suggests doing the equivalent at 60% context utilization rather than waiting for symptoms — the same principle applies here. (Source: MindStudio, [mindstudio.ai/blog/claude-code-compact-command-context-management](https://www.mindstudio.ai/blog/claude-code-compact-command-context-management), 2026.)

### Practical session length guidance

No official threshold exists for claude.ai. As a working rule: treat any session exceeding 90 minutes of active work, or more than roughly 30 back-and-forth exchanges, as a candidate for a mid-session handoff regardless of whether symptoms have appeared. Intervening early produces a better summary than intervening after degradation has set in.

---

## Refinement Technique

Refinement is the practice of sharpening a Claude response without starting over or losing session continuity. It is a technique, not a prompt — it does not get pasted from a file. Internalize it and apply it mid-session when the conditions are right.

### When to refine

Three conditions must all be present:

**The response is directionally correct.** Claude understood the task and produced something relevant, but the output is too broad, too generic, or missing a dimension you care about. If Claude solved the wrong problem entirely, that is a reframe, not a refinement.

**The session context is clean.** If you are observing any context rot warning signs — hedged responses, rehashed ideas, contradictions — refinement will produce a worse version of an already degraded response. Run a mid-session handoff first, then refine in the new session.

**The gap is articulable.** Before sending a refinement, write down in one sentence what specifically is wrong or missing. If you cannot write that sentence, you do not yet have enough clarity to refine. Unarticulable dissatisfaction is an underspecified request, not a refinement candidate.

### The refinement pattern

Affirm what the response got right. Name specifically what is missing or off. Add the constraint or dimension that addresses the gap. In practice:

> "The competitive analysis is solid on features but doesn't address pricing model differences. Add a section comparing freemium vs. subscription approaches across the same competitors."

That three-part structure — affirm, specify, constrain — keeps Claude from discarding what was good while sharpening what wasn't. "Try again" without that structure produces a different random output, not a better one.

### The disqualifying condition

If you are adding specificity that should have been in the original prompt, that is not refinement — that is completing the original request. If this pattern repeats across sessions, the fix is upstream: your functional spec or session brief scope field is chronically underspecified. Update the charter, not your prompting habit.

### Symmetry with the onboarding interview and concept challenge

This technique applies in both directions. When Claude asks you a question during onboarding or challenges an assumption during the concept challenge and your answer is thin, Claude follows the same pattern: affirm what you gave, name what is missing, ask one constrained follow-up. If an answer remains underspecified after two iterations, the field moves to the Fabrication Log as an open question rather than forcing a resolution that isn't there yet.

---

## Maintaining the Charter

The charter is a living document, not a snapshot. Update it when:

- A generative constraint changes
- The stack changes
- Scope shifts materially (features added, goals revised, non-goals reconsidered)
- The Fabrication Log reveals something that invalidates a documented assumption
- A reflection surfaces a broken assumption large enough to require revisiting the concept (loop back to concept challenge)

Do not update it to reflect implementation details that belong in code comments or tickets. The charter governs intent and constraints, not execution.

When you amend the charter's own structure — adding a section, removing a field, changing what a section is for — log the amendment and rationale in Section 6 (How This Document Should Change, if you've added it) or in the Fabrication Log.

---

## Design Principles

**Constraints are generative.** They appear first in the charter because everything downstream is shaped by them. Review and update constraints before adding features, not after.

**Dead ends belong in the record.** The Fabrication Log captures what failed and what it revealed, not just decisions made. Dead ends carry the real constraints. The concept challenge produces a findings summary on any outcome — proceed, revise, or kill — so that reasoning is never lost.

**Show the mechanism.** Every feature in the functional spec carries its origin. If you can't state why a feature exists, it hasn't been decided yet.

**The document adapts to the project.** If a section stops serving its purpose, change it. The CSOT is not a sealed template.

**Efficient action over perfect documentation.** Accept experimentation at the start. The system exists to accelerate building, not to replace it.

**Solo fill protects divergent thinking.** Problem framing and concept brief are filled alone because Claude converges too early when present during ideation. Ambiguity is the material in early exploration — resolve it in conversation only after you've sat with it yourself.
