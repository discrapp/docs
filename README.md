# Discr Documentation

![GitHub branch status](https://img.shields.io/github/checks-status/appdiscr/docs/main)
![GitHub Issues](https://img.shields.io/github/issues/appdiscr/docs)
![GitHub last commit](https://img.shields.io/github/last-commit/appdiscr/docs)
![GitHub repo size](https://img.shields.io/github/repo-size/appdiscr/docs)
![GitHub License](https://img.shields.io/github/license/appdiscr/docs)

## Introduction

This repository contains all documentation for the Discr project, including
architecture decisions, API documentation, user guides, and development
workflows.

### Key Features

- Project architecture and design decisions
- API documentation and reference
- Development setup guides
- User documentation
- CI/CD with GitHub Actions

## Repository Structure

```text
docs/
├── architecture/    # Architecture decision records
├── api/             # API documentation
├── guides/          # Development and user guides
├── .github/         # GitHub Actions workflows
└── README.md
```

## Contributing

Upon first clone, install the pre-commit hooks:

```bash
pre-commit install
```

To run pre-commit hooks locally:

```bash
pre-commit run --all-files
```

This project uses conventional commits for version management.
Please ensure your commits follow the format:

```text
type(scope): description

docs: add API endpoint documentation
docs: update setup guide
chore: update pre-commit hooks
```

### Documentation Standards

- Use Markdown for all documentation
- Follow the project's markdown linting rules
- Keep line length to 120 characters max
- Use proper heading hierarchy (start with H2, not H1 after title)

## License

See LICENSE file for details.
