# Repository

This repository uses an installed repo-spec lifecycle framework.

## Lifecycle

Work proceeds through Design, Planning, Build, Validation, Semantic Review, and Acceptance.

`main` represents accepted repository state.

## Repository surfaces

- `repo/design/` — installed framework Design.
- `repo/specs/` — installed framework normative specifications.
- `repo/scripts/validate` — framework-owned mechanical Validation entry point.
- `scripts/validate` — repository-wide mechanical Validation entry point.
- `product/` is the product-owned domain. Product meaning is established independently through Product Design.
- `product/design/` — starting surface for Product Design.
- `user/` — user-owned operational material outside the framework.

Begin substantive product work in Product Design.

## ADR product model

ADR means **Agent · Dataset · Ruleset**.

An ADR-derived application defines reusable application semantics through its Ruleset and Dataset model. A derived application may have one or more independent application instances. Each instance has its own authoritative Dataset state, while one shared application Ruleset may govern multiple instances.

Ruleset and Dataset are semantic roles rather than required physical containers. A derived application may package them together in a self-contained artifact or manage a shared Ruleset separately from independent Datasets.

Agent reasoning is transient. A reasoning operation is bound to the applicable Ruleset and the selected application instance's relevant current Dataset state.

## Product Functional Sets

- `FS-001` — ADR Core Contract: minimum Agent, Dataset, Ruleset, authority, transition, and seed-spec contract.
- `FS-002` — ADR Application Instances and Ruleset Binding: application/instance topology, shared Ruleset authority, independent Dataset state, Ruleset binding, and consequential Ruleset evolution.
- `FS-003` — ADR Application Realization and Initialization: realization/semantic separation, determinate fresh-session initialization, read-only initialization, and provider/packaging independence.

Concrete single-file, multi-file, and provider-specific application assembly belongs to realization tooling such as `adr-app-builder`, not to ADR core semantics.

The exact repo-spec framework source revision used to initialize this repository is recorded in `repo/validation/framework-source.json`.

Validation is mechanical evaluation only. Semantic Review evaluates meaning and fidelity. Acceptance is intentional integration of a satisfactory candidate into `main`.
