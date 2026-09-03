# FS-003 — ADR Application Realization and Initialization Plan

## Objective

Translate accepted application-realization and initialization Design into a stable normative contract that preserves ADR semantics across self-contained, managed, and provider-specific realizations.

## Planning Intent

FS-003 shall define normative obligations for semantic/realization distinction, determinate initialization, application and instance identity, applicable Ruleset authority, authoritative Dataset state, non-mutating initialization, continued transition semantics, self-contained and managed realizations, provider/packaging independence, builder non-authority, and cross-provider semantic preservation.

## Canonical Authority

Accepted Product Design remains the semantic source for FS-003 Planning. The FS-003 normative specification, once accepted, becomes the canonical normative contract for this Functional Set. Build artifacts are derived outputs and shall not invent, weaken, extend, or silently replace accepted Design and Planning meaning.

## Initialization Contract

A realization intended to initialize an Agent without prior application-specific conversational context shall expose or resolve enough information to determine the ADR-derived application, selected application instance, applicable Ruleset authority where consequential, relevant authoritative Dataset state, and application-owned initialization semantics required for the operation.

Initialization shall not itself commit Dataset state merely because the realization was loaded, attached, selected, discovered, or bound.

## Operation Contract

After initialization, read-only reasoning may inspect or explain state without creating a transition. State-changing operations remain subject to the derived application's Ruleset-governed proposal and acceptance semantics. FS-003 shall not standardize user command words.

## Realization Independence

The normative contract shall permit self-contained and separately managed realizations and shall not require one file format, provider, repository, builder, serialization, transport, storage service, or prompt syntax.

## Builder Boundary

Builder tooling may consume ADR seed specifications and derived-application definitions to create deployable realizations. Such tooling is outside ADR normative authority unless a later specification explicitly assigns otherwise. Generated artifacts remain derived realizations rather than independent ADR authority.

## Planned Normative Output

Planning shall produce `product/specs/FS-003-adr-application-realization.md`.

## Build Output

Build shall create one product-owned distributable FS-003 seed-spec artifact under `product/src/`. The artifact shall identify ADR, FS-003, exact Design revision `44d6ca44a408c2d4c79dba95d4dc363400ae1743`, canonical specification source, and complete active normative contract. It shall use the existing JSON seed-spec representation and shall not become a required runtime dependency.

## Build Validation

Mechanical validation shall verify artifact existence, identity, Design traceability, canonical-source declaration, runtime-dependency declaration, and exact requirement correspondence. Mechanical validation does not establish semantic acceptance.

## Deferred Realization Products

Concrete single-file application assembly, provider-specific bootstrap material, multi-provider output sets, managed Ruleset packages, and related generation workflows belong to derived products such as application-builder tooling rather than ADR core.
