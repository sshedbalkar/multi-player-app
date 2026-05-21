# Commit Message Standard

Every commit must use both a subject and a body. One-line commits are not allowed unless a project explicitly documents a narrower emergency workflow.

## Required Format

```text
<type>(<scope>): <short summary>

<body explaining why the change exists>

<footer>
```

The body is required, concise, and focused on why rather than a file-by-file summary.

## Allowed Types

- `feat`
- `fix`
- `refactor`
- `test`
- `docs`
- `build`
- `perf`
- `security`
- `db`
- `ops`
- `style`
- `ci`
- `chore`
- `revert`
- `hotfix`
- `infra`

## Allowed Footers

- `Fixes <ID>`
- `Closes <ID>`
- `Refs <ID>`
- `BREAKING CHANGE:`
- `Co-authored-by`
- `Reviewed-by`

## Discoverability

When work touches Git workflow, commits, PR preparation, or release history:

1. read this file;
2. read the project-local commit standard, if present;
3. follow the stricter body, scope, validation, and hook rules.
