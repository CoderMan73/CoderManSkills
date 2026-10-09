# CHANGELOG.md Guide

> **Research snapshot for plan-to-active**. Synthesizes best practices from Keep a Changelog and Common Changelog. Source links in Credits section are for attribution only, not for further research.

## Key Findings

### Purpose
A changelog is a file containing a curated, chronologically ordered list of notable changes for each version of a project. It helps users and contributors see what changed between releases.

### Recommended Standard
Keep a Changelog is a widely adopted convention. It sits on top of Semantic Versioning. The file must be named `CHANGELOG.md` and placed in the repository root.

Common Changelog is a stricter subset that emphasizes human readers and references to commits/PRs.

### Keep a Changelog Format

Structure:
```markdown
# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- For new features

### Changed
- For changes in existing functionality

### Deprecated
- For soon-to-be removed features

### Removed
- For now removed features

### Fixed
- For any bug fixes

### Security
- In case of vulnerabilities

## [1.0.0] - YYYY-MM-DD

### Added
- Initial release
```

### Types of Changes (in order)
1. `Added` - new features
2. `Changed` - changes in existing functionality
3. `Deprecated` - soon-to-be removed features
4. `Removed` - now removed features
5. `Fixed` - bug fixes
6. `Security` - vulnerabilities

### Guiding Principles
- Changelogs are for humans, not machines
- There should be an entry for every version
- The latest version comes first
- The release date of each version is displayed
- Mention whether you follow Semantic Versioning
- Keep an `Unreleased` section at the top to track upcoming changes
- Use ISO 8601 date format: YYYY-MM-DD
- Breaking changes should be marked in bold

### Date Format
Use ISO 8601: YYYY-MM-DD (e.g., 2024-01-15). This avoids regional ambiguity.

### Unreleased Section
Keep a `## [Unreleased]` section at the top. Move entries into a new version heading at release time.

## Credits

- Keep a Changelog - https://keepachangelog.com/en/1.1.0/
- Keep a Changelog repository - https://github.com/olivierlacan/keep-a-changelog
- Common Changelog - https://common-changelog.org/

*Note: Links above are for attribution only, not for further research. Use this guide as the source of truth for writing CHANGELOG.md.*
