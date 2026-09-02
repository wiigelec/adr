# FS-003 — ADR Application Realization and Initialization

### FS-003-NR-001 — Semantic and Realization Distinction

**Classification: S**

An ADR-derived application's semantic definition shall remain distinguishable from any concrete realization used to package, deliver, discover, bind, or operate that application.

### FS-003-NR-002 — Initialization Determinacy

**Classification: S**

A realization intended to initialize an Agent without prior application-specific conversational context shall provide or resolve enough information to determine the application, selected application instance, applicable Ruleset authority where consequential, and relevant authoritative Dataset state.

### FS-003-NR-003 — Application Identity

**Classification: S**

Initialization shall establish which ADR-derived application semantics govern the reasoning operation.

### FS-003-NR-004 — Instance Identity

**Classification: S**

Initialization of an independently continuing application instance shall establish which application instance's Dataset authority is selected for the reasoning operation.

### FS-003-NR-005 — Applicable Ruleset at Initialization

**Classification: S**

When multiple distinguishable Ruleset states may coexist, initialization shall preserve enough identity or traceability to determine the applicable governing Ruleset for the selected operation.

### FS-003-NR-006 — Dataset Authority at Initialization

**Classification: S**

Committed application state available during initialization shall be interpreted from the selected application instance's authoritative Dataset rather than from transient Agent or conversational memory.

### FS-003-NR-007 — Initialization Is Not Implicit Mutation

**Classification: S**

Loading, attaching, selecting, discovering, or binding an application realization shall not by itself create a committed Dataset transition unless the derived application's own Ruleset-governed transition semantics explicitly define and accept such a transition.

### FS-003-NR-008 — Missing Governance Is Not Permission

**Classification: S**

When governing Ruleset semantics required for initialization or operation are missing or indeterminate, the Agent shall not invent application meaning or treat that absence as permission to mutate committed Dataset state.

### FS-003-NR-009 — Read-Only Reasoning Permitted

**Classification: S**

After initialization, an Agent may inspect, summarize, explain, or otherwise reason about application state without creating a Dataset transition when the applicable application semantics classify the operation as non-mutating.

### FS-003-NR-010 — Transition Contract Preserved

**Classification: S**

A state-changing operation after initialization shall become committed Dataset state only through the derived application's applicable Ruleset-governed transition acceptance semantics.

### FS-003-NR-011 — Self-Contained Realization Permitted

**Classification: S**

A realization may physically co-locate application identity, Ruleset material, Dataset state, initialization material, and realization metadata while preserving their ADR semantic roles and authority boundaries.

### FS-003-NR-012 — Managed Realization Permitted

**Classification: S**

A realization may obtain shared Ruleset authority separately from independently stored Dataset instances when initialization preserves applicable Ruleset determinacy and Dataset-instance authority.

### FS-003-NR-013 — Provider and Packaging Independence

**Classification: S**

FS-003 conformance shall not require a particular Agent provider, bootstrap prompt, file format, serialization, file count, repository, transport, storage service, or application-builder technology.

### FS-003-NR-014 — Cross-Realization Semantic Preservation

**Classification: S**

When the same ADR-derived application is realized for multiple providers or packaging environments, each claimed semantically compatible realization shall preserve the Ruleset, Dataset, instance, authority, and transition meaning required by the operations it supports.

### FS-003-NR-015 — Seed-Spec Artifact Realization

**Classification: B**

Build shall realize the accepted FS-003 contract as one distributable seed-spec artifact derived from canonical Product Design, Planning, and normative specification state.

### FS-003-NR-016 — Seed-Spec Artifact Fidelity

**Classification: B**

The FS-003 seed-spec artifact shall preserve the complete active FS-003 normative contract without inventing, weakening, extending, or silently replacing canonical ADR meaning.

### FS-003-NR-017 — Seed-Spec Artifact Identity and Traceability

**Classification: M**

The FS-003 seed-spec artifact shall identify ADR as Agent · Dataset · Ruleset, identify itself as derived from FS-003, and record the exact FS-003 Design revision `3c901f08c1014fcbc014f45aedb3a485f791a9f8`.

### FS-003-NR-018 — Builder and Generated Artifact Non-Authority

**Classification: S**

Application-builder tooling and generated application realizations shall not be treated as independent ADR normative authority merely because they consume or implement ADR semantics.
