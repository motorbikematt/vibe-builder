# CSOT — Project Charter
**Project:** *(project name)*
**Collaborators:** *(your name)* × Claude
**Last updated:** YYYY-MM-DD

---

## 0. Discovery Context

**Problem statement:**
*(One paragraph — who has this problem, what it is, why it matters. Carried forward from the concept brief.)*

**Solution direction:**
*(What we're building and why this approach over alternatives. Two to three sentences.)*

**Assumptions this project depends on:**
- *(assumption — survived concept challenge, carries forward as a thing to watch)*
- *(assumption)*

**What the concept challenge revealed:**
*(Key findings from the adversarial review — residual risks, scope adjustments, architectural decisions made during the challenge. If you skipped the concept challenge, delete this field.)*

---

## 1. Generative Constraints

**Rules this project builds inside:**
- Open source tooling and IP over proprietary, always
- Spec before code — architecture and constraints precede implementation
- Concepts before artifacts — brainstorm before build
- *(add project-specific generative rules — e.g., "offline-first", "no third-party auth", "single binary deploy")*

**Hard limits:**
- *(non-negotiables that cannot be traded away — platform, legal, privacy, performance floor, etc.)*

**Stack:**
- Platform: *(iOS / Android / Web / cross-platform)*
- Framework: *(Flutter, React Native, Next.js, etc.)*
- Backend / infra: *(Firebase, Supabase, self-hosted, etc.)*
- Auth: *(Google OAuth, magic link, etc.)*
- Language: *(Dart, TypeScript, etc.)*

**Environment:**
- OS: *(Windows 11, macOS, etc.)*
- IDE: *(VSCode, etc.)*
- Version control: *(GitHub username)*
- Toolchain status: *(note current state — what's installed, what's broken)*

**Known blockers:**
- *(waiting on API key, pending decision, unresolved dependency — or "none")*

---

## 2. Role & Context

**My role:** Product lead, decision-maker. Final authority on all decisions.

**Claude's role:** Senior technical collaborator. Operates spec-driven — architecture and constraints before code. Asserts positions directly, flags uncertainty explicitly, distinguishes inference from demonstrated fact. Executes unless explanation is prerequisite to a decision. Surfaces observations that would change the next action after task completion.

**Working style contract:**
- Post-graduate register; no pleasantries, no apologetic loops
- Cite discrete factual claims; flag unverifiable ones rather than omitting
- Show the mechanism — expose reasoning, not just conclusions

---

## 3. Problem & Goals

**What we're building:**
*(the app, its core user problem, and who it's for)*

**Primary goal:**
*(the one thing success looks like)*

**Secondary goals:**
*(supporting objectives — UX quality, performance, monetization, learning, etc.)*

**Non-goals / out of scope:**
*(what we're explicitly not solving for right now)*

**Definition of done:**
- [ ] *(specific, observable condition)*
- [ ] *(specific, observable condition)*

---

## 4. Functional Spec

**Core flows:**
1. *(flow name)* — *(why this flow is necessary)*
2. *(flow name)* — *(why this flow is necessary)*

**Key screens / surfaces:**
- *(screen)* — *(origin: what user need or constraint produced this)*

**Data model (working):**
- *(entity)* — *(what it holds and why)*

**Integrations / APIs:**
- *(integration)* — *(origin: why this and not an alternative)*

---

## 5. Fabrication Log

| Date | Entry | Status |
|---|---|---|
| YYYY-MM-DD | *(decision, attempt, or dead end — include what it revealed inline)* | Open / Resolved |

**Standing open questions:**
- [ ] *(question — what would it take to resolve this)*

---
