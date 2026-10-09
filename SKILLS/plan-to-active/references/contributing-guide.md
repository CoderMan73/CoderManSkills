# CONTRIBUTING.md Guide

> **Research snapshot for plan-to-active**. Synthesizes best practices from contributing.md, CNCF contribute guide, GitHub Docs, and Glasskube developer experience analysis.

## Key Findings

### Purpose
CONTRIBUTING.md is reference material for developers who want to understand what work is available and how to get involved quickly. It is accessed when someone opens a pull request or creates an issue.

### Placement
CONTRIBUTING.md should be placed in the project root directory, along with README.md and LICENSE.md. GitHub surfaces it in the repository overview and sidebar.

### Essential Sections

1. **Introduction** - Welcoming message, brief statement of encouragement for contributions
2. **Table of Contents** - Linkable sections for skimability
3. **Provide Links** - Resource links, templates, test locations, submit changes link, development environment details
4. **How To Details**:
   - How to make a bug report
   - How to fix a bug (guidelines, style examples)
   - How to suggest enhancements (link to template)
   - Coding conventions and style guide (commit message format, file naming)
5. **Housekeeping**:
   - Code of Conduct - see `references/code-of-conduct-guide.md` for template and best practices
   - Security Reporting - link to SECURITY.md
   - Recognition section (thank you to contributors)
   - Project owner and contributors information
   - Where to get help (communication channels)

### Best Practices

- **Clear and actionable**: Use precise language, avoid vague instructions
- **Easy to skim**: Use clear headings, bullet points, tables
- **Point to additional resources**: Link to deeper docs rather than duplicating
- **Include a TL;DR**: Main points for quick reference
- **Development environment**: Provide enough info to set up, build, test, and submit a PR without questions
- **Testing**: Clear instructions for running tests locally before submitting a PR
- **Forking and branching**: Step-by-step guide for forking, branching, coding, committing, and submitting PRs
- **Commit conventions**: Specify tense, character limits, emoji usage, issue/PR referencing

## Structure Template

```markdown
# Contributing to [Project Name]

Thank you for your interest in contributing to [Project Name]! We welcome contributions from the community.

## Table of Contents

- [Getting Started](#getting-started)
- [How to Report a Bug](#how-to-report-a-bug)
- [How to Fix a Bug](#how-to-fix-a-bug)
- [How to Suggest Enhancements](#how-to-suggest-enhancements)
- [Development Environment](#development-environment)
- [Coding Conventions](#coding-conventions)
- [Pull Request Process](#pull-request-process)
- [Code of Conduct](#code-of-conduct)

## Getting Started

[Link to README.md installation instructions]

## How to Report a Bug

1. Check existing issues
2. Use the bug report template
3. Include: expected behavior, actual behavior, reproduction steps, environment

## How to Fix a Bug

- Check style guides and examples for different scripts
- Reference issue and PR labels

## How to Suggest Enhancements

- Link to enhancement suggestion template
- Encourage testing of suggested enhancements

## Development Environment

- How to set up development environment
- How to get the source code
- How to retrieve dependencies
- How to build the source code
- How to run the project locally
- How to run tests

## Coding Conventions

- Commit message format: present tense, imperative mood, first line limit
- File naming conventions
- Code style guide

## Pull Request Process

1. Fork the repository
2. Create a branch
3. Make changes
4. Submit pull request
5. Address review feedback
6. Merge after approval

## Code of Conduct

[Link to CODE_OF_CONDUCT.md or see references/code-of-conduct-guide.md for template]
```

## Credits

- contributing.md "How to Build a CONTRIBUTING.md" - https://contributing.md/how-to-build-contributing-md/
- CNCF contribute guide - https://contribute.cncf.io/projects/best-practices/templates/contributing.md
- GitHub Docs "Setting guidelines for repository contributors" - https://docs.github.com/en/enterprise-cloud@latest/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors
- contributing.md homepage - https://contributing.md/
- Glasskube blog "contributor guidelines" - https://glasskube.dev/blog/contributor-guidelines/
- Code of Conduct guide - see `references/code-of-conduct-guide.md` (source: https://www.contributor-covenant.org/version/3/0/code_of_conduct/)

*Note: Links above are for attribution only, not for further research. Use this guide as the source of truth.*
