---
doc_id: DP-140
title: Cross-Session Continuity
depends_on:
  - DP-100
  - DP-110
  - DP-120
  - DP-130
---

# Cross-Session Continuity

## Purpose

Cross-session continuity is ADR's end-to-end product outcome.

A later reasoning session can regain enough governed application context and relevant persistent state to continue prior application work coherently.

## Continuity Model

Continuity depends on the relationship established by the preceding Design:

1. the ruleset establishes governed application context,
2. the dataset preserves relevant persistent state,
3. initialization composes context and state for reasoning,
4. a later reasoning session resumes work using that composition.

Continuity therefore spans session boundaries without treating the prior conversation itself as the sole source of memory.

## Coherent Resumption

A resumed session should operate within the intended application context and possess enough relevant prior state to continue the work rather than unknowingly restart, contradict, or reinterpret it.

"Enough" is intentionally semantic rather than volumetric.

Continuity does not require reproducing every token, every prior inference, or every persisted value. It requires sufficient context and state to preserve the meaning necessary for the intended continuation.

## Session Boundaries

ADR recognizes a reasoning-session boundary as a point across which continuity cannot rely solely on transient model context.

The exact identity and mechanics of a session boundary are not defined here.

A derived application may treat process restarts, model invocations, conversation resets, agent replacements, time-separated work, or other events as session boundaries when that distinction is meaningful to the application.

## Failure and Degradation

Continuity can be threatened by:

- missing state,
- stale state,
- invalid state,
- conflicting state,
- missing governed context,
- stale governed context,
- incompatible context and state,
- insufficient reconstruction for the intended task.

These conditions are product-significant, but this Design does not yet assign exact success, failure, recovery, or degraded-operation behavior.

Further Design is required before Planning defines those semantics.

## Drift and Hallucination

Reduced drift and hallucination are motivations for continuity and context governance.

ADR's approach is to make relevant context and state explicit and reconstructable across sessions rather than expecting the reasoning engine to infer or remember them implicitly.

This Design does not claim that the architecture eliminates hallucination, nor does it define a quantitative threshold for acceptable drift.

Conformance evidence and measurable criteria require further Design and Planning.

## SCF and CGI

SCF and CGI provide complementary views of this outcome.

SCF emphasizes state flow, restoration, and continuity across session boundaries.

CGI emphasizes the governed context within which restored state is interpreted and reasoning proceeds.

The continuity outcome depends on both perspectives without requiring either to become a separate runtime subsystem or independent product domain.

## Derived-Application Independence

A derived application can provide cross-session continuity without depending on ADR at runtime.

ADR defines the product semantics to preserve; the application owns the concrete mechanisms that persist state, reconstruct context, initialize reasoning, and recover from session boundaries.

## Design Questions

Further Design may need to resolve:

- the minimum conditions for successful continuity,
- observable success and failure semantics,
- stale, invalid, missing, and conflicting input behavior,
- recovery and fallback semantics,
- session identity where product meaning depends on it,
- what continuity evidence is needed for conformance,
- how drift reduction can be evaluated without overstating model guarantees.

## Planning Boundary

Planning may define bounded Functional Sets and normative requirements for continuity once the relevant Design is sufficiently reviewed.

Planning should not resolve missing continuity semantics by choosing an implementation and treating its behavior as intended product meaning.
