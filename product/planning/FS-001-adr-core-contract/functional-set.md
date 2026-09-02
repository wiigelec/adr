# FS-001 — ADR Core Contract

functional_set: FS-001
design_revision: 54a52705d49d11ee6287470f0562e68172d7075a

## Purpose

FS-001 establishes the minimum semantic contract that distinguishes an ADR-derived application from an arbitrary AI-driven application.

It selects the core Agent, Dataset, Ruleset, authority, and state-transition meaning from ADR Design and expresses that meaning as stable normative obligations.

## Selected Design Scope

FS-001 consumes the following Design at revision `54a52705d49d11ee6287470f0562e68172d7075a`:

- DP-100 — ADR Architecture:
  - Purpose
  - Core Model
  - Dataset as Persistent Authority
  - Ruleset as Governance
  - Agent as Transient Reasoner
  - Agent Interaction
  - ADR-Derived Applications
  - Governed Context
  - Design Boundary
- DP-110 — Ruleset Architecture:
  - Purpose
  - Application Semantics
  - Governance of State Transition
  - User Input and Agent Reasoning
  - Relationship to Dataset
  - Bounded Governed Context
  - Missing Governing Semantics
  - Authority
  - Derived-Application Responsibility
- DP-120 — Dataset Architecture:
  - Purpose
  - Committed-State Authority
  - Persistent State Machine
  - State Transition
  - Dataset and Ruleset Boundary
  - Reading State
  - Modifying State
  - Derived-Application Responsibility
- DP-130 — Agent Interaction and State Transition:
  - Purpose
  - Reasoning Inputs
  - Agent Transience
  - Abstract Transition Model
  - Agent Read
  - Missing Context
  - Proposed State
  - Transition Acceptance
  - Ruleset Governance
  - Dataset Persistence
  - Derived-Application Responsibility

## Functional Boundary

FS-001 establishes the core ADR conformance contract only.

It includes:

- separation of Agent, Dataset, and Ruleset responsibilities;
- Dataset authority for committed application state;
- transient Agent/session/model state;
- Ruleset ownership of application interpretation and transition governance;
- the distinction between proposed and committed state;
- application-owned transition acceptance semantics;
- bounded context fidelity and traceability;
- underspecification when required authority is missing; and
- derived-application ownership of concrete state and governance semantics.

## Exclusions

FS-001 does not establish:

- concrete Dataset schemas or storage technology;
- concrete Ruleset formats, prompt structures, or retrieval mechanisms;
- specific model providers or Agent orchestration;
- universal state-transition approval mechanics;
- SCF implementation semantics;
- SCF Contract Foundation detailed contracts;
- CGI implementation semantics;
- full session-continuity success, failure, or recovery requirements;
- quantitative drift or hallucination measures;
- a runtime dependency on ADR;
- application-specific state vocabularies, rules, or workflows.

Those concerns remain available for later Functional Sets where supported by Design.

## Planning Result

FS-001 is realized through:

- this Functional Set boundary;
- `plan.md`;
- `product/specs/FS-001-adr-core-contract.md`.

All current FS-001 normative requirements are semantic-evaluation obligations. Planning therefore introduces no mechanical requirement-to-validation-task bindings.
