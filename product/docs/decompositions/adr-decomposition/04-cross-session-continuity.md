# ADR-PA-CONT — Cross-session continuity

## Product area

**Stable identifier:** `ADR-PA-CONT`

This area owns the complete directional product outcome: a later reasoning session can regain enough governed context and relevant persisted state to continue prior application work coherently.

## Responsibility boundary

- coordinate the decomposed responsibilities into end-to-end continuity,
- preserve resumption within intended application context,
- tie continuity to governed context and persisted state rather than conversational memory alone,
- maintain derived-application independence from ADR runtime.

## Dependencies

Depends on `ADR-PA-INIT` and transitively on `ADR-PA-CTX` and `ADR-PA-STATE`.

## Exclusions

No exact session identifiers, checkpoints, recovery algorithms, storage protocols, reconstruction mechanics, success thresholds, observability requirements, or release criteria.

## Cross-cutting concerns

SCF is most directly relevant to continuity/state flow; CGI to context/agent governance. Both remain cross-cutting perspectives rather than separately accepted product areas.

Drift/hallucination reduction remains motivation; measurements and thresholds are future normative work.

## Unresolved decisions

- minimum state/context sufficient for continuity,
- observable success/failure behavior,
- stale/missing/conflicting/invalid state handling,
- session-boundary semantics,
- drift/hallucination conformance evidence,
- recovery/fallback semantics.

## Expected downstream specification families

### Level 3 — Cross-session continuity outcome

Define the complete product outcome coordinating initialization, governed context, and persisted state, including observable success/failure behavior once normatively established. Do not redefine primitive context/state semantics.

## Document-wide stopping criteria

Stop before exact semantics or architecture are selected. The four areas are sufficient when they cover the approved functional-set boundary, expose dependencies and unresolved decisions, and support an acyclic Level 0–3 specification graph.

## Planning handoff

After acceptance, successor governed work should establish normative product specifications beginning with shared Level 0 semantics and the two Level 1 concepts before accepting dependent Level 2/3 specifications.

No product specification or implementation plan is authorized by Issue #9 itself.
