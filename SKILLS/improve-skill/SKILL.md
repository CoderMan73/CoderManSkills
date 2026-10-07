---
name: improve-skill
description: Perform a comprehensive post-mortem of a skill interaction to drive continuous improvement. Provide a specific session title (to be looked up via kilo_local_recall) or a raw transcript, plus the skill name being evaluated. Identifies recurring patterns, successful techniques, friction points, and extracts optimized system instructions, refined behavioral constraints, and strategic frameworks for the next skill iteration.
---

# Improve Skill

Drive continuous improvement of a skill by post-mortem analysis of a real interaction. The agent acts as a neutral reviewer of a skill's execution and produces a structured plan for the skill's next version.

## Input

Invoke with **either**:
- A **session title** — look it up and read the full transcript using `kilo_local_recall` (search, then read by ID).
- A **raw transcript** — use the pasted interaction directly.

Also identify the **skill under review** (`[SKILL-NAME]`).

## Post-Mortem Framework

### 1. Reconstruct and segment
Read the full transcript. Segment it into: user intents, agent turns, tool actions, and user corrections/clarifications. Note where intent shifted (e.g., plan → execute, or unclear → refined).

### 2. Recurring patterns
List patterns that recurred across turns — distinct successes (behaviors the skill got right, consistently) from systemic habits (consistent flaws). Note frequency and impact.

### 3. Successful prompting techniques
Enumerate specific techniques that produced good outcomes (e.g., grounded questions, disambiguation by inquiry, proposal-first validation, solicited-only recommendations, context reconciliation, intent-pivot on clarification). Cite the turn.

### 4. Friction points
Identify where the skill misaligned with its own constraints or the user's intent: premature tool cascades before clarifying, unsolicited roadmaps/architecture, presuming intent, inventing default tools, execution drift, conflating unrelated prior concepts, blunt legalizing vs. neutral confirmation. Cite the turn and the violated principle.

### 5. Constraint audit
Map findings to the skill's stated behavioral constraints. Which held? Which failed or were absent? Note gaps — constraints the skill needs that it currently lacks.

### 6. Root-cause hypotheses
For each recurring flaw, posit a testable root cause (e.g., "missing execution-resistance constraint → agent drifts into tool work").

## Deliverable

Present a structured report with exactly these three sections:

### 1. Optimized system instructions
Concrete, reworded instructions the skill should adopt. These are the "next version" of the skill's core rules — how to triage intent, when to ask vs. ground, how to propose.

### 2. Refined behavioral constraints
Tightened rules derived from failures. Each must close a specific gap found in sections 4–5 (e.g., "Front-load intent triage"; "Scope context reconciliation to the same concept only"; "Resist execution drift: document and validate, never execute without explicit permission").

### 3. Strategic frameworks
A reusable decision/turn framework for future runs of the skill (e.g., Triage → Question → Ground(minimally) → Document(draft) → Validate → Execute-if-confirmed), plus guardrail phrasing the skill should use to stay on-mode.

Optionally recommend applying the top 1–2 refinements to the skill's `SKILL.md`.

## Tone
Professional, neutral, and concise. Lead with findings; avoid lengthy narrative.
