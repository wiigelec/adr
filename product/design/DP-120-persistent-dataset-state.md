---
doc_id: DP-120
title: Dataset Architecture
depends_on:
  - DP-100
---

# Dataset Architecture

## Purpose

The Dataset is the persistent state machine of an ADR-derived application and the sole authority for committed application state.

It represents the durable current state from which an Agent can understand ongoing application work and to which accepted governed state transitions can be persisted.

ADR defines the Dataset role and continuity contract. Each ADR-derived application defines its concrete state semantics.

## Current Application State

The Dataset represents application state that must remain meaningful beyond a single Agent reasoning session.

Current state may describe any application-specific facts necessary to continue the work, such as:

- current objects and their relationships,
- progress,
- decisions,
- statuses,
- accumulated results,
- unresolved work,
- application-specific control state.

These examples are illustrative rather than mandatory.

What constitutes state is determined by the derived application's semantics.

## Committed-State Authority

Committed application state has one authoritative home: the Dataset.

Agent working memory, model memory, chat history, intermediate reasoning, and other transient session state may inform reasoning but do not become authoritative application state merely by existing.

Only state accepted through the derived application's governed transition semantics becomes current committed Dataset state.

This boundary allows a later session to distinguish durable application truth from transient reasoning artifacts.

## Persistent State Machine

The Dataset is a state machine in the semantic sense.

At any relevant point, the application has a current Dataset state.

A governed interaction may produce a proposed transition from that state to a next state.

When that transition is accepted according to the derived application's semantics, the resulting state becomes the next durable authoritative Dataset state and is available to later reasoning sessions.

ADR does not require a particular formal state-machine notation, transition engine, database, event model, or serialization.

## State Transition

A proposed Dataset transition may be influenced by:

- current Dataset state,
- applicable Ruleset semantics,
- user input,
- Agent reasoning.

The Dataset does not independently determine whether a proposed transition is valid.

The Ruleset governs application interpretation and transition validity.

The Agent participates in reasoning that may determine or propose the next state.

The derived application defines the exact transition and acceptance semantics.

## Dataset and Ruleset Boundary

Dataset and Ruleset remain semantically distinct.

The Dataset answers, in application-specific terms, **what is the current committed state?**

The Ruleset answers, in application-specific terms, **how is that state interpreted and under what semantics may it change?**

The distinction follows meaning rather than storage mechanism, update frequency, or file type.

## SCF — Session Continuity Framework

**SCF — Session Continuity Framework** is the realization framework aligned with the Dataset concept.

SCF concerns persistent state, state continuity, and preserving meaningful Dataset authority across Agent sessions.

SCF is not itself the concrete Dataset semantics of every ADR-derived application.

A derived application uses or specializes SCF to realize the continuity behavior required by its own state model.

## SCF Contract Foundation

**SCF Contract Foundation** is the reusable Dataset-side foundational contract set underlying SCF realizations.

Its role is to define generic Dataset-side continuity and authority contracts without containing a derived application's concrete state vocabulary or application data.

A completed ADR-derived application may realize those contracts without requiring SCF Contract Foundation as a runtime dependency.

SCF Contract Foundation and SCF are therefore related but not interchangeable: the Contract Foundation supplies reusable foundational contracts, while SCF is the broader Dataset-side realization framework.

## Reading State

An Agent may read relevant current Dataset state when reasoning.

ADR does not require every reasoning operation to consume the complete Dataset.

A derived application may expose a relevant projection or representation of current state when that representation preserves the semantics necessary for the operation.

The Dataset remains the durable application-state authority even when only a bounded representation is supplied to the Agent.

## Modifying State

Agent reasoning may produce a proposed modification of Dataset state.

The proposed modification is interpreted and validated under the applicable Ruleset and may incorporate user input.

The fact that the Agent generated an output does not by itself make that output persistent application state.

The derived application's transition semantics determine whether a proposed change is accepted.

Only an accepted transition changes authoritative Dataset state.

## State Evolution

Derived-application Design may define semantics for:

- state identity,
- state validity,
- transition validity,
- transition acceptance,
- versioning,
- conflict handling,
- stale state,
- recovery,
- provenance,
- retention,
- partial or bounded state views.

ADR does not impose one universal model for those concerns.

## Derived-Application Responsibility

Each ADR-derived application defines its Dataset semantics and state-transition model.

ADR supplies the architectural role and continuity contract.

SCF Contract Foundation supplies reusable Dataset-side foundational contracts.

SCF supplies the broader Dataset-side realization framework.

The derived application supplies the actual application state model.
