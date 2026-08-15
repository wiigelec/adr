# ADR-PA-INIT — Agent initialization

## Product area

**Stable identifier:** `ADR-PA-INIT`

This area owns the directional responsibility for initializing or continuing AI reasoning from both governed application context and relevant persistent state.

## Responsibility boundary

- coordinate `ADR-PA-CTX` and `ADR-PA-STATE`,
- require both governed context and relevant state to be available to reasoning,
- form one coherent reusable initialization responsibility,
- remain independent of provider, prompting, retrieval, and runtime architecture.

## Dependencies

Depends directionally on `ADR-PA-CTX` and `ADR-PA-STATE`.

## Exclusions

No exact prompting, context assembly, model APIs, retrieval algorithms, token budgeting, invocation protocols, error handling, or runtime orchestration.

## Cross-area relationships

`ADR-PA-CONT` consumes this capability to support continuity across sessions.

## Unresolved decisions

- sufficient initialization criteria,
- complete artifacts versus projections,
- stale/conflicting context-state handling,
- validation and failure semantics,
- initialization versus continuation semantics.

## Expected downstream specification families

### Level 2 — Agent initialization capability

Define the reusable capability composing Level 1 governed-context and persistent-state concepts into one coherent initialization responsibility; do not define the complete cross-session outcome.

No separate Level 1 "agent" family is required unless later analysis identifies an independently meaningful elementary ADR contract beyond context/state.

## Stopping boundary

Further detail belongs in normative product specifications; invocation and implementation mechanics remain undecided.
