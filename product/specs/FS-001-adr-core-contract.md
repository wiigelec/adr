# FS-001 — ADR Core Contract

### FS-001-NR-001 — Agent Dataset Ruleset Separation

**Classification: S**

An ADR-derived application shall preserve Agent, Dataset, and Ruleset as semantically distinct responsibilities: the Agent provides reasoning capability, the Dataset represents committed application state, and the Ruleset provides governed application interpretation and state-transition semantics.

### FS-001-NR-002 — Dataset Committed-State Authority

**Classification: S**

The Dataset shall be the sole authority for committed application state within an ADR-derived application.

### FS-001-NR-003 — Agent State Is Transient

**Classification: S**

Agent working memory, model-local memory, chat history, intermediate reasoning, session buffers, and other transient reasoning state shall not be treated as committed application state unless information derived from them is accepted into the Dataset through the application's governed transition semantics.

### FS-001-NR-004 — Ruleset Governs Interpretation

**Classification: S**

The Ruleset shall provide the application-owned semantics that govern interpretation of relevant input and current Dataset state.

### FS-001-NR-005 — Ruleset Governs Transition Validity

**Classification: S**

A proposed Dataset state transition shall be judged according to application-owned Ruleset semantics and current Dataset meaning rather than being considered valid merely because the Agent or implementation can produce it.

### FS-001-NR-006 — Proposed State Is Not Committed State

**Classification: S**

Agent reasoning or user input that could change application state shall remain non-authoritative with respect to committed Dataset state until the derived application's transition semantics accept the resulting proposal.

### FS-001-NR-007 — Transition Acceptance Is Application-Owned

**Classification: S**

Each ADR-derived application shall define the semantics that determine when a proposed state transition becomes accepted and therefore becomes the next committed Dataset state.

### FS-001-NR-008 — Transition Acceptance Must Preserve Governing Meaning

**Classification: S**

A transition-acceptance mechanism shall not invent application semantics beyond the derived application's applicable Ruleset and Dataset model.

### FS-001-NR-009 — Derived Dataset Semantics

**Classification: S**

Each ADR-derived application shall define the concrete Dataset semantics necessary to identify its committed application state and the meaning of accepted state transitions.

### FS-001-NR-010 — Derived Ruleset Semantics

**Classification: S**

Each ADR-derived application shall define the concrete Ruleset semantics necessary to govern application interpretation and state-transition validity.

### FS-001-NR-011 — Bounded Context Fidelity

**Classification: S**

When an Agent receives a bounded representation of Ruleset meaning or Dataset state, that representation shall preserve the semantics required for the active operation and remain traceable to the authoritative source it represents.

### FS-001-NR-012 — Missing Authority Is Underspecification

**Classification: S**

When an operation requires governing semantics or committed-state information that is unavailable, ambiguous, or unresolved, the operation shall be treated as semantically underspecified rather than as permission for the Agent to invent application rules or committed state.

### FS-001-NR-013 — Implementation Independence

**Classification: S**

ADR conformance shall not require a particular model provider, prompting technique, retrieval mechanism, orchestration framework, or persistence technology unless a later derived specification explicitly assigns such a choice product meaning.

### FS-001-NR-014 — ADR Runtime Independence

**Classification: S**

An ADR-derived application shall not be required to retain ADR itself or an ADR seed-spec artifact as a runtime dependency merely to preserve the FS-001 semantic contract.

### FS-001-NR-015 — Seed-Spec Artifact Realization

**Classification: B**

Build shall realize the accepted FS-001 contract as one distributable seed-spec artifact derived from canonical Product Design, Planning, and normative specification state.

### FS-001-NR-016 — Seed-Spec Artifact Fidelity

**Classification: B**

The FS-001 seed-spec artifact shall preserve the complete active FS-001 normative contract without inventing, weakening, extending, or silently replacing canonical ADR meaning.

### FS-001-NR-017 — Seed-Spec Artifact Identity and Traceability

**Classification: M**

The FS-001 seed-spec artifact shall identify ADR as Agent · Dataset · Ruleset, identify itself as derived from FS-001, and record the exact FS-001 Design revision `4874ac8f288afeb1b45abbdd042eacec6aa081d5`.

### FS-001-NR-018 — Derived Artifact Non-Authority

**Classification: S**

The FS-001 seed-spec artifact shall be treated as a distributable realization of canonical ADR meaning rather than as an independent normative authority.
