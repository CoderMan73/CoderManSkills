# README.md Guide

> **Research snapshot for plan-to-active**. Synthesizes best practices from standard-readme spec, shields.io, Jupyter Team Compass, and GitHub documentation.

## Key Findings

### Standard Readme Spec (RichardLitt/standard-readme)
A compliant README must satisfy these section requirements, appearing in order:

1. **Title** - The project name
2. **Banner** - Optional visual header
3. **Badges** - Build status, coverage, package version (use shields.io)
4. **Short Description** - One to two sentences
5. **Long Description** - Detailed explanation
6. **Table of Contents** - Linkable sections
7. **Security** - Security reporting policy
8. **Background** - Motivation, context
9. **Install** - Installation instructions
10. **Usage** - Code examples with common usage
11. **Extra Sections** - API, Examples, FAQ, Changelog, etc.
12. **API** - API documentation if applicable
13. **Maintainers** - List of maintainers
14. **Thanks** - Acknowledgments
15. **Contributing** - Link to CONTRIBUTING.md
16. **License** - License reference

### Security Policy
A security policy (SECURITY.md) details how to report security vulnerabilities. GitHub provides built-in security policy setup. The README should link to SECURITY.md so users know how to report vulnerabilities safely without creating public issues.

The security section should include:
- Link to SECURITY.md or a note about how to report vulnerabilities
- Supported versions table (if applicable)
- Reporting instructions

### Badges (shields.io)
- Use shields.io for consistent, professional badges
- Place near the top of the README
- Avoid excessive badges; keep it clean and readable
- Badge format: `[![Alt Text](badge-url)](link-url)`

### Best Practices

- **First paragraph**: Explain what the project does and why it matters
- **Installation**: Clear, platform-specific commands with prerequisites
- **Usage**: Code blocks with common use cases
- **Not broken links**: Verify all links work
- **Linted code examples**: Match project's linting rules
- **Security section**: Include security policy link
- **Contributing section**: Link to CONTRIBUTING.md

## Structure Template

```markdown
# [Project Name]

[Short description - one to two sentences explaining what the project does]

## Badges

[![Build Status](https://img.shields.io/badge/build-status.svg)](link)
[![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg)](link)

## Description

[Longer description explaining the purpose, motivation, and what the project does in detail]

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Security](#security)
- [Contributing](#contributing)
- [License](#license)

## Installation

[Prerequisites and installation steps]

```bash
# Installation command
```

## Usage

[Common usage examples with code blocks]

```bash
# CLI usage example
```

```javascript
// Library usage example
```

### CLI

[If applicable: CLI-specific usage]

## Security

[Link to security policy and reporting instructions]

## Contributing

[Link to CONTRIBUTING.md]

## License

[License name] - see [LICENSE.md](LICENSE.md) for details.
```

## Credits

- standard-readme spec - https://github.com/RichardLitt/standard-readme/blob/HEAD/spec.md
- standard-readme repository - https://github.com/RichardLitt/readme-standard
- shields.io - https://shields.io/
- shields.io README - https://github.com/badges/shields/blob/master/README.md
- Jupyter Team Compass - https://compass.hub.jupyter.org/practices/readme-badges/
- GitHub security best practices - https://github.com/github/opensource.guide/blob/main/articles/pcm/security-best-practices-for-your-project.md
- GitHub security policy docs - https://docs.github.com/en/code-security/how-tos/report-and-fix-vulnerabilities/configure-vulnerability-reporting/add-security-policy

*Note: Links above are for attribution only, not for further research. Use this guide as the source of truth.*
