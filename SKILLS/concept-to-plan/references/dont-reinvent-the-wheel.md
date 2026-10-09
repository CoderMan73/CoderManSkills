---
name: dont-reinvent-the-wheel
description: Exhaustively research the existing technology landscape for a given problem or idea. Prioritize web and source-code searching to verify uniqueness, analyze gaps where solutions fall short, and identify reusable foundations. Produces a discovery report, not an implementation.
---

> **Reference snapshot**: Local copy of the `dont-reinvent-the-wheel` skill for self-contained use by `concept-to-plan`. Source: `SKILLS/dont-reinvent-the-wheel/SKILL.md`. Snapshotted: 2026-10-09T17:43:30Z.

# Don't Reinvent the Wheel

Before any implementation work begins, conduct an exhaustive discovery pass to determine what already exists for a given problem or idea. The goal is to inform development decisions with the current landscape of existing technology, avoid redundant effort, and surface reusable foundations.

## Scope

Focused, single-purpose: exhaustive discovery of existing solutions. This skill performs research only. It does not estimate feasibility, write code, or run builds.

## Behavioral Guidelines

- **Research depth over speed**: Cast a wide net across package registries, source repositories, documentation, forums, and community discussions. Prefer primary sources (READMEs, source code, commit history) over secondary summaries.
- **Professional and neutral tone**: Report findings factually with links. No anthropomorphism or filler.
- **Concise structure**: Use plain headings and minimal formatting. Avoid em-dashes and dramatic structural flourishes. Lead with action; keep introductions brief or omit them.
- **Evidence-backed claims**: Every assertion that a solution is unique, incomplete, or usable as a foundation must cite a specific source, repository, or documentation link. When a source is unavailable, state that explicitly rather than guessing.
- **No presumptive interpretation**: Do not restate the idea in your own terms. Treat the requester's framing as given. When a term or goal could mean several things, ask one clarifying question before searching broadly.
- **Scope context reconciliation**: Check open files and tabs in the working directory for prior versions of the same concept or prior research. Reconcile differences before searching, and surface any prior findings you build on.
- **No implementation drift**: Discovery only. Do not prototype, patch, or modify identified projects. If a follow-up implementation is requested, flag the shift explicitly.

## Discovery Objectives

1. **Uniqueness Verification**: Determine whether the idea is entirely unique and currently unimplemented. Search package managers, public repositories, blogs, academic papers, and forum discussions. A finding that a complete solution already exists is a terminal result for this skill.

2. **Gap Analysis**: Where existing solutions exist but do not fully address the specific nuances of the proposed idea, document the precise gaps. Identify which requirements, platforms, languages, or constraints the existing solutions do not cover. Distinguish a genuine uncovered gap from a feature request that could be filed upstream.

3. **Foundation Identification**: Locate existing projects, libraries, frameworks, or implementations that can serve as a robust starting point. Evaluate each candidate on maturity (active maintenance, license, documentation, community adoption) and structural fit (architecture, data model, extension points). Rank candidates from strongest to weakest foundation.

## Discovery Process

1. **Define search anchors**: Extract the core keywords, domain, target platforms, and distinguishing features from the idea. Use these to scope all subsequent searches.
2. **Search package registries and repositories**: Query npm, PyPI, crates.io, Maven, GitHub, GitLab, and SourceForge using the anchors. Inspect READMEs and source for actual behavior versus claims.
3. **Search broader sources**: Query general web search, documentation sites, academic indexes, Stack Overflow, Reddit, and relevant community forums.
4. **Evaluate candidates**: For each promising hit, assess uniqueness, gaps, and suitability as a foundation. Record license, last activity, and known limitations.
5. **Synthesize the report**: Deliver a structured discovery report covering the three objectives (see Report Structure).

## Report Structure

1. **Executive summary** (unique, partially unique, or redundant; one-sentence rationale).
2. **Existing Solutions Survey** (every relevant project found, with links, brief description, and status).
3. **Uniqueness Verification** (the strongest evidence that the idea is or is not already implemented).
4. **Gap Analysis** (where solutions fall short of the proposed idea; specific uncovered nuances).
5. **Foundation Candidates** (ranked list of projects suitable as a starting point, with fit assessment and caveats).
6. **Unknown Areas** (what could not be verified and what additional search would resolve it).

If a complete existing solution is found, the report should lead with that finding and its confidence level, rather than proceeding to a full survey.
