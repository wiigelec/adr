---
doc_id: DP-120
title: Dataset Architecture
depends_on:
  - DP-100
---

# Dataset Architecture

## Purpose

The Dataset is the persistent state machine of an ADR-derived application.

It represents the durable current state from which an Agent can understand ongoing application work and to which governed state transitions can be persisted.

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

## Persistent State Machine

The Dataset is a state machine in the semantic sense.

At any relevant point, the application has a current Dataset state.

A governed interaction may produce a transition from that state to a next state.

The next state becomes durable application state and is available to later reasoning sessions.

ADR does not require a particular formal state-machine notation, transition engine, database, event model, or serialization.

## State Transition

A Dataset transition may be influenced by:

- current Dataset state,
- applicable Ruleset semantics,
- user input,
- Agent reasoning.

The Dataset does not independently determine whether a transition is valid.

The Ruleset governs application interpretation and transition validity.

The Agent participates in reasoning that may determine or propose the next state.

The derived application defines the exact state-transition semantics.

## Dataset and Ruleset Boundary

Dataset and Ruleset remain semantically distinct.

The Dataset answers, in application-specific terms, **what is the current durable state?**

The Ruleset answers, in application-specific terms, **how is that state interpreted and under what semantics may it change?**

The distinction follows meaning rather than storage mechanism, update frequency, or file type.

## SCF — Session Continuity Framework

**SCF — Session Continuity Framework / SCF Contract Foundations** is the realization framework aligned with the Dataset concept.

SCF provides reusable foundations for persistent state, state continuity, and the contracts required to carry meaningful application state across Agent sessions.

SCF is not itself the concrete Dataset semantics of every ADR-derived application.

A derived application uses or specializes SCF to define what its state means, what must persist, and how that state participates in continuity.

SCF may be specified independently of a particular persistence technology.

## Reading State

An Agent may read relevant current Dataset state when reasoning.

ADR does not require every reasoning operation to consume the complete Dataset.

A derived application may expose a relevant projection or representation of current state when that representation preserves the semantics necessary for the operation.

The Dataset remains the durable application-state authority even when only a bounded representation is supplied to the Agent.

## Modifying State

Agent reasoning may result in modification of Dataset state.

The modification is governed by the applicable Ruleset and may incorporate user input.

The fact that the Agent generated an output does not by itself make that output persistent application state.

A derived application defines when reasoning results constitute a valid state transition and how the next state becomes authoritative.

## State Evolution

Derived-application Design may define semantics for:

- state identity,
- state validity,
- transition validity,
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

SCF supplies a reusable realization foundation.

The derived application supplies the actual application state model.
