# Quick Guide: Onboarding Interview

**File:** `prompts/onboarding-interview.md`
**Phase:** Charter
**Mode:** Interactive — Claude interviews, you answer and defend
**Session:** Single-use. Open a fresh Claude session; do not reuse for build work.
**Attach:** Your partially-filled `charter.md` with Section 0 pre-filled from the concept brief and concept challenge findings

---

## What happens in this session

Claude works through the charter's sections in order, asking follow-up questions where answers are thin, challenging contradictions, and arguing when a constraint and a goal are in tension. The interview closes when all sections are covered — not when the topic is exhausted.

Claude follows these interaction rules: no more than two questions at a time, no summarizing your answers back to you, no performative agreement. If a field remains underspecified after two iterations, it gets deferred to the Fabrication Log as an open question.

## Closing the interview

When you are satisfied the charter is ready, paste this exact text:

```
The interview is closed. Produce the final token-optimized charter now.
```

This trigger exists because the session can run long enough for context degradation to affect recall of the output format instruction. The trigger re-states it at the moment it's needed. Do not skip it.

---

## What happens next

Copy Claude's output into `charter.md`. Pin it to your Claude Project. Use `session-brief.md` to open every subsequent session.
