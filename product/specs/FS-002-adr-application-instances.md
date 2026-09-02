# FS-002 — ADR Application Instances and Ruleset Binding

### FS-002-NR-001 — Application Definition and Instance Distinction

**Classification: S**

An ADR-derived application shall distinguish reusable application definition from independently continuing application instances whose committed state is represented by their Datasets.

### FS-002-NR-002 — Independent Dataset Authority

**Classification: S**

Each application instance shall retain independent Dataset authority for its committed application state.

### FS-002-NR-003 — Shared Ruleset Governance

**Classification: S**

One application Ruleset may govern multiple independent application instances without merging their Dataset authority.

### FS-002-NR-004 — Instance-Scoped Transition

**Classification: S**

A proposed or accepted Dataset state transition shall be scoped to the selected application instance unless the derived application's Ruleset explicitly defines a cross-instance operation.

### FS-002-NR-005 — No Implicit Cross-Instance Authority

**Classification: S**

Shared Ruleset semantics, schemas, storage mechanisms, or Agent access shall not by themselves authorize state transfer, mutation, or committed-state inference between application instances.

### FS-002-NR-006 — Applicable Ruleset Determinacy

**Classification: S**

When multiple distinguishable Ruleset states may coexist, the derived application shall preserve enough Ruleset identity or traceability to determine which governing semantics apply to the selected Dataset operation.

### FS-002-NR-007 — No Unnecessary Revision Identifier

**Classification: S**

When only one Ruleset state can govern an application operation, ADR conformance shall not require a separate Ruleset revision identifier merely to satisfy FS-002.

### FS-002-NR-008 — Physical Co-Location Permitted

**Classification: S**

A derived application may physically co-locate Ruleset and Dataset material while preserving their semantic distinction and authority boundaries.

### FS-002-NR-009 — Managed Separation Permitted

**Classification: S**

A derived application may realize one separately managed Ruleset authority governing multiple independently stored Dataset instances.

### FS-002-NR-010 — Consequential Ruleset Evolution

**Classification: S**

When Ruleset evolution can alter the interpretation, validity, or permitted transitions of existing Dataset state, the derived application shall define the compatibility, migration, acceptance, refusal, recovery, or other semantics needed to keep the affected instance well-defined.

### FS-002-NR-011 — No Silent Retroactive Reinterpretation

**Classification: S**

A changed Ruleset shall not silently retroactively reinterpret committed Dataset state unless the derived application's own semantics establish that resulting meaning.

### FS-002-NR-012 — Agent Session Binding

**Classification: S**

A reasoning operation shall be semantically bound to the applicable Ruleset and relevant current Dataset state of the selected application instance.

### FS-002-NR-013 — Agent Reuse Does Not Transfer State

**Classification: S**

Reuse of an Agent implementation, model, or reasoning session mechanism across application instances shall not transfer committed Dataset state between those instances.

### FS-002-NR-014 — Implementation Independence

**Classification: S**

FS-002 conformance shall not require Git, GitHub, a particular file format, a database, a corporate chat provider, or another realization technology unless a later derived specification explicitly assigns that choice product meaning.

### FS-002-NR-015 — Seed-Spec Artifact Realization

**Classification: B**

Build shall realize the accepted FS-002 contract as one distributable seed-spec artifact derived from canonical Product Design, Planning, and normative specification state.

### FS-002-NR-016 — Seed-Spec Artifact Fidelity

**Classification: B**

The FS-002 seed-spec artifact shall preserve the complete active FS-002 normative contract without inventing, weakening, extending, or silently replacing canonical ADR meaning.

### FS-002-NR-017 — Seed-Spec Artifact Identity and Traceability

**Classification: M**

The FS-002 seed-spec artifact shall identify ADR as Agent · Dataset · Ruleset, identify itself as derived from FS-002, and record the exact FS-002 Design revision `87b0ab6d1dfcb5a0a18f93e1c04bf845265e71de`.

### FS-002-NR-018 — Derived Artifact Non-Authority

**Classification: S**

The FS-002 seed-spec artifact shall be treated as a distributable realization of canonical ADR meaning rather than as an independent normative authority.
