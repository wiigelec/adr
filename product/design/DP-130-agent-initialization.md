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

The Agent is the transient reasoning engine that operates over governed application semantics and current committed state.

This Design defines the abstract interaction through which Ruleset, Dataset, user input, and Agent reasoning can produce a proposed state transition and through which an accepted transition becomes authoritative Dataset state.

## Reasoning Inputs

An Agent reasoning operation may consume:

- applicable Ruleset semantics,
- relevant current Dataset state,
- user input,
- other application-authorized information.

The Ruleset establishes how these inputs are interpreted.

The Dataset establishes the authoritative durable current state from which the application is operating.

User input introduces new application-relevant information or intent.

The Agent supplies transient reasoning over those inputs.

## Agent Transience

The Agent owns no committed application state merely by reasoning.

Chat history, model-local memory, reasoning state, intermediate conclusions, and session buffers are transient unless information derived from them is accepted into the Dataset through the application's governed transition semantics.

Transient Agent state must never silently substitute for current committed Dataset state.

## Abstract Transition Model

ADR models the central interaction as:

`current Dataset state + Ruleset + user input + Agent reasoning → proposed next state`

A proposed next state becomes authoritative only if the derived application's Ruleset-governed transition semantics accept it.

This is a semantic relationship rather than a required implementation pipeline.

Not every Agent operation must propose a state change.

Not every user input must produce a state change.

Not every proposed state change must be accepted.

## Agent Read

The Agent may read a representation of current Dataset state sufficient for the reasoning operation.

The Agent may also receive a bounded representation of applicable Ruleset semantics.

ADR does not require the complete Dataset or complete Ruleset to be placed directly into model context.

Derived applications may use projections, retrieval, context construction, tools, or other mechanisms while preserving governing semantics, current-state meaning, and traceability to authoritative Ruleset and Dataset sources.

## Missing Context

If a reasoning operation requires governing semantics or current-state information that is not available, the operation is semantically underspecified.

The Agent must not treat the absence of required authority as permission to invent application rules or committed state.

A derived application may define explicit fallback, refusal, recovery, or degraded behavior for such conditions.

## Agent Reasoning

Agent reasoning may:

- interpret user input,
- inspect or analyze current state,
- derive conclusions,
- identify candidate actions,
- propose state changes,
- explain or communicate application results.

ADR does not define a universal reasoning algorithm.

The reasoning engine remains subject to the application's Ruleset and current Dataset state.

## Proposed State

An Agent output is not automatically a Dataset mutation.

A reasoning result that could affect application state is a proposal until the derived application's semantics accept it as a valid governed transition.

This distinction separates:

- reasoning from persistence,
- proposals from committed state,
- transient intermediate work from durable application authority.

ADR requires this semantic distinction but does not require one universal approval, transaction, or commit mechanism.

## Transition Acceptance

A derived application defines the conditions under which a proposed state transition becomes accepted.

Those conditions are governed by the applicable Ruleset and interpreted against current Dataset state.

Acceptance may be automatic, user-mediated, externally validated, multi-step, or otherwise specialized by the derived application.

Whatever mechanism is chosen, it must not invent semantics beyond the application's Ruleset and Dataset model.

## Ruleset Governance

Ruleset semantics govern the Agent's interpretation of current state and the validity of proposed transitions.

This includes whatever application-specific authority, constraints, transition conditions, or interpretation rules the derived application defines.

CGI provides the Ruleset-side realization foundation for applying this governance to Agent interaction.

## Dataset Persistence

When a proposed state transition is accepted, the next Dataset state becomes the durable authoritative application state used by subsequent reasoning.

SCF Contract Foundation provides reusable Dataset-side continuity and authority contracts.

SCF provides the broader Dataset-side realization framework for maintaining that continuity across sessions.

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
- what counts as a valid proposed transition,
- what counts as an accepted transition,
- when accepted reasoning results become durable state,
- what authority user input carries,
- how invalid or conflicting transitions are handled,
- what behavior applies when required authority is missing,
- what Agent behavior is required by the domain.
