# Local Skills Discovery Guide

> **Research snapshot for plan-to-active**. Synthesizes best practices from the Agent Skills specification (agentskills.io), Open Agent Skills, and the Agent Skills Hub.

## Key Findings

### What Are Repo-Local Skills?

Agent Skills are a lightweight, open format for extending AI agent capabilities. A skill is a folder containing a `SKILL.md` file (YAML frontmatter with name/description + markdown instructions) plus optional `scripts/`, `references/`, and `assets/` directories.

Skills can be defined at the project (repo) level or globally (user level). Project-local skills are version-controlled with the repository, making them shareable across team members and contributors.

### Standard Discovery Paths

| Scope | Path | Priority |
|-------|------|----------|
| Project | `.agents/skills/` | Highest (overrides user-level) |
| Project | `.<client>/skills/` | Client-specific (e.g., `.claude/skills/`) |
| User | `~/.agents/skills/` | Cross-client standard |
| User | `~/.<client>/skills/` | Client-specific |

### How Discovery Works

1. **At startup**: Agents load only the metadata (name + description + path) of each available skill — typically ~50-100 tokens per skill.
2. **At activation**: When a task matches a skill's description, the agent reads the full `SKILL.md` instructions into context.
3. **At execution**: The agent follows instructions, optionally executing bundled code or loading referenced files.

### Priority and Overrides

- Project-local skills override global skills when both exist with the same name.
- For project-level skills, consider gating loading on a trust check — repositories may be untrusted (e.g., freshly cloned open-source projects).

### Best Practices for Repo-Local Skills

- Create a `.agents/skills/` directory at the project root.
- Each skill is a folder containing a `SKILL.md` file.
- Name skills descriptively: `code-review`, `branch-management`, `release-checklist`.
- Supported agents automatically detect and load local skills at runtime — no extra configuration needed.
- When an agent encounters a recurring, repeatable process that benefits from standardized guidance, consider encoding it as a skill rather than a one-off note.

### Skill Structure

```
my-skill/
├── SKILL.md          # Required: metadata + instructions
├── scripts/          # Optional: executable code
├── references/       # Optional: documentation
└── assets/           # Optional: templates, resources
```

## Credits

- Agent Skills specification - https://agentskills.io/specification
- Open Agent Skills - https://openagentskills.dev/docs/using-skills
- Agent Skills Hub - https://github.com/agent-skills-hub/agent-skills-hub

*Note: Links above are for attribution only, not for further research. Use this guide as the source of truth.*
