# Discr Documentation - Project Memory

This file contains persistent context for Claude Code sessions on this project.
It will be automatically loaded at the start of every session.

## Project Overview

This repository contains all documentation for the Discr project, including
architecture decisions, API documentation, user guides, and development workflows.

**Key Details:**

- **Purpose:** Centralized documentation repository
- **Format:** Markdown with proper linting
- **CI/CD:** GitHub Actions with release workflow
- **Linting:** Pre-commit hooks for markdown and YAML

## Repository Structure

```text
docs/
├── .github/workflows/     # CI/CD workflows
├── architecture/          # Architecture decision records (ADRs)
├── api/                   # API documentation
├── guides/                # Development and user guides
├── README.md
└── CLAUDE.md
```

## Documentation Standards

### Markdown Guidelines

- Follow markdownlint rules
- Use proper heading hierarchy (H1 for title, then H2, H3, etc.)
- Maximum line length: 120 characters
- Include table of contents for long documents
- Use fenced code blocks with language specified
- Use descriptive link text (no "click here")

### Architecture Decision Records (ADRs)

Format for ADRs:

```markdown
# ADR-XXX: Title

## Status

[Proposed | Accepted | Deprecated | Superseded]

## Context

What is the issue we're seeing that is motivating this decision?

## Decision

What is the change we're proposing and/or doing?

## Consequences

What becomes easier or more difficult to do because of this change?
```

### API Documentation

- Document all endpoints with examples
- Include request/response formats
- Document error responses
- Keep examples up to date with code

## Git Workflow

1. **Create feature branch:** `git checkout -b docs/description`
1. **Make changes** to documentation
1. **ALWAYS run pre-commit BEFORE committing:** `pre-commit run --all-files`
   - Fix ALL errors (especially markdown and YAML formatting)
   - Do NOT commit with `--no-verify` unless absolutely necessary
1. **Commit with conventional format:** `git commit -m "docs: description"`
1. **Push and create PR:** `gh pr create --title "docs: description"`
1. **Merge to main:** Automatic release created based on commits

**Commit Format:** Conventional Commits (enforced by pre-commit hook)

- `docs:` - Documentation changes (no version bump)
- `chore:` - Maintenance like updating pre-commit hooks

## Pre-commit Hooks

**Installed hooks:**

- YAML linting (yamllint)
- Markdown linting (markdownlint)
- Conventional commit format
- File hygiene (trailing whitespace, EOF, etc.)

**Setup:**

```bash
pre-commit install              # One-time setup
pre-commit run --all-files      # Run manually
pre-commit autoupdate           # Update hook versions
```

## Important Notes

### Code Quality Standards

**CRITICAL:** All documentation must adhere to markdown linter rules from the start.

**Markdown (markdownlint):**

Configuration: `.markdownlint.yaml` (allows 2-space indent, 120 char lines)

- Nested lists under unordered items: Use 2-space indentation
- Nested lists under ordered items: Use 2-space indentation
- Line length: 120 characters max (code/tables excluded)
- Bare URLs: Allowed in reference sections
- Bold for emphasis: Allowed in lists

**YAML (yamllint):**

- Maximum line length: 80 characters
- Use 2-space indentation
- No trailing whitespace

### Best Practices

1. **Keep docs updated** - Documentation should match current code
1. **Use examples** - Show, don't just tell
1. **Link related docs** - Help users navigate between related topics
1. **Version important changes** - Note when APIs or features change
1. **Review for clarity** - Have someone else review before merging

## References

- @README.md - Repository overview
- Markdown Guide: <https://www.markdownguide.org/>
- ADR Template: <https://github.com/joelparkerhenderson/architecture-decision-record>

---

**Last Updated:** 2025-11-30

This file should be updated whenever:

- Documentation standards change
- Important context is discovered
- Tooling is added or modified
