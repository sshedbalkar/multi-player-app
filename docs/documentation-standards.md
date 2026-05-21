# Documentation Standards

## Ownership

- One durable fact has one owner; other files link to it.
- Workspace docs own domain- and technology-agnostic rules.
- Project docs own project-specific scope, commands, paths, APIs, validators, and exceptions.
- `README.md`, `AGENTS.md`, and `AI_PERSONA.md` are routers and summaries; keep rule bodies in `docs/`.

## Markdown Economy

- All tracked Markdown is LLM-facing; token cost is a correctness concern.
- Keep only source-owned, reusable, non-deducible information.
- Prefer links to owning docs over repeated rule text.
- Remove redundancy before adding text.
- Use examples only when they change behavior, validation, routing, or decisions.
- Same-scope conflicts must be removed or narrowed with scope, reason, owner, and removal condition.

## Writing Rules

- Use plain, enforceable statements.
- Use `must` for requirements, `should` for strong guidance, and `may` for optional behavior.
- Use relative Markdown links for local docs.
- Keep external links near the section that uses them.
- Keep examples short and free of secrets, tokens, private addresses, and personal data.
- Validate links when docs move or routing changes.

## Required Durable Docs

Create or update durable docs for:

- architecture or ownership changes;
- public API or protocol contracts;
- security-sensitive design;
- deployment architecture or rollback behavior;
- data migrations or state movement;
- major dependency choices;
- incidents and operational runbooks.

## Templates

ADR:

```markdown
# ADR: <Decision>

## Status
## Context
## Decision
## Alternatives Considered
## Consequences
## Validation
## Rollout And Rollback
## References
```

API or protocol spec:

```markdown
# Spec: <Name>

## Purpose
## Version
## Authentication And Authorization
## Fields
## Errors
## Idempotency And Retry Rules
## Compatibility
## Test Cases
```

Runbook:

```markdown
# Runbook: <Operation>

## Symptoms
## Impact
## Preconditions
## Diagnosis
## Mitigation
## Rollback
## Verification
## Escalation
```

Incident:

```markdown
# Incident: <Title>

## Summary
## Impact
## Timeline
## Root Cause Or Best-Known Cause
## Mitigation
## Prevention Tasks
## Follow-Up Owners
```

Pull request:

```markdown
## Summary
## Standards
## How To Test
## Risk And Rollback
## Screenshots Or Logs
```
