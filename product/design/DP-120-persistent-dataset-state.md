---
doc_id: DP-120
title: Persistent Dataset State
depends_on:
  - DP-100
---

# Persistent Dataset State

## Purpose

The dataset provides persistent application and session state that remains available beyond a single reasoning session.

Its role is to preserve information needed for later initialization, continuation, and coherent progress without depending on conversational memory alone.

## Persistent State

Dataset state represents relevant information about the application, its ongoing work, or its prior reasoning activity that must survive a reasoning-session boundary.

Persistence is a semantic property here: information remains available for later use.

ADR does not equate persistence with any particular database, file format, storage service, serialization, or transaction model.

## Dataset and Ruleset Boundary

Dataset state is distinct from ruleset context.

The dataset records state about the application or work.

The ruleset establishes the governed context used to interpret and reason about that state.

The distinction follows semantic role rather than physical representation. A value does not become ruleset material merely because it changes rarely, and it does not become dataset state merely because it is stored in a database.

When the role is ambiguous and materially affects behavior, further Design is required.

## State Across Sessions

A later reasoning session may need only a relevant portion of persisted state rather than the entire dataset.

ADR therefore does not require complete-state loading.

A derived application may select, retrieve, project, summarize, or otherwise construct the state made available to reasoning, provided the result preserves the state meaning required for the intended continuation.

## State Evolution

Persistent state is expected to evolve as application work progresses.

The exact semantics for:

- identity,
- versioning,
- mutation,
- validation,
- retention,
- provenance,
- conflict detection,
- stale-state handling,
- recovery,

are not established by this Design.

These are not assumed to be implementation-only concerns. Where they materially change the meaning of continuity or state, they require further Design before Planning fixes concrete behavior.

## Independence from Storage Technology

ADR does not prescribe:

- relational or document databases,
- files,
- object stores,
- vector stores,
- event logs,
- memory services,
- synchronization systems,
- transaction mechanisms.

Different derived applications may realize persistent state differently while conforming to the same semantic role.

## Cross-Cutting Perspective

SCF is the perspective most directly associated with persistent state and its use across reasoning sessions.

SCF remains cross-cutting and does not independently define a product domain at this level.

## Design Questions

Further Design may need to resolve:

- state identity and lifecycle,
- the ruleset/dataset information boundary,
- how state validity is determined,
- how stale or conflicting state affects reasoning,
- what state must be carried forward,
- when a bounded projection is sufficient,
- whether SCF eventually contains independently meaningful concepts that justify further decomposition.

## Planning Boundary

Planning may define concrete state requirements only where Design provides sufficient intended meaning.

Storage and mutation mechanisms should not be used to invent missing state semantics.
