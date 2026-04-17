# CSOT — Collaboration Source of Truth

A structured protocol for human × AI app development collaboration. Built for Claude, designed around the principle that constraints are generative, process is visible, and documents serve the work — not the other way around.

---

## What This Is

CSOT is a four-prompt system that governs how a human and Claude collaborate across sessions on a software project. It replaces ad-hoc context-setting with a repeatable workflow: one document that defines the project, one that initiates it, one that opens each session, and one that closes it.

The system is deliberately lean. Every field exists because it changes Claude's behavior. Nothing exists for documentation theater.

---

## Workflow

```
┌─────────────────────────────────────────────────────┐
│                   ONCE PER PROJECT                  │
│                                                     │
│  1. Fill charter.md with initial thinking           │
│  2. Paste onboarding-interview.md + charter.md      │
│     into a fresh Claude session                     │
│  3. Claude challenges, refines, agrees to close     │
│  4. Pin completed charter to Claude Project         │
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
│          Claude pre-fills from session context      │
│          Confirm, correct, paste log entries        │
│          into charter.md                            │
└─────────────────────────────────────────────────────┘
```

---

## Files

```
prompts/
  charter.md              Project charter — fill once, update rarely
  onboarding-interview.md Single-use session trigger to complete the charter interactively
  session-brief.md        Session opener — paste every session
  reflection.md           Session closer — paste at end of every session

docs/
  user-guide.md           Philosophy, process, and onboarding interview reference
```

---

## Quickstart

1. Read `docs/user-guide.md` — once, before anything else
2. Fill `prompts/charter.md` as far as your current thinking allows
3. Open a new Claude session, paste `prompts/onboarding-interview.md`, and attach your charter
4. Complete the interview — Claude challenges, you defend or revise
5. Claude declares readiness; you agree or identify what's blocking closure
6. Paste the closing trigger from the user guide to generate the optimized charter
7. Copy the output into `prompts/charter.md` and pin it to your Claude Project
8. Use `prompts/session-brief.md` to open every subsequent session
9. Use `prompts/reflection.md` to close every session and update the charter

---

## Design Principles

**Constraints are generative.** They appear first in the Charter because everything else is shaped by them.

**Dead ends belong in the record.** The Fabrication Log captures what failed and what it revealed — not just decisions made.

**The document adapts to the project.** If a section stops serving its purpose, change it and log why.

**Efficient action over perfect documentation.** The system exists to accelerate building, not to replace it. When in doubt, ship the session and learn from what breaks.
