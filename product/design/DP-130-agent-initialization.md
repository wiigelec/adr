---
doc_id: DP-130
title: Agent Interaction and State Transition
depends_on:
  - DP-100
  - DP-110
  - DP-120
---

# Agent Interaction and State Transition

## Purpose

The Agent is the reasoning engine that operates over governed application semantics and current persistent state.

This Design defines the abstract interaction through which Ruleset, Dataset, user input, and Agent reasoning can produce a governed application state transition.

## Reasoning Inputs

An Agent reasoning operation may consume:

- applicable Ruleset semantics,
- relevant current Dataset state,
- user input,
- other application-authorized information.

The Ruleset establishes how these inputs are interpreted.

The Dataset establishes the durable current state from which the application is operating.

User input introduces new application-relevant information or intent.

The Agent supplies reasoning over those inputs.

## Abstract Transition Model

ADR models the central interaction as:

`current Dataset state + Ruleset + user input + Agent reasoning → next Dataset state`

This is a semantic relationship rather than a required implementation pipeline.

Not every Agent operation must produce a state change.

Not every user input must produce a state change.

When a state change does occur, the resulting transition is governed by application-specific Ruleset semantics and becomes meaningful only according to the derived application's Dataset semantics.

## Agent Read

The Agent may read a representation of current Dataset state sufficient for the reasoning operation.

The Agent may also receive a bounded representation of applicable Ruleset semantics.

ADR does not require the complete Dataset or complete Ruleset to be placed directly into model context.

Derived applications may use projections, retrieval, context construction, tools, or other mechanisms while preserving the governing semantics and current-state meaning.

## Agent Reasoning

Agent reasoning may:

- interpret user input,
- inspect or analyze current state,
- derive conclusions,
- identify candidate actions,
- propose or determine state changes,
- explain or communicate application results.

ADR does not define a universal reasoning algorithm.

The reasoning engine remains subject to the application's Ruleset and state semantics.

## Agent Write

An Agent output is not automatically a Dataset mutation.

A state modification occurs only when the derived application's semantics treat the result as a valid governed transition.

This distinction allows applications to separate:

- reasoning from persistence,
- proposals from accepted changes,
- transient intermediate work from durable application state.

The exact acceptance mechanism is application-specific.

## Ruleset Governance

Ruleset semantics govern the Agent's interpretation of current state and the validity of transitions.

This includes whatever application-specific authority, constraints, transition conditions, or interpretation rules the derived application defines.

CGI provides the Ruleset-side realization foundation for applying this governance to Agent interaction.

## Dataset Persistence

When a valid state transition occurs, the next Dataset state becomes the durable application state used by subsequent reasoning.

SCF provides the Dataset-side realization foundation for maintaining that continuity across sessions.

## Initialization and Continuation

Starting a new Agent session and continuing prior application work both use the same foundational relationship:

- establish applicable Ruleset semantics,
- obtain relevant current Dataset state,
- reason from that governed application condition.

A derived application may distinguish initial start, continuation, recovery, refresh, or other modes when those distinctions matter to its product semantics.

## Derived-Application Responsibility

ADR defines the interaction contract among Agent, Dataset, Ruleset, and user input.

Each ADR-derived application defines the concrete semantics for:

- what the Agent may read,
- what counts as a valid transition,
- when reasoning results become durable state,
- what authority user input carries,
- how invalid or conflicting transitions are handled,
- what Agent behavior is required by the domain.
