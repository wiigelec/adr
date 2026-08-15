# Governed agent initialization and continuity

## Capability boundary

This candidate defines one capability-oriented directional unit spanning the three named ADR components:

- ruleset-defined agent context,
- dataset-defined persistent state,
- initialization of the AI reasoning engine from both context and state,
- preservation of continuity across sessions.

The boundary is intentionally end-to-end rather than a technical-layer slice. It expresses what ADR should govern directionally without deciding how a derived application implements the capability.

## Included intent

The candidate carries forward the accepted analysis direction that ADR should provide scaffolding for an AI-driven application whose reasoning is initialized from explicit application context and persisted state. The resulting continuity should reduce uncontrolled drift between sessions while keeping the ruleset, dataset, and reasoning engine meaningfully related.

The candidate also preserves the directional expectation that derived applications can implement ADR-derived specifications independently rather than depending on ADR as a runtime component.

## Exclusions

This candidate does not define:

- exact ruleset structure or encoding,
- exact dataset schema, storage model, ownership, mutation, or lifecycle,
- prompting strategy or context-window construction,
- APIs or runtime interfaces,
- agent implementation architecture,
- conformance measurements,
- release-readiness criteria,
- product decomposition,
- normative product specifications,
- implementation planning,
- implementation issues,
- runtime code or tests.

It also does not decide whether SCF or CGI become independently governed specification domains.

## Dependencies

The boundary depends directionally on:

- a usable ruleset representation supplying bounded application context,
- persistent dataset semantics sufficient to carry relevant state between sessions,
- availability of both context and state when initializing or continuing reasoning,
- later normative work to resolve exact responsibilities, interfaces, validation, and conformance.

Those exact semantics remain unresolved and are not invented by this candidate.

## Integration foundation

The integration concern is the relationship among agent, dataset, and ruleset rather than any particular transport or runtime mechanism. The reasoning engine is directionally initialized or informed by both governed context and persisted state so that a new session can continue prior application work within the intended application context.

This candidate does not require the agent to consume complete source artifacts directly. Bounded projections, context construction, retrieval, or other mechanisms remain later design and specification questions.

## End-to-end usability

The candidate is coherent only if the combined boundary can support a useful derived-application flow at directional level:

1. application context is established by the ruleset,
2. relevant persistent state is established by the dataset,
3. both are available to initialize or continue AI reasoning,
4. subsequent sessions can regain enough governed context and state to preserve continuity.

This expresses the minimum end-to-end value identified by the accepted analysis without specifying implementation details.

## Analyzed alternatives

The accepted analysis identified two narrower alternatives that remain traceable and are not rejected by user approval:

### Candidate B — Context governance foundation

A narrower core centered on ruleset-defined bounded context and drift control, with CGI as the primary analytical lens. This leaves dataset/session continuity outside the first functional boundary.

### Candidate C — Session continuity foundation

A narrower core centered on persistent session state and continuity, with SCF as the primary analytical lens. This does not by itself cover how ruleset context constrains reasoning.

Candidate A is represented here because the accepted analysis favors it as the strongest end-to-end expression of the user-supplied three-component model. That analytical preference is not user approval.

## Decomposition handoff

Decomposition handoff is **ready** because this exact functional-set boundary has explicit user approval and lifecycle status `approved`.

Successor governed product decomposition may now consume this approved boundary. This approval does not itself authorize decomposition artifacts outside a separately governed successor issue, and any material boundary change requires returning to candidate revision.
