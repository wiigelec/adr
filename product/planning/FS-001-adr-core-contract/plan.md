# FS-001 — ADR Core Contract Plan

## Objective

Translate the selected ADR Design into the smallest stable normative contract that an ADR-derived application must preserve.

The Functional Set is intentionally architecture-level. It specifies semantic responsibilities and boundaries without choosing an application domain, runtime architecture, storage mechanism, prompting system, model provider, or concrete SCF/CGI realization.

## Technical Intent

The canonical FS-001 normative specification shall define the minimum contract around four relationships:

1. **Role separation** — Agent, Dataset, and Ruleset remain semantically distinct.
2. **Authority** — committed application state belongs to the Dataset; transient Agent state does not become authority implicitly.
3. **Governed transition** — Agent reasoning may produce proposed state, but only a transition accepted under application-owned Ruleset semantics becomes committed Dataset state.
4. **Derived specialization** — each ADR-derived application supplies the concrete Dataset, Ruleset, transition, and Agent semantics needed by its domain.

## Agent Contract

The Agent is treated as transient reasoning capability.

FS-001 does not require a particular model, provider, memory mechanism, prompt architecture, or orchestration system.

The implementation must preserve the distinction between transient Agent working state and committed Dataset state. Agent output alone is not sufficient to establish committed application state.

## Dataset Contract

The Dataset is treated as the persistent state machine and sole authority for committed application state.

FS-001 does not prescribe the state schema, serialization, persistence technology, transaction mechanism, or formal state-machine representation.

A derived application must define enough Dataset semantics to determine what constitutes its committed state and what accepted transitions mean.

## Ruleset Contract

The Ruleset is treated as the governed source of application interpretation and state-transition semantics.

FS-001 does not prescribe the Ruleset representation or delivery mechanism.

A derived application must define enough Ruleset semantics to govern interpretation of current state, relevant inputs, and transition acceptance.

## Transition Contract

The implementation model preserves a semantic boundary between:

- current committed Dataset state;
- transient reasoning and user input;
- proposed next state; and
- accepted next Dataset state.

Acceptance may be automatic, user-mediated, externally validated, multi-step, or otherwise application-specific.

FS-001 does not select one mechanism. It requires only that acceptance behavior be grounded in application-owned Ruleset and Dataset semantics rather than invented ad hoc by the Agent or implementation.

## Bounded Context

A derived application may provide bounded representations of Ruleset meaning and Dataset state to the Agent.

The bounded representation must preserve the meaning required for the active operation and remain traceable to the authoritative Ruleset or Dataset source it represents.

FS-001 does not require complete source loading or prescribe retrieval technology.

## Missing Authority

When required governing semantics or committed-state information is unavailable, the operation is semantically underspecified.

The Agent must not use that absence as permission to invent application rules or committed state.

A derived application may define explicit fallback, refusal, recovery, or degraded behavior in later application-specific Design.

## Product Form

ADR remains a seed specification set.

FS-001 therefore does not require creation of an ADR runtime or a continuing runtime dependency on this repository.

Build for FS-001 must preserve the normative contract and may add only repository state necessary to realize or evaluate that contract without introducing product semantics beyond Design and Planning.

## Deferred Design and Planning

Later Functional Sets may address:

- SCF and SCF Contract Foundation contracts;
- CGI realization semantics;
- session-continuity outcomes;
- state identity, provenance, versioning, conflict, and recovery;
- authority precedence among user input, Ruleset, Dataset, Agent conclusions, and external evidence;
- stronger ADR-derived conformance profiles;
- application-specific realizations.

Those subjects are not implied requirements of FS-001.
