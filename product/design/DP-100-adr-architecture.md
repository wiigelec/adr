---
doc_id: DP-100
title: ADR Architecture
depends_on: []
---

# ADR Architecture

## Purpose

ADR — **Agent · Dataset · Ruleset** — is a seed specification set for deriving AI-driven applications.

ADR defines the foundational product concepts, relationships, and contracts that an ADR-derived application specializes. ADR does not define the concrete domain semantics of a particular application and does not need to exist as a runtime dependency of that application.

## Core Model

ADR defines three first-class concepts:

- **Agent** — the transient reasoning engine.
- **Dataset** — the persistent state machine and sole authority for committed application state.
- **Ruleset** — the governed application semantics that establish reasoning context and constrain valid interpretation and state transition.

The three concepts are defined separately so that their responsibilities remain clear, but ADR's primary meaning is expressed through their interaction.

## Dataset as Persistent Authority

The Dataset represents the durable state of an ADR-derived application.

A reasoning session reads relevant current Dataset state rather than depending on conversational memory, model memory, or transient Agent working state as the application's authoritative state.

The Dataset is a state machine in the semantic sense: it has a current state, that state may evolve, and the resulting accepted state is persisted so later reasoning sessions can continue from it.

Committed application state has one authoritative home: the Dataset.

ADR does not define the concrete state vocabulary, schema, storage model, or transition set of a derived application. Those semantics belong to the derived application.

## Ruleset as Governance

The Ruleset defines the application-specific semantics under which the Agent interprets input and Dataset state.

It governs the context in which reasoning occurs and the conditions under which application state may change.

The Ruleset does not merely supply static instructions. It participates in defining what application state means, what inputs are relevant, and what constitutes a valid transition from one Dataset state to another.

ADR defines the role of the Ruleset without defining the concrete domain rules of a derived application.

## Agent as Transient Reasoner

The Agent performs reasoning but owns no committed application state merely by reasoning about it.

Agent working memory, conversational context, intermediate conclusions, and model-local state are transient unless a derived application's governed transition semantics accept resulting information into the Dataset.

Transient Agent state must not silently substitute for committed Dataset authority.

## Agent Interaction

The Agent reasons over the current application situation using:

- relevant current Dataset state,
- the applicable Ruleset,
- user input,
- Agent reasoning and intermediate conclusions.

That interaction may produce a proposed state transition.

At the abstract level, the relationship is:

`current Dataset state + Ruleset + user input + Agent reasoning → proposed next state`

A proposed next state becomes the next authoritative Dataset state only when the derived application's Ruleset-governed transition semantics accept it.

This expression describes product meaning, not a required execution algorithm.

The Ruleset governs the interpretation and validity of the transition. The Dataset persists the accepted resulting application state. The Agent supplies the reasoning capability that participates in proposing or determining the transition.

## ADR-Derived Applications

An ADR-derived application specializes the seed architecture by defining its own:

- Dataset state semantics,
- Dataset state-transition semantics,
- Ruleset context and governance semantics,
- transition acceptance semantics,
- relationships between user input, Agent reasoning, and state change,
- Agent behavior needed by the application,
- concrete realization and implementation choices.

A derived application may therefore be highly domain-specific while remaining structurally grounded in ADR.

ADR conformance is about preserving the defined Agent, Dataset, Ruleset responsibilities and their contracts, not about copying one fixed application schema or runtime.

## SCF, SCF Contract Foundation, and CGI

ADR recognizes reusable realization frameworks aligned with the Dataset and Ruleset concepts.

**SCF — Session Continuity Framework** is the Dataset-side realization framework concerned with persistent state and continuity across Agent sessions.

**SCF Contract Foundation** is the reusable Dataset-side foundational contract set from which SCF realizations and ADR-derived application Dataset semantics may be constructed.

**CGI — Chat Governance Infrastructure** is the Ruleset-side realization framework concerned with governed context, interpretation, and state-transition semantics.

SCF, SCF Contract Foundation, and CGI are not the application-specific Dataset and Ruleset semantics themselves. They provide reusable foundations through which an ADR-derived application can define and realize those semantics.

They may be specified independently of any particular runtime implementation.

## Governed Context

An Agent may operate on bounded Ruleset context rather than receiving every Ruleset artifact in full.

A bounded context remains valid only when it preserves the governing semantics required for the active reasoning operation and remains traceable to those semantics.

When required governing semantics are missing, the operation is semantically underspecified. Missing Ruleset authority is not permission for the Agent to invent application meaning.

## Session Continuity

Session continuity follows from the persistent-state model.

A later Agent session can read relevant current Dataset state and operate under the applicable Ruleset without requiring the prior conversation itself to remain the application's authoritative memory.

Continuity therefore means preserving enough durable application state and governed semantics for reasoning to resume coherently across session boundaries.

## Product Motivation

ADR is intended for context-rich and data-intensive AI-driven applications where important application state and governing semantics exceed what should be entrusted to one transient chat session.

By separating durable state, governing semantics, and reasoning capability, ADR provides a structure for reducing uncontrolled drift and preserving application continuity.

ADR does not claim to eliminate hallucination and does not define a universal quantitative drift threshold.

## Further Design

This architecture is decomposed into:

- DP-110 — Ruleset Architecture
- DP-120 — Dataset Architecture
- DP-130 — Agent Interaction and State Transition
- DP-140 — Session Continuity

DP-110 defines Ruleset meaning and its relationship to CGI.

DP-120 defines Dataset state-machine and committed-authority meaning and its relationship to SCF and SCF Contract Foundation.

DP-130 defines how Agent reasoning, Ruleset governance, user input, current Dataset state, and transition acceptance participate in state change.

DP-140 defines continuity across reasoning sessions as an outcome of persistent Dataset state interpreted under the applicable Ruleset.

## Design Boundary

ADR establishes seed semantics and contracts.

It does not prescribe the concrete state vocabulary, domain rules, schemas, APIs, encodings, storage technologies, prompting techniques, retrieval algorithms, model providers, approval mechanisms, or runtime orchestration of an ADR-derived application.

Those choices belong to derived-application Design, Planning, or implementation according to whether they carry product meaning or merely realize already-defined meaning.
