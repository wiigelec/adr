# FS-002 — ADR Application Instances and Ruleset Binding

functional_set: FS-002
design_revision: 87b0ab6d1dfcb5a0a18f93e1c04bf845265e71de

## Purpose

FS-002 establishes the ADR contract for reusable application definition, independent application instances, shared Ruleset authority, Dataset-instance isolation, applicable Ruleset binding, and continuity across consequential Ruleset evolution.

It selects the application-topology meaning added to accepted ADR Design after FS-001 without widening or rewriting the already accepted FS-001 Core Contract.

## Selected Design Scope

FS-002 consumes ADR Design at revision `87b0ab6d1dfcb5a0a18f93e1c04bf845265e71de`, including:

- DP-100 — ADR Architecture:
  - application definition and application instances;
  - one application Ruleset governing multiple independent Dataset instances;
  - Ruleset/Dataset binding;
  - physical co-location or separation of Ruleset and Dataset material;
  - Ruleset evolution and instance compatibility;
  - Agent session binding.
- DP-110 — Ruleset Architecture:
  - shared Ruleset authority;
  - applicable Ruleset identity when multiple Ruleset states may coexist;
  - consequential Ruleset evolution.
- DP-120 — Dataset Architecture:
  - Dataset authority scoped to an application instance;
  - independent application-instance state;
  - transition isolation;
  - intrinsic or explicit applicable Ruleset binding.
- DP-130 — Agent Interaction and State Transition:
  - instance-bound reasoning inputs;
  - Dataset transition isolation;
  - continuation under an applicable Ruleset/Dataset binding;
  - incompatibility behavior delegated to application-owned semantics.
- DP-140 — Session Continuity:
  - continuity evaluated independently per application instance;
  - Ruleset identity/traceability where multiple Ruleset states coexist;
  - Agent reuse without cross-instance committed-state transfer;
  - continuity implications of consequential Ruleset evolution.

## Functional Boundary

FS-002 includes:

- distinction between reusable ADR-derived application definition and independently continuing application instances;
- one application Ruleset governing multiple independent Dataset instances;
- Dataset authority scoped to the selected application instance;
- default isolation of state transitions between instances;
- semantic determinacy of the applicable Ruleset when multiple governing Ruleset states may coexist;
- preservation of Ruleset/Dataset semantic distinction when physically co-located;
- support for separately managed shared Ruleset authority and independently stored Datasets;
- application-owned compatibility, migration, refusal, recovery, or other semantics when consequential Ruleset evolution affects existing Dataset state; and
- Agent reasoning bound to the selected Dataset instance and applicable Ruleset for the active operation.

## Exclusions

FS-002 does not establish:

- Git, GitHub, or any other repository technology as required Ruleset storage;
- Markdown, JSON, YAML, database, or other required Dataset or Ruleset encoding;
- Microsoft Copilot, ChatGPT, Claude, Gemini, or any required Agent provider;
- a mandatory portable-artifact profile;
- a mandatory managed-Ruleset profile;
- a universal Ruleset versioning scheme;
- a universal Dataset migration algorithm;
- cross-instance transitions or shared Dataset state;
- application-specific state vocabularies, workflows, rules, approval semantics, or recovery policy;
- SCF implementation semantics;
- CGI implementation semantics; or
- a new ADR runtime dependency.

## Relationship to FS-001

FS-001 remains the minimum ADR Core Contract.

FS-002 builds on that contract by defining application-instance topology and Ruleset/Dataset binding semantics that are consequential when an ADR-derived application supports multiple independently continuing instances or multiple distinguishable Ruleset states.

FS-002 does not retroactively change the Design revision selected by FS-001.

## Planning Result

FS-002 is realized through:

- this Functional Set boundary;
- `plan.md`;
- `product/specs/FS-002-adr-application-instances.md`; and
- one Build-produced distributable seed-spec artifact derived from the accepted canonical FS-002 specification state.

The artifact is a realization of accepted meaning, not a second normative source.

Portable self-contained application artifacts, managed shared-Ruleset application realizations, and other environment-specific profiles remain separate future Functional Sets.
