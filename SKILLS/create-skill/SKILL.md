---
name: create-skill
description: Generate a new specialized Kilo Code skill on demand in the established project style, in either single-file (SKILL.md only) or multi-file (SKILL.md plus references/templates/scripts) form based on complexity triage. Provide a skill name and a brief description of the desired behavior, optionally plus its scope. The skill writes valid SKILL.md (YAML frontmatter with name matching the directory, a neutral description, and concise behavioral guidelines following project conventions) and any named auxiliary files into the CoderManSkills SKILLS directory, then tells the user to reload.
---

# Create Skill

Create new specialized skills on demand in the established style without requiring the requester to restate conventions each time. The generator enforces the project's format, tone, and complexity norms, then writes a valid `SKILL.md` into the existing skills directory.

## Input

Required:
- **Skill name**: lowercase letters, numbers, hyphens only; no leading or trailing hyphen; at most 64 characters. Becomes the directory name.
- **Skill description**: one sentence describing what the skill does and when to use it (at most 1024 characters). Written verbatim into frontmatter.

Optional:
- **Scope / complexity**: a short note on depth (for example, "focused, single-purpose") and any constraints to bake in (for example, "ask before writing files", or "no shell commands").
- **Auxiliary files**: when the skill's process depends on more than SKILL.md alone — templates for structured output artifacts, bundled reference snapshots from other skills, or reusable helper scripts — list each file and its path under `references/`, `templates/`, or `scripts/`.

If the request is too vague to produce a confident skill (unclear name, ambiguous purpose, or conflicting scope), ask 2 to 4 targeted clarifying questions before generating.

### Complexity triage

After receiving the request, ask one question to decide the generation tier: "Does this skill's process reference template files, bundle reference snapshots, or require helper scripts?"

- **If no**: generate a single `SKILL.md`.
- **If yes**: generate `SKILL.md` plus the named auxiliary files in `references/` and/or `scripts/`.

Use the multi-file criterion (below) to confirm.

### Multi-file criterion

Generate auxiliary files when any of the following hold:
- The skill's Process references template files for structured output artifacts (e.g., "write X using references/x-template.md").
- The skill bundles a local copy of another skill or discovery process for self-containment.
- The skill needs reusable helper scripts beyond SKILL.md.
- The skill caches boilerplate artifacts (e.g., gitignore patterns, license texts) in a `templates/` subdirectory to minimize webfetches at skill-use time.
- The Scope note explicitly names templates, references, or bundled resources.

Otherwise a single `SKILL.md` is sufficient.

## Enforced Conventions

Every generated `SKILL.md` must satisfy these rules:
1. **Frontmatter**: `name` equals the directory name; `description` within 1024 characters. Optional `license`, `compatibility`, and `metadata` only when explicitly requested. For multi-file skills, record bundled reference snapshot timestamps under `references.<name>` in metadata.
2. **Body**: a short objective line, a **Behavioral Guidelines** bulleted list of concise actionable constraints, and a **Process** section describing what the agent does and in what order.
3. **Formatting**: plain headings, minimal formatting, no em-dashes, no dramatic structural flourishes.
4. **Tone**: professional, neutral, concise. No anthropomorphism or fake relatability.
5. **Lead with action**: keep introductions brief or omit them.
6. **Scope context reconciliation**: before generating, check `SKILLS/` and `SKILLS/research/` for prior skills with the same name or overlapping purpose; surface conflicts rather than overwriting silently.
7. **Frontloaded research**: when a skill's process involves external research, bake the research results into `references/` files rather than directing the agent to invoke `/research` or other research skills at runtime. Use a `templates/` subdirectory for cached boilerplate artifacts (gitignore patterns, license texts, etc.).
8. **One source of truth**: a step's instructions live in exactly one place — fully in the SKILL.md Process section, or in a single linked reference file. Never duplicate instructions across both. If detail exceeds a one-line description, link to the guide and treat it as the sole source.
9. **Credit-only attribution**: when reproducing or deriving from external sources in reference or template files, include attribution links (e.g., in a consolidated Sources section at the bottom of each file). Label them as credit-only — not for further research.
10. **Path safety**: use `{name}` notation inside backticks for path placeholders (e.g., `` `SKILLS/{name}/` ``); never use HTML entities like `<name>` in file paths, as some markdown renderers interpret them as tags, corrupting path construction.
11. **Error handling**: if a bash command times out or blocks, report the failure and proceed using alternative read-only approaches rather than abandoning the error silently.

## Generation Steps

1. If the request is vague, ask clarifying questions and stop.
2. Run complexity triage: ask whether the skill references template files, bundles reference snapshots, caches boilerplate in a `templates/` subdirectory, or requires helper scripts.
3. If the skill involves research, conduct the research now and bake results into `references/` files (including a `templates/` subdirectory for cached boilerplate). Do not direct the agent to invoke `/research` at runtime.
4. Create the directory `E:/Coding_Projects/CoderManSkills/SKILLS/{name}/`.
5. Write `SKILL.md` whose frontmatter and body follow all enforced conventions above, using the provided description and any baked-in constraints.
6. If multi-file: also write each named auxiliary file (`references/*.md`, `scripts/*.py`, `templates/*.gitignore`, etc.) using the project's conventions. Record snapshot timestamps under `references.*` in frontmatter metadata.
7. Confirm all written files.
8. Instruct the user to run `/reload`. The `skills.paths` entry in the global config already covers the `SKILLS` parent directory, so no config change is required.

## Output

A single concise message: the path of the written `SKILL.md`, the written auxiliary file paths (if any), the skill name, and a one-line confirmation that the conventions were applied. End with: run `/reload` to load it.
