# CSOT — Collaboration Source of Truth

A structured protocol for human × AI app development collaboration. Built for Claude, designed around the principle that constraints are generative, process is visible, and documents serve the work — not the other way around.

---

## What This Is

CSOT is a seven-file system that governs how a human and Claude collaborate across sessions on a software project. It covers the full lifecycle: from early problem exploration and concept validation through charter creation and iterative build sessions.

The system is deliberately lean. Every field exists because it changes Claude's behavior. Nothing exists for documentation theater.

---

## Workflow

```
┌─────────────────────────────────────────────────────┐
│                   ONCE PER PROJECT                  │
│                                                     │
│  Pre-charter (enter wherever your thinking is):     │
│                                                     │
│  1. Fill problem-framing.md alone (optional)        │
│  2. Fill concept-brief.md alone                     │
│  3. Paste concept-challenge.md into fresh session   │
│     + attach concept brief (and problem framing)    │
│     Claude challenges, you defend or revise         │
│  4. Pre-fill charter.md Section 0 from findings     │
│                                                     │
│  Charter:                                           │
│                                                     │
│  5. Paste onboarding-interview.md + charter.md      │
│     into a fresh Claude session                     │
│  6. Claude challenges, refines, agrees to close     │
│  7. Pin completed charter to Claude Project         │
└─────────────────────────┬───────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────┐
│                  EVERY SESSION                      │
│                                                     │
│  OPEN  → Paste session-brief.md                     │
│          (attach charter.md only if it changed)     │
│                                                     │
│  BUILD → Work                                       │
│                                                     │
│  CLOSE → Paste reflection.md                        │
│          Claude pre-fills from session context       │
│          Confirm, correct, paste log entries         │
│          into charter.md                            │
└─────────────────────────────────────────────────────┘
```

---

## Files

```
prompts/
  problem-framing.md       Solo thinking tool for unfamiliar problem spaces (optional)
  concept-brief.md         Solo template — proposed direction and key assumptions
  concept-challenge.md     Interactive prompt — adversarial concept review
  charter.md               Project charter — fill once via interview, update via reflection
  onboarding-interview.md  Single-use session trigger to complete the charter
  session-brief.md         Session opener — paste every session
  reflection.md            Session closer — paste at end of every session
  midsession-summary-handoff.txt  Context rot intervention — paste mid-session when needed

docs/
  user-guide.md            Philosophy, process, and onboarding interview reference
  guides/
    problem-framing.md     Quick reference for the problem framing template
    concept-brief.md       Quick reference for the concept brief template
    concept-challenge.md   Quick reference for the concept challenge prompt
    charter.md             Quick reference for the charter template
    onboarding-interview.md Quick reference for the onboarding interview
    session-brief.md       Quick reference for the session brief
    reflection.md          Quick reference for the reflection prompt
```

---

## Quickstart

1. Read `docs/user-guide.md` — once, before anything else
2. Fill `prompts/problem-framing.md` alone if the domain is unfamiliar (optional)
3. Fill `prompts/concept-brief.md` alone
4. Open a new Claude session, paste `prompts/concept-challenge.md`, attach concept brief (and problem framing if completed)
5. Complete the challenge — Claude attacks, you defend or revise
6. Pre-fill `prompts/charter.md` Section 0 from the concept brief and challenge findings
7. Open a new Claude session, paste `prompts/onboarding-interview.md`, attach pre-filled charter
8. Complete the interview — Claude challenges, you defend or revise
9. Paste the closing trigger from the user guide to generate the optimized charter
10. Copy the output into `prompts/charter.md` and pin it to your Claude Project
11. Use `prompts/session-brief.md` to open every subsequent session
12. Use `prompts/reflection.md` to close every session and update the charter

Quick guides in `docs/guides/` provide field-level reference for each prompt — consult them when filling or pasting.

---

## Design Principles

**Constraints are generative.** They appear first in the Charter because everything else is shaped by them.

**Dead ends belong in the record.** The Fabrication Log captures what failed and what it revealed — not just decisions made.

**Solo fill protects divergent thinking.** Problem framing and concept brief are filled alone because ambiguity is the material in early exploration.

**The document adapts to the project.** If a section stops serving its purpose, change it and log why.

**Efficient action over perfect documentation.** The system exists to accelerate building, not to replace it. When in doubt, ship the session and learn from what breaks.
