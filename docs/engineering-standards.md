# Engineering Standards

## Decision Priority

1. Correctness, security, and data safety.
2. Maintainability, clear ownership, and replaceable modules.
3. User or operator experience, runtime performance, and cost.
4. Recoverability, observability, and graceful degradation.
5. Portability and deployability.
6. Delivery speed.

## Common Engineering

- Keep modules single-purpose, bounded, and easy to replace.
- Prefer reusable foundations before feature-specific cases.
- Define durable constants, defaults, config keys, environment variable names, route or protocol markers, status names, error codes, reusable limits, and date formats in an owned central location before implementation, tests, scripts, or bindings consume them.
- Automate repeated, manual, or error-prone work.
- Make long-lived decisions explicit in durable docs.
- Treat external input, runtime config, imports, and recovered state as untrusted until validated.
- Use UTC for persisted, exported, cross-system, and audit-facing time values unless a project documents a narrow exception.

## Boundaries And Errors

- Every component must have a clear boundary, owner, and replacement path.
- Validate at boundaries and return structured, typed errors.
- Do not branch on human-readable error text.
- Retry only idempotent or explicitly deduplicated operations.
- Log unexpected failures with safe correlation metadata.

## Configuration And Secrets

- Configuration must be explicit, layered, environment-specific, and reviewable.
- Safe local defaults may exist only when they cannot expose secrets or corrupt shared state.
- Runtime config should be inspectable through redacted diagnostics.
- Secrets must never be committed or printed.
- Secret refs must be provider-neutral and explicit, such as `env:<name>` or `file:<absolute_path>`.
- Development may use environment injection; shared or production-like environments should prefer mounted read-only secret files.
- Feature flags need an owner, rollout plan, expiry condition, and cleanup task.

## Security And Operations

- Use least privilege for identities, filesystem access, network access, and deployment credentials.
- Separate authentication from authorization.
- Redact tokens, credentials, personal data, and raw private content from logs, metrics, traces, reports, and diagnostics.
- Production features must be observable and operable through useful logs, metrics, health checks, alerts, and runbooks.
- Alerts must be actionable and link to mitigation or diagnosis steps.

## Build Release And Deployment

- Builds must be reproducible from checked-in source, config, and dependency manifests.
- Build, deploy, validation, and utility scripts must live in the repo.
- Scripts must keep top-level comments with a short purpose statement and `Usage examples:`.
- Scripts must print a `Usage:` block and exit successfully for `--help` before doing work.
- Script fallback defaults must live in a central config file, not executable script literals.
- Artifacts must include source commit, build time, version, target, dependency summary where available, and checksum.
- Promote the same artifact between environments; change only config, secrets, limits, and external bindings.
- Every release needs validation evidence and rollback or forward-fix notes.

## Testing And Validation

- Significant behavior should cover happy, sad, edge, hot, and recovery paths.
- Prefer many deterministic unit tests, fewer integration tests, and targeted end-to-end or load tests.
- Hot paths need benchmarks or profiling when performance claims are made.
- Native or memory-sensitive code needs sanitizer, leak, or equivalent memory evidence where available.
- Repo-local temporary, scratch, cache, report, and generated local-only files belong under the project `.tmp/` tree.
- Closeout requires validation evidence or an explicit blocker.

## Folder Structure

- Keep committed config in `configs/`.
- Keep durable docs in `docs/`.
- Keep retrieval metadata in `context/`.
- Keep automation in `scripts/`.
- Keep contracts in `api/` or a project-owned equivalent.
- Keep local scratch under `.tmp/`.
- Nested subprojects own local `configs/`, `docs/`, `context/`, `scripts/`, and validators when they are independently buildable or reusable.

## Dependencies

- Prefer standard libraries and small, conservative dependencies.
- Add a dependency only when the reliability, stability, performance, cost, or delivery benefit justifies ownership.
- Document major dependency choices with reason, alternatives, license, maintenance, security posture, owner, and removal plan.
- Keep dependency direction explicit; depend on stable interfaces across boundaries.
- Avoid cycles, hidden global state, broad utility packages, and convenience dependencies for trivial helpers.
