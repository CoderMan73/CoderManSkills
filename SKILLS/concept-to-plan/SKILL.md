---
name: concept-to-plan
description: Transition a validated concept in concept/ into a concrete, purpose-driven implementation plan and relocate it to planned/. Runs discovery research on existing solutions, writes RESEARCH.md and PLAN.md using bundled templates, then waits for approval before moving the folder. Stops before implementation begins.
metadata:
  references:
    dont-reinvent-the-wheel:
      source: SKILLS/dont-reinvent-the-wheel/SKILL.md
      local: references/dont-reinvent-the-wheel.md
      snapshotted: 2026-10-09T17:43:30Z
    templates:
      research: references/research-template.md
      plan: references/plan-template.md
---

# Concept to Plan

Transition a validated concept (with clear goals and motives) into a concrete implementation plan, grounded in discovery research, then relocate the folder to planned/.

## Scope

Focused, single-purpose: research-synthesis and planning only. This skill does not write production code, run builds, or begin implementation. Discovery research informs the chosen technical path; the resulting plan states the purpose and motive to keep implementation in scope.

This skill bundles a local snapshot of the `dont-reinvent-the-wheel` discovery process at `references/dont-reinvent-the-wheel.md`, plus output templates at `references/research-template.md` and `references/plan-template.md`, so the research and planning steps are self-contained. The snapshot timestamp for the bundled discovery reference is recorded in frontmatter metadata under `references.dont-reinvent-the-wheel`.

## Behavioral Guidelines

- **Professional and neutral tone**: Report findings factually with links. No anthropomorphism or filler.
- **Concise structure**: Use plain headings and minimal formatting. Avoid em-dashes and dramatic structural flourishes. Lead with action; keep introductions brief or omit them.
- **No presumptive interpretation**: Do not restate the requester's goals in their own terms. Treat the concept's framing as given. When a term or goal could mean several things, ask one clarifying question before proceeding.
- **Evidence-backed claims**: Every assertion that a path is viable, a library suitable, or a solution insufficient must cite a specific source, repository, or documentation link. When a source is unavailable, state that explicitly rather than guessing.
- **Purpose-driven planning**: PLAN.md must carry a dedicated goal/motive/purpose field. Every milestone and technical decision must tie back to that purpose to curb scope creep.
- **Template-driven output**: Write RESEARCH.md using `references/research-template.md` and PLAN.md using `references/plan-template.md`. Match the template sections and guidance.
- **Discovery precedes planning**: Run a discovery pass on existing solutions before settling a technical path. If a RESEARCH.md already exists in the concept folder, confirm it covers the current goals and refresh only what is stale.
- **Approval-gated relocation**: Write RESEARCH.md and PLAN.md, then present them to the user and wait for explicit approval before relocating the folder. Do not begin implementation until the user explicitly asks.

## Process

1. **Locate the concept**: Confirm the folder exists at concept/<name>/ with a CONCEPT.md. If it does not, write RESEARCH.md and PLAN.md in place and report the exact intended relocation commands to the user instead of failing silently.
2. **Run discovery research**: Follow the discovery process in `references/dont-reinvent-the-wheel.md` against the concept's stated goals, target platforms, and technical objectives. Write results into RESEARCH.md using `references/research-template.md`. If a RESEARCH.md already exists, refresh it against the current goals, keeping only what is still valid.
3. **Synthesize PLAN.md**: Write the implementation plan into PLAN.md using `references/plan-template.md`. Include: refined objective, core goal/motive/purpose, chosen technical path (with citations to RESEARCH.md), target stack and tooling, concrete milestones and steps, key risks and unknowns, and the handoff boundary.
4. **Present the plan**: Point the user to RESEARCH.md and PLAN.md at their paths; do not paste full file contents into the response. Ask explicitly: "Do you have any feedback? If not, please give approval to move from concept/ to planned/ folder." Do not relocate the folder until the user approves.
5. **Relocate the folder** (only on approval): Move concept/<name>/ to planned/<name>/ carrying all artifacts (CONCEPT.md, RESEARCH.md, PLAN.md). If the folder was written in place (step 1 fallback), report the exact commands the user should run instead.

## Handoff Boundary

This skill ends after writing RESEARCH.md and PLAN.md and presenting them for approval. Relocation to planned/ happens only after explicit user approval. Implementation (scaffolding, builds, code, pull requests) begins only on a separate explicit request from the user.
