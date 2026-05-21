# Naming Strategy

## Core Rule

Choose names that narrow from broad context to specific meaning:

1. boundary or domain;
2. concept;
3. role, state, or action.

Path and package context count. Do not repeat context already made obvious by the containing directory, module, or type.

## Local Glossary

- Each project owns its local glossary.
- Use one term for one concept.
- Introduce synonyms only when they represent distinct concepts.
- Keep stable exported names, config keys, metrics, artifact fields, API fields, and persisted names version-safe.

## Variables And Functions

- Prefer business, boundary, or operational meaning over raw type.
- Function names should start with the action when the language style allows it.
- Boolean names should read as predicates or states.
- Output names should describe the returned artifact, not only direction.
- Tight loop counters and short-lived algorithm locals may stay compact when local context is enough.

## Collections And Maps

- Collection names should describe entries, not container type.
- Map names should identify the key when ambiguity is likely.
- Avoid generic standalone names when local context does not narrow them enough.

## External Names

- Metrics should use `<domain>.<component>.<measurement>` or the project-local equivalent.
- Metric labels must stay low-cardinality and must not include raw user, tenant, or secret values.
- Database or persisted object names should use the project-local storage convention and stay stable after release.

## Anti-Patterns

- Type-only names such as `data`, `info`, `helper`, `manager`, `list`, `map`, and `value`.
- Hidden abbreviations.
- Reusing a generic name across unrelated domains.
- Encoding temporary implementation details into durable names.
- Overlong names that repeat surrounding context.
