# AGENTS.md Guide

> **Research snapshot for plan-to-active**. Synthesizes best practices from agents.md, SSOT docs/README_AGENTS, googlarz/agents-sync, sergiusavva ai-context-docs-lifecycle, and gist by jerdaw.

## Key Findings

### Purpose
AGENTS.md is a simple, open format for guiding coding agents. Think of it as a "README for agents" - a dedicated, predictable place to provide context and instructions that help AI coding assistants work on your project. It complements README.md by containing the detailed context agents need (build steps, tests, conventions) that might clutter a human-focused README.

### Key Distinction
- README.md is for humans (project orientation, high-level description)
- AGENTS.md is for agents (operational instructions, commands, conventions)
- ai-docs/ is for AI field notes, decisions, and lessons learned between sessions

### Recommended Sections

1. **Agent Role** - Define a specialist persona, not a generic "helpful assistant"
2. **Tech Stack** - Technologies with versions in a table
3. **Key Commands** - Full syntax with flags (build, test, lint, run)
4. **Architecture** - System design, data flow, key patterns with code examples
5. **Code Style and Conventions** - Observable rules with real code examples
6. **Testing** - How to run tests, coverage expectations
7. **Boundaries** (Three-Tier):
   - **Always** - Must do by default
   - **Ask First** - Requires human approval
   - **Never** - Hard prohibitions
8. **Context Loading** - When to read which docs/skills
9. **Gotchas** - Known pitfalls, surprising behavior, non-obvious constraints
10. **ai-docs** - Instructions for the ai-docs/ subdirectory

### Best Practices

- **Keep concise**: Aim for 50-200 lines in root AGENTS.md
- **Prefer links**: Point to deeper docs instead of duplicating
- **Commands early**: Include full syntax with flags near the top
- **Short, actionable instructions**: Copy-paste runnable commands
- **Tool-agnostic**: Route to docs and skills by name, not tool-specific syntax
- **Living document**: Update when patterns change or agents make mistakes
- **Self-documenting code**: Write code so clear it needs no comments
- **Mark user-specified content**: Sections that AI must not modify

### The ai-docs / Field Notes Pattern

```
project/
  AGENTS.md                 # Router for agents (50-80 lines)
  ai-docs/                  # AI field notes, decisions, lessons learned
    README.md               # Explains how to record field notes
    decisions/              # Architectural decision records
    notes/                  # Debugging discoveries, non-obvious fixes
  docs/                     # Human-facing documentation only
```

The `ai-docs/` subdirectory is specifically for AI agents to record and retrieve knowledge:
- Field notes (hard-won solutions, non-obvious fixes)
- Architectural decisions (lightweight ADRs)
- Lessons learned (patterns that worked or failed)
- Non-trivial debugging discoveries

Do NOT use `docs/` for AI field notes. The `docs/` directory is for human-facing documentation. AI agents should only write to `docs/` when explicitly asked to write documentation as a deliverable.

Each ai-docs entry should be timestamped with context about the problem, the solution, and why it matters. Entries should be written as if the next agent reading them has no prior context.

## Structure Template

```markdown
# AGENTS.md - [Project Name]

## Agent Role

The agent is a [specialist role] for [project purpose]. Prioritize [key priorities].

## Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| [Language] | [version] | [purpose] |

## Key Commands

[build command]        # Build the project
[test command]         # Run tests
[lint command]         # Lint and type-check
[run command]          # Run locally

## Architecture

- [Key directories and what lives in them]
- [Entry points]
- [Data flow patterns]

## Code Style and Conventions

- [Observable, falsifiable rules with examples]

## Testing

- **Framework**: [test framework]
- **Run all**: [command]
- **Coverage target**: [percentage]

## Boundaries

### Always
- [Must do by default]

### Ask First
- [Requires human approval]

### Never
- [Hard prohibitions]

## Context Loading

| Task | Read |
|------|------|
| [task] | [docs/skills to load] |

## Gotchas

- [Surprising behaviors, footguns]

## ai-docs

This project uses an `ai-docs/` subdirectory for field notes, architectural decisions, and lessons learned. See `ai-docs/README.md` for guidelines on recording and retrieving knowledge between agent sessions.

## When to Update

- Add to Boundaries when the agent makes a preventable mistake
- Update Tech Stack when dependencies are upgraded
- Add code examples when new patterns are established
```

## Credits

- agents.md official site - https://agents.md/
- SSOT docs/README_AGENTS - https://github.com/artificial-intelligence-first/ssot/blob/main/docs/README_AGENTS.md
- agents-sync spec - https://github.com/googlarz/agents-sync/blob/main/docs/agents-md-spec.md
- AI Context Docs Lifecycle - https://sergiusavva.github.io/ai-context-docs-lifecycle/guides/agents-md-best-practices/
- AGENTS.md Best Practices gist - https://gist.github.com/jerdaw/3917eab775d3e4bbcf37928101fbc3db

*Note: Links above are for attribution only, not for further research. Use this guide as the source of truth.*
