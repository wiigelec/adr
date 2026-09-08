# FS-001 — ADR Core Contract

functional_set: FS-001
design_revision: 1918caa562dc459de34f1181bf72dca24ec4dbeb

## Purpose

FS-001 establishes the minimum semantic contract that distinguishes an ADR-derived application from an arbitrary AI-driven application and defines the first distributable ADR seed-spec realization of that contract.

It selects the core Agent, Dataset, Ruleset, authority, state-transition, and seed-spec realization meaning from ADR Design and expresses that meaning as stable normative obligations.

## Selected Design Scope

FS-001 consumes ADR Design at revision `1918caa562dc459de34f1181bf72dca24ec4dbeb` including:

- DP-100 — ADR Architecture:
  - Agent, Dataset, and Ruleset roles;
  - Dataset committed-state authority;
  - Agent transience;
  - Ruleset governance;
  - proposed versus accepted state;
  - ADR-derived application specialization;
  - bounded governed context;
  - seed specification realization;
  - runtime independence.
- DP-110 — Ruleset Architecture:
  - governed application semantics;
  - Ruleset ownership of Dataset structural/schema requirements, interpretation, validity, invariants, transition validity, and transition acceptance;
  - mechanical rule realizations as implementations rather than independent semantic authority;
  - bounded context fidelity;
  - missing-governance underspecification.
- DP-120 — Dataset Architecture:
  - persistent state-machine semantics;
  - committed-state authority;
  - governed state transition;
  - Dataset/Ruleset boundary.
- DP-130 — Agent Interaction and State Transition:
  - transient Agent reasoning;
  - proposed state;
  - transition acceptance;
  - authoritative Dataset persistence.

## Functional Boundary

FS-001 includes:

- separation of Agent, Dataset, and Ruleset responsibilities;
- Dataset authority for committed application state;
- transient Agent/session/model state;
- Ruleset ownership of rules governing Dataset structure/schema, interpretation, validity, invariants, transition validity, and transition acceptance;
- the distinction between proposed and committed state;
- Ruleset-owned transition acceptance semantics;
- schemas, validators, transition checkers, and equivalent enforcement mechanisms as realizations of Ruleset-owned semantics rather than independent semantic authorities;
- bounded context fidelity and traceability;
- underspecification when required authority is missing;
- derived-application definition of Ruleset semantics and Dataset ownership of committed state; and
- one distributable seed-spec artifact carrying the accepted FS-001 contract.

## Exclusions

FS-001 does not establish:

- concrete Dataset schemas or storage technology;
- concrete Ruleset formats, prompt structures, or retrieval mechanisms;
- specific model providers or Agent orchestration;
- universal transition-approval mechanics;
- SCF implementation semantics;
- SCF Contract Foundation detailed contracts;
- CGI implementation semantics;
- full session-continuity success, failure, or recovery requirements;
- quantitative drift or hallucination measures;
- a runtime dependency on ADR;
- application-specific state vocabularies, rules, or workflows.

## Planning Result

FS-001 is realized through:

- this Functional Set boundary;
- `plan.md`;
- `product/specs/FS-001-adr-core-contract.md`; and
- a Build-produced distributable seed-spec artifact derived from the accepted canonical FS-001 specification state.

The artifact is a realization of accepted meaning, not a second normative source.
