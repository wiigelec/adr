---
doc_id: DP-150
title: Application Realization and Initialization
depends_on:
  - DP-100
  - DP-110
  - DP-120
  - DP-130
  - DP-140
---

# Application Realization and Initialization

## Purpose

ADR distinguishes application semantics from the concrete means by which those semantics are packaged, delivered, loaded, or operated in a particular environment.

This design establishes the semantic contract needed for a fresh Agent reasoning operation to bind to an ADR-derived application realization without making a file format, provider, repository, builder, or runtime technology part of ADR core meaning.

## Application Realization

An **application realization** is a concrete arrangement that makes an ADR-derived application's applicable Ruleset semantics and an application instance's relevant Dataset state available to an Agent.

A realization may be self-contained, distributed across multiple artifacts, backed by separately managed services or repositories, or composed through another environment-specific mechanism.

Realization changes physical arrangement. It does not collapse or replace the semantic distinction between Agent, Dataset, and Ruleset.

## Initialization

**Initialization** is the act of establishing enough application identity, applicable Ruleset authority, selected application-instance identity, relevant current Dataset state, and binding information for a reasoning operation to begin under determinate ADR semantics.

Initialization does not itself create committed application state.

Merely loading, attaching, selecting, discovering, or binding an application realization shall not silently mutate the authoritative Dataset unless the derived application's own governed transition semantics explicitly define and accept such a transition.

## Initialization Determinacy

A realization intended to initialize an Agent without prior application-specific conversational context must provide, directly or through resolvable references, enough information to determine:

- which ADR-derived application is being operated;
- which application instance is selected;
- which Ruleset authority applies when that distinction is consequential;
- where relevant current authoritative Dataset state is obtained; and
- any application-owned initialization semantics needed before ordinary reasoning can proceed.

Missing governing semantics are not permission for the Agent to invent application meaning.

## Operation After Initialization

After initialization, reasoning remains governed by the existing ADR interaction contract:

`current Dataset state + applicable Ruleset + user input + Agent reasoning → proposed next state`

Read-only interpretation may summarize, explain, inspect, or otherwise reason about application state without creating a Dataset transition.

A state-changing operation becomes committed state only through the derived application's Ruleset-governed transition acceptance semantics.

ADR does not standardize commands such as `help`, `status`, `start`, or `complete`. A derived application or realization profile may expose such interactions when they preserve application-owned semantics.

## Provider and Packaging Independence

The same ADR-derived application semantics may be realized for more than one Agent provider, packaging arrangement, or deployment environment.

Provider-specific bootstrap wording, prompt structure, serialization, file extension, transport, storage, retrieval, and presentation are realization concerns unless a derived specification intentionally assigns them product meaning.

A provider-specific realization must not silently weaken Dataset authority, Ruleset governance, instance isolation, transition acceptance, or applicable Ruleset determinacy.

## Self-Contained and Managed Realizations

A self-contained realization may physically package application identity, Ruleset material, Dataset state, initialization material, and other realization metadata together.

A managed realization may instead obtain shared Ruleset authority separately from independently stored Dataset instances.

Both are ADR-compatible when they preserve the accepted semantic boundaries and establish determinate initialization for the active reasoning operation.

## Builders and Generated Artifacts

Tooling may consume ADR seed specifications and derived-application definitions to produce one or more deployable application realizations.

Such builder tooling and its generated artifacts are not ADR normative authorities merely because they implement ADR semantics.

ADR does not require one builder, artifact schema, provider adapter, or generation technology.

## Portability

Portability means that application semantics and committed state can be transferred or rebound across compatible reasoning environments without treating transient conversational memory as authoritative application state.

Portability does not guarantee identical natural-language presentation or model behavior across providers.

A realization claiming cross-provider semantic equivalence must preserve the application-owned Ruleset and Dataset meaning required by the operations it supports.

## Design Boundary

ADR defines realization and initialization semantics only to the extent needed to preserve Agent, Dataset, Ruleset, instance, authority, and transition meaning.

Concrete single-file formats, multi-file layouts, provider profiles, prompt templates, serializers, repositories, storage APIs, deployment packages, and application-builder workflows belong to derived products or realization tooling.
