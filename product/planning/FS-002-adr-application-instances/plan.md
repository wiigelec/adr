# FS-002 — ADR Application Instances and Ruleset Binding Plan

## Objective

Translate the selected ADR application-instance topology into a stable normative contract for ADR-derived applications that support independent application instances, shared Ruleset authority, or multiple distinguishable Ruleset states.

## Planning Intent

FS-002 shall define normative obligations for:

1. application definition versus application-instance state;
2. independent Dataset authority per application instance;
3. shared Ruleset governance across multiple instances;
4. transition isolation between instances unless application-owned semantics explicitly define otherwise;
5. semantic determinacy of the applicable Ruleset when multiple Ruleset states may coexist;
6. preservation of Ruleset/Dataset distinction across co-located and separately managed physical realizations;
7. application-owned handling of consequential Ruleset evolution; and
8. Agent-session binding to the selected instance and applicable Ruleset.

## Canonical Authority

Accepted Product Design remains the semantic source for FS-002 Planning.

The FS-002 normative specification, once created and accepted, will become the canonical normative contract for this Functional Set.

Any Build artifact or realization produced later is derived output and must not invent, weaken, extend, or silently replace accepted Design and Planning meaning.

## Application and Instance Contract

Planning shall preserve the distinction between:

- the reusable ADR-derived application definition, which supplies application-owned Dataset semantics, Ruleset semantics, transition semantics, and required Agent behavior; and
- an application instance, whose independently continuing committed state is represented by its Dataset.

One application may support one or more instances.

## Dataset Isolation Contract

Each application instance shall retain independent committed Dataset authority.

Shared schemas, Ruleset semantics, storage mechanisms, or Agent access shall not by themselves merge Dataset authority.

A state transition shall be scoped to the selected application instance unless application-owned Ruleset semantics explicitly define a cross-instance operation.

## Shared Ruleset Contract

One application Ruleset may govern multiple independent application instances.

Shared Ruleset authority shall not by itself authorize cross-instance state transfer, mutation, or inference.

## Applicable Ruleset Contract

When only one Ruleset state can govern an application operation, FS-002 shall not require a separate revision identifier.

When multiple distinguishable Ruleset states may coexist, the normative contract shall require enough identity or traceability to determine which governing semantics apply to the selected Dataset operation.

Planning shall remain neutral as to the realization mechanism.

## Physical Realization Contract

FS-002 shall preserve the semantic distinction between Ruleset and Dataset without requiring separate physical containers.

The normative contract shall permit both:

- self-contained realizations in which Ruleset and Dataset material are physically co-located; and
- managed realizations in which one separately managed Ruleset authority governs multiple independently stored Datasets.

## Ruleset Evolution Contract

When a Ruleset change can alter the interpretation, validity, or permitted transitions of existing Dataset state, the derived application shall own the semantics needed to determine compatibility, migration, acceptance, refusal, recovery, or other defined behavior.

FS-002 shall not prescribe one universal migration algorithm or versioning technology.

## Agent Session Contract

A reasoning operation shall be semantically bound to the applicable Ruleset and relevant current Dataset state of the selected application instance.

Agent reuse across instances shall not by itself transfer committed state or create cross-instance state authority. Cross-instance state operations remain governed by explicit application-owned Ruleset and transition semantics.

## Planned Normative Output

Planning shall produce:

`product/specs/FS-002-adr-application-instances.md`

The normative requirements should be the smallest stable set that captures the selected Design meaning and should use conditional obligations where the behavior only becomes consequential for multi-instance applications or coexisting Ruleset states.

## Build Output

Build shall create one product-owned distributable FS-002 seed-spec artifact under `product/src/`.

The artifact shall contain enough explicit information to identify:

- ADR as Agent · Dataset · Ruleset;
- the FS-002 identity;
- the exact Design revision consumed by FS-002;
- the complete active FS-002 normative contract;
- the distinction between canonical authority and derived artifact status; and
- the absence of a required ADR runtime dependency.

The artifact shall use the same simple project-native JSON seed-spec representation established by FS-001 unless that representation proves unable to preserve FS-002 meaning.

Build shall not introduce Git, a corporate chat provider, a portable application-file profile, a database, or another technology choice merely to realize FS-002.

## Build Validation

Mechanical validation shall verify that:

- the FS-002 seed artifact exists;
- its ADR, Functional Set, authority, and Design-revision identity are correct;
- its normative requirements exactly correspond to the canonical FS-002 specification; and
- mechanically evaluated FS-002 requirements are bound to the seed-spec-artifact task.

Mechanical validation does not establish semantic acceptance.

## Deferred Realization Profiles

Candidate future Functional Sets may separately define:

- a portable self-contained Ruleset + Dataset artifact;
- a managed shared-Ruleset + independent-Dataset realization; and
- other environment-specific realization profiles.

Those profiles are intentionally outside FS-002.
