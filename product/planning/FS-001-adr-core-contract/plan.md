# FS-001 — ADR Core Contract Plan

## Objective

Translate the selected ADR Design into the smallest stable normative contract that an ADR-derived application must preserve, and define the physical realization Build must produce for that contract.

## Technical Intent

FS-001 has two technical outputs:

1. the canonical Product Planning and normative specification state that defines the ADR Core Contract; and
2. one distributable seed-spec artifact generated from that accepted canonical state.

The distributable artifact exists so ADR-derived application workflows can consume the FS-001 contract without depending on this repository's internal lifecycle layout.

## Canonical Authority

Canonical Product Design, Planning, and normative specification files remain authoritative.

The seed-spec artifact is derived output.

It must preserve accepted FS-001 meaning and must not create, alter, weaken, or extend normative semantics.

When the artifact and canonical source disagree, the canonical source controls and the artifact is defective.

## Artifact Boundary

Build shall create one product-owned distributable artifact under the product implementation/output domain selected during Build within existing authorized repository structure.

The artifact shall contain enough explicit information to identify:

- ADR as Agent · Dataset · Ruleset;
- the FS-001 identity;
- the exact Design revision consumed by FS-001;
- the complete active FS-001 normative contract;
- the distinction between canonical authority and derived artifact status; and
- the absence of a required ADR runtime dependency.

The artifact may use a simple project-native representation chosen by Build unless a representation choice materially changes meaning.

## Agent Contract

The Agent is transient reasoning capability.

The artifact must preserve the distinction between transient Agent state and committed Dataset state.

## Dataset Contract

The Dataset is the persistent state machine and sole authority for committed application state.

The artifact must preserve that committed-state authority without imposing a concrete persistence technology.

## Ruleset Contract

The Ruleset is the application-owned source of interpretation and transition-governance semantics.

The artifact must preserve that role without imposing a concrete Ruleset encoding or delivery mechanism.

## Transition Contract

The artifact must preserve the semantic boundary:

`current committed Dataset state + Ruleset + user input + Agent reasoning → proposed next state → governed acceptance → next committed Dataset state`

Acceptance remains application-specific.

## Bounded Context and Missing Authority

The artifact must preserve:

- bounded context fidelity and traceability to governing meaning; and
- missing required authority as underspecification rather than permission for Agent invention.

## Derived-Application Consumption

The artifact is intended for use during creation, Design, Planning, generation, initialization, or maintenance of ADR-derived applications.

Consumption of the artifact must not imply a continuing runtime dependency on ADR.

## Build Freedom

Build may choose the smallest practicable serialization and generation mechanism that preserves the Plan and normative requirements.

Build shall not introduce a generalized packaging framework, runtime library, code-generation platform, plugin system, or application-specific semantics merely to realize FS-001.

## Deferred Work

SCF, SCF Contract Foundation, CGI, full continuity behavior, richer conformance profiles, and application-specific realizations remain outside FS-001.
