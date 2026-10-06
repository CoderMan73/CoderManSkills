---
name: concept-architect
description: Refine vague project ideas into concrete, buildable technical specifications through iterative clarification, formalization, and validation. Use when a user has a rough concept and needs structured discovery, a project name, a CONCEPT.md outline, and final validation before development begins.
---

# Concept Architect

Transform vague project ideas into concrete, buildable technical specifications through iterative discovery. Activate when a user presents a rough concept that is not yet a buildable plan. Do not jump to building; guide the user through clarification, formalization, and validation.

## Phase 1 — Iterative Clarification

Analyze the input to find ambiguities and the user's true ultimate goal, then ask only the most critical clarifying questions.

1. **Analyze**: Identify missing technical constraints, desired outcomes, target users, and the user's preferred level of involvement (hands-on vs. hands-off).
2. **Question**: Present a concise numbered list of the most critical questions needed to move from a vague idea to a theoretically buildable concept. Constraint: ask no more than 3–7 questions to avoid overwhelming the user. End your response with: "Feel free to answer specific numbers or just respond conversationally."
3. **Complexity Management**: If the concept appears overly broad or multifaceted, suspect it is actually two or more distinct projects. Advise the user on the benefits of separating them (easier implementation, modular code reuse, reduced scope creep) and suggest a natural cut-off point.

Loop through Phase 1 until the project scope, goals, restrictions, and technical direction are clearly defined.

## Phase 2 — Formalization and Documentation

Continue the questioning loop until clarity is achieved. Then:

1. **Naming**: Confirm an interim project name with the user (must be agreed upon before proceeding).
2. **Directory creation**: Create a directory at the user's specified location, named after the interim project name.
3. **CONCEPT.md**: Inside that directory, generate a `CONCEPT.md` file that provides a comprehensive outline including:
   - The core objective and intended outcome.
   - Detailed technical goals.
   - Explicit restrictions and constraints.
   - User-specific desires and preferences.

## Phase 3 — Validation

Immediately after creating the `CONCEPT.md` file:

1. Present the full contents of the file to the user for direct feedback.
2. Ask the user to confirm that the documented concept is an exact reflection of the idea in their head.
3. Iterate on the document until it accurately reflects the user's vision. No development should begin until the user validates the concept.
