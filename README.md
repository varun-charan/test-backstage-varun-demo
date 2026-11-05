# test-backstage-varun-demo

> **This repository was provisioned by [Backstage](https://backstage.io) using the *Create an Application Repository* template.**
> Update this README with project-specific details before your first PR.

## Overview

<!-- Briefly describe what this project does and why it exists. -->

## Prerequisites

- **Python** >= 3.13
- **pip** or **uv** for package management

- Access to Azure subscription (for CI variables)

## Getting Started

```bash
# Clone the repo
git clone https://github.com/jerzybobrowski/test-backstage-varun-demo.git
cd test-backstage-varun-demo

# Create virtual environment
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -e ".[dev]"
```

## Project Structure

```
test-backstage-varun-demo/
├── .github/
│   ├── CODEOWNERS              # Auto-assigns reviewers
│   ├── labeler.yml             # PR labels based on branch
│   ├── pull_request_template.md
│   ├── release.yaml            # Auto-generated release notes
│   └── workflows/
│       ├── ci.yaml             # Lint, mypy, pytest
│       └── stale.yaml          # Marks stale issues/PRs
├── .gitignore
├── .pre-commit-config.yaml     # Lint hooks
├── .python-version             # Python version for pyenv/CI
├── CONVENTIONS.md              # Branching, PR, repo standards
├── pyproject.toml              # Project config
├── README.md
├── src/
│   └── __init__.py
├── tests/
│   ├── __init__.py
│   └── test_placeholder.py
└── ...
```

## What's Pre-Configured

| Setting | Value |
|---|---|
| Default branch | `main` (protected) |
| Required approvals | 1 |
| Dismiss stale reviews | Yes |
| Require code owner review | Yes |
| Require conversation resolution | Yes |
| Auto-delete head branches | Yes |
| Repository topics | `managed-with-backstage`, owner, department, app name |
| CI variables | `AZURE_CLIENT_ID`, `AZURE_SUBSCRIPTION_ID`, `AZURE_TENANT_ID` (placeholders) |
| Linting | Ruff |
| Formatting | Ruff |
| Type checking | Mypy |
| Testing | Pytest + coverage |


See [CONVENTIONS.md](CONVENTIONS.md) for full details.

## Development

```bash
# Run tests
pytest

# Lint
ruff check .
ruff format .

# Type check
mypy src/
```

## Pre-commit Hooks

Install hooks to enforce linting and formatting on commit:

```bash
pre-commit install
pre-commit run --all-files  # Run once on existing files
```

## Contributing

1. Create a branch: `<type><-|/><TICKET-ID>[-description]` (e.g., `feat-BIZ-123-add-auth`)
2. Make your changes and run tests locally
3. Open a pull request using the included template
4. Get at least one approval from a code owner
5. Merge after all conversations are resolved

