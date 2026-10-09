---
name: plan-to-active
description: Transition a project from planned/ to active/ by relocating it, initializing a git repository, and generating foundational files (README.md, CONTRIBUTING.md, CODE_OF_CONDUCT.md, SECURITY.md, LICENSE.md, AGENTS.md, .gitignore, ROADMAP.md, CHANGELOG.md) guided by pre-baked research results in references/. Creates an ai-docs/ subdirectory for AI field notes.
metadata:
  references:
    contributing:
      source: contributing.md/how-to-build-contributing-md
      local: references/contributing-guide.md
      snapshotted: 2026-10-09T19:00:00Z
    readme:
      source: github.com/RichardLitt/standard-readme
      local: references/readme-guide.md
      snapshotted: 2026-10-09T19:00:00Z
    license:
      source: IQAndreas/markdown-licenses/gnu-gpl-v3.0
      local: references/license-gplv3.md
      snapshotted: 2026-10-09T19:00:00Z
    agents:
      source: agents.md/
      local: references/agents-guide.md
      snapshotted: 2026-10-09T19:00:00Z
    gitignore:
      source: github.com/github/gitignore
      local: references/gitignore-guide.md
      snapshotted: 2026-10-09T19:00:00Z
    roadmap:
      source: multiple
      local: references/roadmap-guide.md
      snapshotted: 2026-10-09T19:00:00Z
    conduct:
      source: contributor-covenant.org/version/3/0
      local: references/code-of-conduct-guide.md
      snapshotted: 2026-10-09T19:00:00Z
    changelog:
      source: keepachangelog.com/common-changelog
      local: references/changelog-guide.md
      snapshotted: 2026-10-09T19:00:00Z
---

# Plan to Active

Move a validated project plan from planned/ to active/ and scaffold the foundational files needed to begin active development. All best-practice guidance is frontloaded in references/ rather than fetched at runtime.

## Context: PLAN.md

PLAN.md is the output of the concept-to-plan skill. It contains the project's refined objective, goal/motive/purpose, chosen technical path, target stack, milestones, key risks, and handoff boundary. It is found at `planned/{name}/PLAN.md`.

## Scope

Focused, single-purpose: project initialization and scaffolding only. This skill does not write production code, implement features, or run builds. It generates only repository initialization files, documentation, configuration, and project planning artifacts. All artifacts follow guidance from the pre-baked research snapshots in references/.

## Behavioral Guidelines

- **Professional and neutral tone**: Report actions factually. No anthropomorphism or filler.
- **Concise structure**: Use plain headings and minimal formatting. Avoid em-dashes and dramatic structural flourishes. Lead with action; keep introductions brief or omit them.
- **Guide-backed generation**: Before generating each artifact, read the corresponding snapshot in references/ and use its findings to inform structure and content.
- **One source of truth**: Each reference guide holds the complete instructions for its artifact. Link to it rather than restating its contents here.
- **Evidence-backed claims**: Every structural choice must cite a specific source from the references/ snapshots. When a source is unavailable, state that explicitly.
- **Purpose-driven scaffolding**: Every generated file must serve the project's stated goal in PLAN.md. Do not add files or sections not justified by the plan.
- **User-approved repository creation**: Prompt the user before creating a remote repository. Never create a remote without explicit confirmation. GitHub free tier supports both public and private repositories, but default to public when the user does not specify a preference.
- **Credit-only sources**: Source URLs recorded in this file and in references/ are for attribution only. Do not follow them for further research.
- **No content echo**: After writing each file, point the user to its path. Do not paste full file contents into the response.
- **Self-contained references**: All research results are bundled in references/ as snapshots with timestamps. This skill does not depend on /research or any other skill being loaded at runtime.

## Process

1. **Locate the project**: Confirm the folder exists at `planned/{name}/` with a PLAN.md. PLAN.md is the output of the concept-to-plan skill and contains the project goal, target stack, and milestones.

2. **Copy to working directory**: Copy CONCEPT.md, RESEARCH.md, and PLAN.md from `planned/{name}/` to `E:\Coding_Projects\{name}\`. The planning files remain the source of truth for the tracking workspace; the actual repo is a separate copy at the user's coding directory.

3. **Move to active**: Move `planned/{name}/` to `active/{name}/` in the tracking workspace. This marks the project as having transitioned from planning to active development.

4. **Create manifest**: Create `active/{name}/MANIFEST.md` using the standardized manifest template (see Manifest Template below). The manifest records the transition and points to the working directory at `E:\Coding_Projects\{name}\`.

5. **Initialize git**: Run `git init` in `E:\Coding_Projects\{name}\`. Configure the default branch as `main`.

6. **Prompt for remote repository**: Ask the user whether to create a remote repository using the GitHub CLI. If confirmed, default to public visibility. If the user agrees:
   - Create the repo with the chosen visibility.
   - Generate CONTRIBUTING.md following `references/contributing-guide.md`.

7. **Generate README.md**: Follow `references/readme-guide.md` for structure, badges, and sections. Incorporate PLAN.md goals and target stack.

8. **Generate LICENSE.md**: Use the GNU GPLv3 license text in `references/license-gplv3.md`. Substitute the project name and current year in the copyright line.

9. **Generate CODE_OF_CONDUCT.md**: Follow `references/code-of-conduct-guide.md` for structure. Use the Contributor Covenant 3.0 template.

10. **Generate SECURITY.md**: Link to `references/readme-guide.md` for security policy guidance. Document how to report vulnerabilities and supported versions.

11. **Generate AGENTS.md**: Follow `references/agents-guide.md` for structure and best practices. Create the `ai-docs/` directory with an `ai-docs/README.md` explaining how to record field notes, architectural decisions, and lessons learned between agent sessions. Do not conflate `ai-docs/` with `docs/`.

12. **Generate .gitignore**: Follow `references/gitignore-guide.md`. Use cached language templates in `references/templates/` when the project stack matches (e.g., `Python.gitignore`, `Rust.gitignore`).

13. **Generate ROADMAP.md**: Follow `references/roadmap-guide.md` for structure and required sections.

14. **Generate CHANGELOG.md**: Follow `references/changelog-guide.md` for the Keep a Changelog format. Start with an `[Unreleased]` section.

15. **Initial commit**: Stage all files in `E:\Coding_Projects\{name}\` and create an initial commit with message `chore: initialize active development environment`. If a remote was created, push to the default branch.

16. **Report completion**: Point the user to all generated files at their paths. List next steps from PLAN.md milestones. Do not paste file contents.

## Manifest Template

The `active/{name}/MANIFEST.md` file should follow this exact structure:

```markdown
# {name}

## Status
Active

## Origin
Planning files copied from `planned/{name}/` to `E:\Coding_Projects\{name}\` on {YYYY-MM-DD}. Project folder moved from `planned/{name}/` to `active/{name}/` in the tracking workspace.

## Working Directory
`E:\Coding_Projects\{name}\`
```

## Handoff Boundary

This skill ends after scaffolding all foundational files and creating the initial commit at `E:\Coding_Projects\{name}\`. Implementation of features and milestones from PLAN.md begins only on a separate explicit request from the user.
