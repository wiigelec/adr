---
doc_id: DP-100
title: ADR Architecture
depends_on: []
---

# ADR Architecture

## Purpose

ADR is a foundational specification basis for AI-driven applications that need governed reasoning context and durable state across reasoning sessions.

ADR defines product meaning that derived applications realize independently. ADR does not require a derived application to depend on ADR as a runtime component.

## Core Model

ADR is organized around three primary concepts:

- **AI agent** — the reasoning engine.
- **Ruleset** — governed application context.
- **Dataset** — persistent application and session state.

The concepts are independently meaningful, but ADR's central product meaning is expressed through their relationship.

The ruleset establishes the application context within which reasoning occurs. The dataset carries relevant state beyond a single reasoning session. The AI agent reasons using context and state supplied by the derived application.

## Governing Relationship

A derived application uses governed context and relevant persisted state together to initialize or continue reasoning.

The relationship is semantic rather than implementation-specific. ADR does not require a particular model provider, prompting strategy, retrieval system, serialization, storage engine, API, or runtime architecture.

A realization may use complete source material, bounded projections, retrieval, generated context, or another mechanism when that mechanism preserves the intended relationship among ruleset, dataset, and agent.

## Continuity Outcome

ADR supports applications in which a later reasoning session can regain sufficient governed context and relevant persisted state to continue prior application work coherently.

Continuity is therefore not conversational memory alone. It is the reconstruction or re-establishment of enough explicit application context and state for reasoning to resume within the intended application domain.

## Derived-Application Independence

ADR provides semantic scaffolding rather than a mandatory runtime.

A derived application owns its concrete realization of:

- ruleset representation,
- dataset representation and persistence,
- context construction,
- state selection,
- agent invocation,
- retrieval or projection mechanisms,
- runtime orchestration.

Those choices remain implementation concerns unless later ADR Design gives them product-level meaning.

## Cross-Cutting Perspectives

ADR recognizes two cross-cutting perspectives over the core model:

- **SCF — Session Continuity Framework** focuses on continuity, state flow, and restoration across reasoning sessions.
- **CGI — Context Governance Infrastructure** focuses on governed context and its relationship to reasoning.

SCF and CGI describe perspectives over the same core product model. They are not independently established product domains unless later Design determines that separating them materially improves product meaning.

## Product Motivation

ADR is intended to reduce uncontrolled drift and hallucination in context-rich, data-intensive AI-driven work where a single chat session is insufficient to carry the full application context and state.

This motivation does not by itself define a measurable conformance threshold. Observable conformance semantics belong in later Design and Planning when sufficiently understood.

## Further Design

This architecture is decomposed into:

- DP-110 — Ruleset Context Governance
- DP-120 — Persistent Dataset State
- DP-130 — Agent Initialization
- DP-140 — Cross-Session Continuity

DP-110 and DP-120 establish the two foundational inputs to reasoning.

DP-130 defines their composition for initialization or continuation.

DP-140 defines the end-to-end continuity outcome produced from that composition.

## Design Boundary

This Design establishes product meaning without prescribing exact schemas, APIs, encodings, storage technologies, prompting techniques, retrieval algorithms, provider choices, or runtime implementation.

Consequential unresolved semantic decisions remain Design work. Planning may consume sufficiently developed Design but does not invent missing product meaning.
