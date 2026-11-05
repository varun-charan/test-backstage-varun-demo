# Repository Conventions

## Purpose

This document defines standard practices for application repositories created through the **Create an Application Repository** Backstage template. Following these conventions ensures consistency, maintainability, and collaboration across teams.

## What Gets Provisioned Automatically

| Feature | Detail |
|---|---|
| Skeleton files | `pyproject.toml`, `.python-version`, `.pre-commit-config.yaml`, `src/`, `tests/`, `.gitignore`, `CODEOWNERS`, `CONVENTIONS.md`, PR template |
| GitHub workflows | CI (lint, mypy, pytest), stale issues/PRs, release notes, labeler |
| Repository topics | `managed-with-backstage`, `repo-owner-<owner>`, `<department>`, `<app-name>` |
| Branch protection | `main` branch — enforce admins, 1 approval, dismiss stale reviews, require conversation resolution, code owner reviews |
| Auto-delete head branches | Enabled |
| Repository variables | `AZURE_CLIENT_ID`, `AZURE_SUBSCRIPTION_ID`, `AZURE_TENANT_ID` (placeholders) |

## Branch Naming

All branches (except `main`) must follow:

```
<type><-|/><TICKET-ID>[-description]
```

- **type**: `feat`, `enh`, `bug`, or `chore`
- **separator**: `-` or `/`
- **ticket ID**: Jira-style uppercase ID (e.g., `ABC-123`)
- **description** (optional): lowercase alphanumeric slug

**Examples**: `feat-BIZ-123-add-auth`, `bug/OPS-456`, `chore/DEV-012-update-deps`

## Commit Messages

- Use conventional commits: `feat:`, `fix:`, `chore:`, `docs:`, etc.
- Reference ticket IDs: `feat(BIZ-123): add login endpoint`
- Use imperative mood ("add", "fix" — not "added", "fixes")

## Pull Request Process

- Use the included PR template
- Require at least one approval before merge
- Resolve all review conversations before merging
- PR titles should follow: `[TICKET-ID] Brief description`

## Code Style

- **Ruff**: Linting and formatting — run `ruff check .` and `ruff format .`
- **Mypy**: Type checking — run `mypy src/`
- Pre-commit hooks enforce these on commit (see README for setup)

## Testing

- All new features require tests
- Run `pytest` for the test suite
- Coverage is reported via `pytest --cov=src`
- Remove `tests/test_placeholder.py` once you add real tests

