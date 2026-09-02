---
doc_id: DP-110
title: Ruleset Architecture
depends_on:
  - DP-100
---

# Ruleset Architecture

## Purpose

The Ruleset defines the governed application semantics under which an Agent interprets input, reasons about current Dataset state, and participates in application state transitions.

Within ADR, Ruleset is an abstract product role. Each ADR-derived application defines the concrete Ruleset semantics appropriate to its domain.

## Application Semantics

The Ruleset establishes the meaning necessary for the Agent to operate within the intended application.

That meaning may include:

- domain concepts and relationships,
- interpretation rules,
- constraints,
- permitted or prohibited behavior,
- state-transition conditions,
- authority rules,
- application-specific operating guidance.

ADR does not require every derived application to represent these concerns in the same form.

The defining property is semantic: the Ruleset is the governed source of application meaning used to interpret input and state.

## Governance of State Transition

The Dataset represents current application state, but the Ruleset establishes the semantics under which that state is interpreted and changed.

A state transition is therefore not valid merely because an Agent can produce a different value.

The transition must remain consistent with the application semantics established by the Ruleset.

The exact meaning of validity is application-specific and is defined by the ADR-derived application.

## User Input and Agent Reasoning

User input and Agent reasoning may both affect the next application state.

The Ruleset governs how those influences are interpreted.

User input may introduce commands, decisions, corrections, observations, or other application-specific information.

Agent reasoning may derive conclusions, transformations, classifications, proposed actions, or other application-specific results.

Neither user input nor Agent reasoning independently replaces the Ruleset as the governing application semantics.

## Relationship to Dataset

Ruleset and Dataset have distinct roles:

- Ruleset defines how the application is understood and governed.
- Dataset represents the application's current persistent state.

A piece of information belongs conceptually to the Ruleset when its primary role is to define application meaning or governance.

A piece of information belongs conceptually to the Dataset when its primary role is to represent current persistent application state.

A derived application may realize both using the same physical technology without collapsing their semantic distinction.

## CGI — Chat Governance Infrastructure

**CGI — Chat Governance Infrastructure** is the realization framework aligned with the Ruleset concept.

CGI provides a reusable foundation for expressing and applying governed application context and Ruleset semantics to Agent reasoning.

CGI is not itself the concrete Ruleset of every ADR-derived application.

A derived application uses or specializes CGI to define the rules, context, constraints, and interpretation semantics specific to that application.

CGI may be specified without requiring a particular model provider, prompt format, retrieval system, or runtime framework.

## Bounded Context

An Agent need not receive every Ruleset artifact in full for every reasoning operation.

A derived application may construct a bounded representation of applicable Ruleset meaning.

Whatever mechanism is used, the resulting reasoning context must preserve the application semantics required for the current operation.

The method of context construction is not itself part of the abstract Ruleset definition unless a derived application gives that method product-level meaning.

## Authority

A Ruleset is an application-owned source of governed semantics.

Derived-application Design may need to establish how Ruleset authority interacts with:

- user input,
- Agent-derived conclusions,
- Dataset state,
- external evidence,
- conflicting or stale governing material.

ADR establishes that such authority relationships are consequential but does not impose one universal precedence model on all derived applications.

## Derived-Application Responsibility

Each ADR-derived application defines the Ruleset semantics required by its domain.

ADR supplies the architectural role and contract.

CGI supplies a reusable realization foundation.

The derived application supplies the actual application meaning.
