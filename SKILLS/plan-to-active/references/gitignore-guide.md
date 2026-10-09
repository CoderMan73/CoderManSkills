# .gitignore Guide

> **Research snapshot for plan-to-active**. Synthesizes best practices from GitHub gitignore repository (github/gitignore) and the Node.js, Python, and Rust gitignore templates.

## Key Findings

### Purpose
A .gitignore file specifies intentionally untracked files and directories that Git should ignore. It prevents sensitive files, build artifacts, and dependency directories from being committed to version control.

### GitHub Gitignore Repository Structure
The github/gitignore repository organizes templates as follows:

- Root folder: Templates for common programming languages and technologies
- Global folder: Templates for editors, tools, and operating systems
- Community folder: Specialized templates for less common languages and tools

### Placement
Place .gitignore in the repository root. GitHub surfaces it when someone forks or clones the repository.

### Repository Templates
The following templates are cached locally in `references/templates/`:

- `Python.gitignore` - For Python projects (covers PyInstaller, Django, Flask, Jupyter, pipenv, uv, poetry, pdm, mypy, PyPy, Ruff)
- `Rust.gitignore` - For Rust projects (covers Cargo, rustfmt, rustc, cargo-mutants, RustRover, pdb)

When the project stack matches a cached template, copy from the local template file rather than fetching from the network.

### Best Practices

- Start from a template: Use the relevant template from github/gitignore as a baseline
- Add project-specific ignores: Beyond the standard template, add any project-specific patterns
- Ignore environment files: .env files (but not .env.example)
- Ignore build outputs: build artifacts, dist, target, etc.
- Ignore dependencies: node_modules/, .pnpm-store, etc.
- Ignore logs: *.log, debug logs
- Ignore system files: .DS_Store, Thumbs.db, etc.
- Never ignore: source code, configuration files that are needed, LICENSE, README, package.json

### Common Sections (from Node.js)

```
# Logs
logs
*.log

# Runtime data
pids
*.pid

# Coverage directory
coverage

# Dependency directories
node_modules/

# TypeScript cache
*.tsbuildinfo

# Environment variables
.env
.env.*
!.env.example

# Build outputs
.next
dist

# OS files
.DS_Store
Thumbs.db

# Editor directories
.vscode/
.idea/
```

### Project-Specific Considerations
Beyond language templates, always consider:
- CI/CD artifacts (.github/workflows/*.yml if locally cached)
- Documentation build outputs
- Local development databases
- IDE-specific cache directories
- Package manager caches (.npm, .yarn, .pnpm)
- Secrets and credentials

## Credits

- GitHub gitignore repository - https://github.com/github/gitignore
- GitHub gitignore README - https://raw.githubusercontent.com/github/gitignore/main/README.md
- Node.js gitignore template - https://github.com/github/gitignore/blob/main/Node.gitignore
- Python gitignore template - https://github.com/github/gitignore/blob/main/Python.gitignore
- Rust gitignore template - https://github.com/github/gitignore/blob/main/Rust.gitignore

*Note: Links above are for attribution only, not for further research. Use the cached templates in `references/templates/` as the source of truth for common gitignore patterns.*
