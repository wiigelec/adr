# ADR-PA-CTX — Ruleset context governance

## Product area

**Stable identifier:** `ADR-PA-CTX`

This area owns the directional responsibility for ruleset-defined application context that bounds reasoning.

## Responsibility boundary

- establish bounded application context as an ADR-governed concern,
- distinguish governed context from unconstrained inference,
- supply context needed by later agent initialization,
- preserve derived-application independence from an ADR runtime.

## Dependencies

Foundational within the decomposition. Future normative specifications may depend on shared Level 0 ADR semantics.

## Exclusions

No exact ruleset syntax, serialization, prompt construction, retrieval, context-window mechanics, policy language, or runtime loading behavior.

## Cross-area relationships

`ADR-PA-INIT` consumes this responsibility with `ADR-PA-STATE`; `ADR-PA-CONT` depends on it transitively.

## Unresolved decisions

- ruleset/dataset information boundary,
- representation and validation of ruleset authority,
- complete ruleset versus bounded projections,
- exact context-compliance semantics,
- whether CGI becomes an independent normative concern.

## Expected downstream specification families

### Level 0 — ADR shared semantics

Only shared authority, identity, lifecycle, and interpretation semantics needed across areas; no feature-specific ruleset behavior.

### Level 1 — Ruleset context concept

Define the independently meaningful concept of governed application context and its elementary contract without coordinating dataset state or complete outcomes.

## Stopping boundary

Further detail belongs in normative product specifications; no encoding or operational behavior is selected here.
