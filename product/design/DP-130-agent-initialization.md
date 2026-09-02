---
doc_id: DP-130
title: Agent Initialization
depends_on:
  - DP-100
  - DP-110
  - DP-120
---

# Agent Initialization

## Purpose

Agent initialization establishes the relationship by which AI reasoning begins or resumes using both governed application context and relevant persistent state.

Initialization is the first explicit composition point among ADR's three primary concepts.

## Initialization Inputs

Reasoning depends on two semantically distinct inputs:

- governed context from the ruleset,
- relevant persistent state from the dataset.

Both contribute to a coherent reasoning environment.

Context without state may preserve application meaning while losing continuity of work.

State without governed context may preserve facts while losing the intended interpretation and boundaries under which they should be reasoned about.

ADR therefore treats their composition as a product concern.

## Initialization and Continuation

Initialization includes both starting a new reasoning session and restoring enough context and state for a later session to continue prior work.

ADR does not yet require these to be implemented as identical operations.

Further Design may distinguish initial start, resumption, recovery, refresh, or other modes if those distinctions materially affect product meaning.

## Bounded Inputs

The agent does not necessarily consume the complete ruleset or complete dataset.

A derived application may provide bounded projections selected for the current reasoning task.

The bounded form must remain sufficient to preserve the intended governed context and relevant state.

The criteria for sufficiency are not yet fully defined and remain a Design concern.

## Consistency

Initialization may encounter context and state that are stale, incomplete, invalid, or mutually inconsistent.

ADR recognizes these as consequential semantic conditions.

This Design does not define automatic precedence, repair, rejection, degradation, or fallback behavior. Those outcomes require further Design rather than being inferred from implementation convenience.

## Runtime Independence

ADR does not prescribe how initialization is performed.

Possible realizations may use prompting, retrieval, context assembly, tool calls, agent frameworks, generated instructions, provider-specific mechanisms, or other techniques.

No particular mechanism defines ADR meaning.

## Relationship to Continuity

Agent initialization supplies the immediate reasoning state consumed by cross-session continuity.

DP-140 depends on initialization being able to reconstruct enough governed context and relevant persistent state for coherent continuation.

Initialization itself does not define whether continuity succeeded over time; it defines the composition needed to make that outcome possible.

## Design Questions

Further Design may need to resolve:

- minimum sufficient initialization content,
- whether initialization and continuation have distinct semantics,
- required behavior for missing context or state,
- required behavior for stale or conflicting inputs,
- how initialization validity is observed,
- whether the agent may proceed in a degraded mode,
- what guarantees are required before reasoning begins.

## Planning Boundary

Planning may select concrete initialization behavior only from sufficiently developed Design.

Provider APIs, prompt construction, retrieval algorithms, token budgeting, and orchestration remain implementation concerns unless Design later assigns them product-level meaning.
