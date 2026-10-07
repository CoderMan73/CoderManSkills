---
name: create-skill
description: Generate a new specialized Kilo Code skill on demand in the established project style. Provide a skill name and a brief description of the desired behavior, optionally plus its scope. The skill emits a correctly-structured SKILL.md (YAML frontmatter with name matching the directory, a neutral description, and concise behavioral guidelines following project conventions), writes it to the CoderManSkills SKILLS directory, and tells the user to reload.
---

# Create Skill

Create new specialized skills on demand in the established style without requiring the requester to restate conventions each time. The generator enforces the project's format, tone, and complexity norms, then writes a valid `SKILL.md` into the existing skills directory.

## Input

Required:
- **Skill name**: lowercase letters, numbers, hyphens only; no leading or trailing hyphen; at most 64 characters. Becomes the directory name.
- **Skill description**: one sentence describing what the skill does and when to use it (at most 1024 characters). Written verbatim into frontmatter.

Optional:
- **Scope / complexity**: a short note on depth (for example, "focused, single-purpose") and any constraints to bake in (for example, "ask before writing files", or "no shell commands").

If the request is too vague to produce a confident skill (unclear name, ambiguous purpose, or conflicting scope), ask 2 to 4 targeted clarifying questions before generating.

## Enforced Conventions

Every generated `SKILL.md` must satisfy these rules:
1. **Frontmatter**: `name` equals the directory name; `description` within 1024 characters. Optional `license`, `compatibility`, and `metadata` only when explicitly requested.
2. **Body**: a short objective line, a **Behavioral Guidelines** bulleted list of concise actionable constraints, and a **Process** section describing what the agent does and in what order.
3. **Formatting**: plain headings, minimal formatting, no em-dashes, no dramatic structural flourishes.
4. **Tone**: professional, neutral, concise. No anthropomorphism or fake relatability.
5. **Lead with action**: keep introductions brief or omit them.

## Generation Steps

1. If the request is vague, ask clarifying questions and stop.
2. Create the directory `E:/Coding_Projects/CoderManSkills/SKILLS/<name>/`.
3. Write `SKILL.md` whose frontmatter and body follow all enforced conventions above, using the provided description and any baked-in constraints.
4. Confirm the file was written.
5. Instruct the user to run `/reload`. The `skills.paths` entry in the global config already covers the `SKILLS` parent directory, so no config change is required.

## Output

A single concise message: the path of the written `SKILL.md`, the skill name, and a one-line confirmation that the conventions were applied. End with: run `/reload` to load it.
