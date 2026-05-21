# Workspace Docs

Workspace docs are the first stop for any prompt whose scope is inside this workspace. Read these before project-local docs; project docs specialize this baseline only for a narrow local scope.

## Source Order

1. `AGENTS.md`
2. `README.md`
3. `AI_PERSONA.md`
4. this file
5. `docs/workflow.md`
6. relevant workspace standard below
7. project `AGENTS.md`, `README.md`, `AI_PERSONA.md`, `context/`, and local docs

## Standards

- `engineering-standards.md`: common engineering, security, configuration, dependency, testing, release, and operations rules.
- `workflow.md`: retrieval order, rule-change workflow, context sync, validation, and closeout rules.
- `documentation-standards.md`: Markdown economy, ownership, links, technical-doc templates, and review rules.
- `naming-strategy.md`: domain-neutral naming strategy.
- `commit-messages.md`: workspace commit-message baseline.

## Specialization Rule

Project docs may add stricter or more specific rules. Same-scope conflicts are not allowed unless the project doc states the narrow scope, reason, owner, and removal condition.
