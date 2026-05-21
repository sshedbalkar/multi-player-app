# Workspace Workflow

## Retrieval

- For workspace-scoped work, read workspace docs first, then the narrowest project route.
- Truth order: source truth > validated context > local scratch > chat history.
- Choose the narrowest project route before reading large doc sets.
- `context/` files are retrieval aids, not rule owners.

## Rule Changes

- Add or update shared rules only in workspace `docs/`.
- After any workspace rule change, rescan the workspace for affected `README.md`, `AGENTS.md`, `AI_PERSONA.md`, `context/`, standards, validators, scripts, and project docs.
- Update affected project docs in the same change so they either point to the workspace owner or state a narrow specialization.
- Do not duplicate full rule bodies into routers or context indexes.

## Context Sync

- Edit source truth first.
- Refresh context only when reusable routing, validation commands, source paths, durable docs, or open work changed.
- Keep top-level selectors thin; put reusable detail in semantic shards.
- Preserve declared ordering and fixed field order.
- Backfill context after a cache miss only when the discovered fact is reusable.

## Validation

- Run the cheapest relevant static docs/context checks after doc-only changes.
- Run project tests when code, build, validation, or deployment behavior changes.
- Report validation evidence at closeout.
- If validation cannot run, report the exact blocker and keep affected claims unverified.

## Closeout

- Summarize changed source truth and affected routing docs.
- Include commands run and results.
- Name any unverified risk or skipped validator.
