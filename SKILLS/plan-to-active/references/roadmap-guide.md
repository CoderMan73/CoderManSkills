# ROADMAP.md Guide

> **Research snapshot for plan-to-active**. Synthesizes best practices from NaCode-Studios ROADMAP-CONVENTIONS, IPFS team-mgmt ROADMAP_HOW_TO, Tenzo standard.md, and nasrulhazim/claude project-roadmap skill.

## Key Findings

### Purpose
A project roadmap provides a visual or structured representation of the project's direction, showing where the project has been, where it is going, and what is currently in progress. It serves as a communication tool to answer questions like "what is shipping this quarter" and "what is the status on feature X".

### Essential Sections

1. **Project Goals** - The core objectives the project aims to achieve
2. **Project Non-Goals** - Explicitly what the project will NOT do (prevents scope creep)
3. **Progress Tracking** - Completed milestones with dates or version references
4. **Current Objectives** - Immediate tasks that are actively being worked on
5. **Out-of-Scope Items** - Explicitly not planned work
6. **Aspirational Goals** - Future "nice-to-haves" or long-term vision items

### Formats Observed

#### Phase/Milestone Format (nasrulhazim/claude project-roadmap)
Uses phases with checkboxes, dependencies, and status tracking:
```
## Phase 0 - Foundation
- [ ] Setup CI/CD
- [ ] Configure linting
```

#### Status-Based Format (NaCode-Studios)
Uses status tokens consistently:
- Shipped: links to CHANGELOG version
- In progress: targeting next version
- Planned: not started
- Deferred: decided against with reason

#### Vision-to-Milestones Format (IPFS)
1. Gather ideas from stakeholders
2. Draft top-level goals (vision statement)
3. Chunk progress into milestones
4. Assign projects to milestones
5. Iterate with stakeholders

### CI/CD Caution
CI/CD should be configured thoughtfully, not exhaustively. Avoid running builds on every push across all platforms unless necessary. Local CI/CD (e.g., pre-commit hooks) is preferred for early feedback. Remote CI/CD (e.g., GitHub Actions) should be reserved for meaningful validation gates (tests, type checking, security scanning) rather than redundant platform matrix builds. Consider using a single primary CI job and extending only when cross-platform behavior is genuinely at risk.

### CHANGELOG Reference
When documenting shipped milestones, link to CHANGELOG.md entries. See `references/changelog-guide.md` for CHANGELOG.md best practices based on Keep a Changelog and Common Changelog conventions.

### Best Practices

- Clear status vocabulary: Use exact, consistent status values
- Tie to versions: Milestones should reference released versions
- Include dates or ETAs: Time windows for phases/milestones
- Separate shipped from planned: Don't leave completed work in active view
- Non-goals are important: Actively prevent scope creep
- Dependency mapping: Show what can run in parallel vs. sequential
- Testable acceptance criteria: Each phase/milestone has observable conditions
- Update cadence: Refresh when milestones ship

## Structure Template

```markdown
# [Project Name] Roadmap

## Project Goals

[Core objectives the project aims to achieve]

## Project Non-Goals

[Explicitly what the project will NOT do]

## Shipped

### v1.0.0 - [Date]
- [Completed milestone, link to CHANGELOG entry]

## Current Objectives

### Phase/Milestone: [Name]
- [ ] [Task]
- [ ] [Task]

## Planned

[Future milestones with approximate timelines]

## Out of Scope

[Items explicitly not planned]

## Aspirational Goals

[Future "nice-to-haves" or long-term vision items]
```

## Credits

- NaCode-Studios ROADMAP-CONVENTIONS - https://github.com/NaCode-Studios/Kmemo/blob/main/ROADMAP-CONVENTIONS.md
- IPFS team-mgmt ROADMAP_HOW_TO - https://github.com/ipfs/team-mgmt/blob/master/ROADMAP_HOW_TO.md
- Tenzo standard.md - https://github.com/CatOfJupit3r/tenzo/blob/refs/heads/main/standard.md
- nasrulhazim/claude project-roadmap skill - https://github.com/nasrulhazim/claude/blob/main/skills/project-roadmap/SKILL.md
- gsd-core roadmap template - https://github.com/open-gsd/gsd-core/blob/next/gsd-core/templates/roadmap.md

*Note: Links above are for attribution only, not for further research. Use this guide as the source of truth.*
