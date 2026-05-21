# AGENTS.md

workspace_state: multi_project
workspace_foundation_file: README.md

## Bootstrap

- Read order for workspace-scoped prompts: `AGENTS.md` -> `README.md` -> `AI_PERSONA.md` -> `docs/README.md` -> `docs/workflow.md` -> relevant `docs/*.md` -> target project `AGENTS.md` -> project `README.md` -> project `AI_PERSONA.md` -> project `context/` -> target docs/files.
- Pick the narrowest project route after the workspace layer is understood.
- Source truth: workspace `docs/`, project durable docs, then validated `context/`.

## Hard Rules

- Workspace `docs/` own domain- and technology-agnostic rules.
- Project docs may specialize workspace rules for local scope; conflicts require narrow scope, reason, owner, and removal condition.
- `README.md`, `AGENTS.md`, `AI_PERSONA.md`, and `context/` are token-optimized routers; do not copy full rule bodies into them.
- Any workspace rule addition or update requires a workspace rescan and affected project docs/context updates in the same change.
- Source truth beats context; context beats scratch; scratch beats chat history.
- Commit-message work reads `docs/commit-messages.md` before project-local commit docs.
- Closeout requires validation evidence or an explicit blocker.

## Project Entrypoints

- `multi-player-app-ai/AGENTS.md`
- `mp-cache/AGENTS.md`
- `multi-player-app-ai/native/mp_logger/AGENTS.md`
- `mp-cache/native/mp_logger/AGENTS.md` when working through the cache-owned logger copy.
