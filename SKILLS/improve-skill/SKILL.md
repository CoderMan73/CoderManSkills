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

1. **Post-mortem report** — run the six post-mortem steps as internal rationale.
2. **Apply** — edit the reviewed skill's `SKILL.md` directly to enact the clear, additive refinements derived from the report. Do not gate on user confirmation.
3. **Summarize** — concisely report what changed and why, as applied facts.

### Report structure (rationale for the applied changes)
Keep the three-section structure as supporting analysis:
- **Optimized system instructions**: reworded core rules for the skill's next version.
- **Refined behavioral constraints**: tightened rules that close specific gaps found in friction points.
- **Strategic frameworks**: a reusable decision/turn framework plus guardrail phrasing.

### Execution rules
- **Apply, don't ask**: when findings are clear and changes are additive, enact them directly in the reviewed skill's `SKILL.md`. Only surface — never gate — genuinely destructive or ambiguous changes.
- **Walk your own talk**: improve-skill applies its own recommendations. If the post-mortem reveals the skill should apply directly rather than propose, it does so without waiting for confirmation.
- **One-line summary per change**: report each edit as an applied fact, not a proposal awaiting approval.

## Tone
Professional, neutral, and concise. Lead with findings as applied changes; avoid lengthy narrative.
