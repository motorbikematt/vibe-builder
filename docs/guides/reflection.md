# Quick Guide: Reflection

**File:** `prompts/reflection.md`
**Phase:** Build (repeating)
**Mode:** Paste at the end of every session. Claude pre-fills; you confirm or correct.

---

## What happens

Claude reviews the full session context and pre-fills answers to nine reflection questions. You confirm, correct, or add anything Claude couldn't determine. Claude then generates formatted Fabrication Log entries ready to paste into the charter.

## The nine questions

1. What did we set out to do this session?
2. What did we actually accomplish?
3. What did we attempt that didn't work, and why?
4. What assumption turned out to be wrong?
5. What constraint surfaced that wasn't in the charter before this session?
6. What decision did we make that can't easily be undone?
7. What is clearer now than it was at the start of this session?
8. What is still unresolved, and what would it take to resolve it?
9. Does anything in the charter need to change based on what we learned?

Claude skips questions that don't apply. It asks one constrained follow-up on ambiguous answers before generating the log entry — it does not guess.

## Context rot risk

This prompt depends on Claude having coherent recall of the full session. Run it earlier than feels necessary. If you're seeing context rot warning signs (hedged responses, rehashed approaches, contradictions), trigger reflection immediately rather than waiting for session close. You can run reflection mid-session, start fresh, and continue.

---

## What happens next

Paste the generated Fabrication Log entries into the pinned `charter.md`. If question 9 surfaces a change large enough to revisit the concept, the next session type is "pivot."
