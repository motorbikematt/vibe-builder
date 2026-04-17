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

## The Three Prompts

**charter.md** — The project charter. Written once per project via the Onboarding Interview, updated only when constraints, stack, or scope materially change. Pin this to your Claude Project so it's always in context without manual upload.

**session-brief.md** — Pasted at the start of every session. Tells Claude what today's session is doing, what done looks like, and what carry-ins exist from last session. Attach the charter only on session one or when the charter has changed.

**reflection.md** — A session-close trigger. Paste it at the end of any build session. Claude reviews the full session context, pre-fills the reflection questions from what it observed, confirms with you, then generates Fabrication Log entries ready to paste into the charter. You correct or add anything Claude couldn't determine from context. This is the mechanism that makes the charter a living document.

The nine questions Claude works through internally:
- What did we set out to do this session?
- What did we actually accomplish?
- What did we attempt that didn't work, and why?
- What assumption turned out to be wrong?
- What constraint surfaced that wasn't in the charter before this session?
- What decision did we make that can't easily be undone?
- What is clearer now than it was at the start of this session?
- What is still unresolved, and what would it take to resolve it?
- Does anything in the charter need to change based on what we learned?

---

## Workflow

```
ONCE PER PROJECT
  1. Fill charter.md with your initial thinking (leave gaps where uncertain)
  2. Open a new Claude session
  3. Paste the Onboarding Interview below as your first message,
     followed by your partially-filled charter
  4. Complete the interview — Claude challenges, you defend or revise
  5. Claude declares readiness; you agree or identify what's blocking closure
  6. Paste the closing trigger: "The interview is closed. Produce the final
     token-optimized charter now."
  7. Copy the output into charter.md, pin it to your Claude Project

EVERY SESSION
  Open  → paste session-brief.md (attach charter.md on session #1 or after charter changes)
  Build → work
  Close → paste reflection.md
          Claude pre-fills reflection from session context and confirms with you
          Paste generated Fabrication Log entries back into charter.md
```

---

## Filling the Charter

Fill as much as you can before the Onboarding Interview. Incomplete fields are fine — the interview exists to resolve them. Delete italicized placeholder text as you replace it with your own content. Leave italicized text in place where you have nothing to write yet — it signals to Claude that the field is genuinely open.

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

**Step 1.** Paste this prompt into the current session:

```
Before we close this session, generate a handoff summary containing:
- Decisions made this session that must carry forward
- Approaches we ruled out and why
- Current state of what was built or changed
- Open questions that remain unresolved
- Anything in the charter that needs updating

Be specific and terse. This summary will open the next session.
```

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

### Symmetry with the onboarding interview

This technique applies in both directions. When Claude asks you a question during onboarding and your answer is thin, Claude follows the same pattern: affirm what you gave, name what is missing, ask one constrained follow-up. If an answer remains underspecified after two iterations, the field moves to the Fabrication Log as an open question rather than forcing a resolution that isn't there yet.

---

## Maintaining the Charter

The charter is a living document, not a snapshot. Update it when:

- A generative constraint changes
- The stack changes
- Scope shifts materially (features added, goals revised, non-goals reconsidered)
- The Fabrication Log reveals something that invalidates a documented assumption

Do not update it to reflect implementation details that belong in code comments or tickets. The charter governs intent and constraints, not execution.

When you amend the charter's own structure — adding a section, removing a field, changing what a section is for — log the amendment and rationale in Section 6 (How This Document Should Change, if you've added it) or in the Fabrication Log.

---

## Design Principles

**Constraints are generative.** They appear first in the charter because everything downstream is shaped by them. Review and update constraints before adding features, not after.

**Dead ends belong in the record.** The Fabrication Log captures what failed and what it revealed, not just decisions made. Dead ends carry the real constraints.

**Show the mechanism.** Every feature in the functional spec carries its origin. If you can't state why a feature exists, it hasn't been decided yet.

**The document adapts to the project.** If a section stops serving its purpose, change it. The CSOT is not a sealed template.

**Efficient action over perfect documentation.** Accept experimentation at the start. The system exists to accelerate building, not to replace it.
