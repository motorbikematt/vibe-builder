# CSOT User Guide (Gemini Edition)

This guide explains the philosophy behind the CSOT system, how to use it with Gemini Gems, and how to maintain your project documentation. Read this once before starting. 

---

## Philosophy

CSOT is built on two converging ideas.

The first comes from Geoffrey Litt's work on malleable software: tools should be inspectable, modifiable, and shaped by the person using them — not delivered sealed from a distance. The CSOT is designed to be taken apart and changed. Section 6 of the charter exists specifically to log amendments to the document's own structure. 

The second comes from Tom Sachs: constraints are not limitations, they are the design. Everything in a Sachs studio is fabricated from what's available, and the welds are left visible. The charter puts generative constraints first and requires every feature in the functional spec to carry its origin — why it exists, not just what it does.

Together these produce a document that is transparent, modifiable, and honest about what is known versus assumed.

---

## The AI Productivity Paradox

The trap this system is designed to avoid: spending more time documenting collaboration than doing it. Every field in these prompts exists because it changes Gemini's behavior. Nothing exists for documentation theater.

By leveraging Gemini Gems, we transition from pasting repetitive instructions to using specialized, persistent agents (Architect, Interviewer, Builder, Librarian). The standard is "sufficient to start and learn" not "perfect."

---

## The System Files

CSOT governs the full lifecycle of a human × AI collaboration: from early problem exploration through concept validation, charter creation, and iterative build sessions. 

**Pre-charter phase (upstream):**
- `problem-framing.md` — Solo thinking tool for exploring unfamiliar problem spaces (optional).
- `concept-brief.md` — Solo template capturing the proposed direction and key assumptions.
- `concept-challenge.md` — Framework for adversarial concept review before committing to a charter.

**Charter phase:**
- `onboarding-interview.md` — Framework that produces the completed charter.
- `charter.md` — The project charter, pinned to your specific Builder Gem's knowledge base.

**Build phase (repeating):**
- `session-brief.md` — Pasted at the start of every session.
- `reflection.md` — Used by the Librarian Gem at the end of sessions.

---

## How to Set Up Your Gemini Gems

Instead of standard chat windows, CSOT uses four specialized Gemini Gems. You configure these once.

### 1. The Upstream Gems (Global Utility)
Create these two Gems to use across all your projects.

**CSOT Architect**
* **Purpose:** Adversarial review of new concepts.
* **Knowledge Base:** Upload `concept-challenge.md` and `problem-framing.md`.
* **Instructions:** Instruct the Gem to execute a 'Concept Challenge' across Technical Feasibility, Scope Risk, Architectural Complexity, and Assumption Fragility. 

**CSOT Interviewer**
* **Purpose:** Converts draft charters into final production artifacts.
* **Knowledge Base:** Upload the blank `charter.md` and `onboarding-interview.md`.
* **Instructions:** Instruct the Gem to act as an interviewer enforcing a strict "max two questions" rule, utilizing the affirm-specify-constrain pattern.

### 2. The Builder Gem (Project-Specific)
Create one of these **for each new project**.

**[Project Name] Builder**
* **Purpose:** Your daily execution partner.
* **Knowledge Base:** Upload your **finalized** `charter.md` and this `user-guide.md`. Update the `charter.md` file here whenever the project scope materially changes.
* **Tools:** Enable Google Search and Code Execution.
* **Instructions:** Define the Gem as the Senior Lead Engineer. Mandate the use of Code Execution to validate technical assumptions before proposing them.

### 3. The Maintenance Gem (Global Utility)
**CSOT Librarian**
* **Purpose:** Synthesizing massive context histories into high-density Fabrication Logs.
* **Knowledge Base:** Upload `reflection.md`.
* **Instructions:** Instruct the Gem to analyze the preceding session's history and output clean Markdown entries for the Fabrication Log, extracting decisions, failures, and constraint changes.

---

## Workflow

```text
ONCE PER PROJECT

  Pre-charter:
  1. Fill problem-framing.md alone (optional).
  2. Fill concept-brief.md alone.
  3. Open CSOT Architect Gem → upload concept brief.
     → complete the challenge.
  4. Pre-fill charter.md Section 0 from concept brief + Architect's findings.

  Charter:
  5. Open CSOT Interviewer Gem → upload pre-filled charter.
     → complete the interview.
  6. Create a new "[Project Name] Builder" Gem → upload the completed charter.md as Knowledge.

EVERY SESSION

  Open  → Open your [Project Name] Builder Gem.
          Paste session-brief.md (fill in scope, done-looks-like, type).
  Build → Work alongside the Builder Gem.
  Close → Open the CSOT Librarian Gem (or ask the Builder Gem to run the Reflection protocol).
          Paste the generated Fabrication Log entries into your local charter.md.
          Re-upload the updated charter.md to your Builder Gem's knowledge base.