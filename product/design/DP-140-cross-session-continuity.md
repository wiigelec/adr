---
doc_id: DP-140
title: Session Continuity
depends_on:
  - DP-100
  - DP-110
  - DP-120
  - DP-130
---

# Session Continuity

## Purpose

Session continuity is the ability of an ADR-derived application to preserve coherent application operation across separate Agent reasoning sessions.

Continuity is grounded in authoritative persistent Dataset state interpreted under the applicable Ruleset.

It does not require the prior chat transcript, model memory, or transient Agent state to function as the application's authoritative memory.

## Continuity Model

A later Agent session can continue prior application work when it can obtain:

- applicable Ruleset semantics,
- relevant current Dataset state,
- any new user input or other application-authorized information needed for the current operation.

The Agent reasons from that governed condition and may participate in a further proposed state transition.


For a derived application with multiple instances, continuity is evaluated independently for the selected application instance. Each instance continues from its own authoritative Dataset state under the applicable shared or instance-specific Ruleset authority.

The continuity loop is therefore:

1. read relevant current authoritative Dataset state,
2. establish applicable Ruleset semantics,
3. reason with current input,
4. produce any proposed state transition,
5. accept or reject that proposal according to the derived application's governed transition semantics,
6. persist an accepted resulting Dataset state,
7. allow a later session to repeat the process.

## Durable State, Not Conversational Memory

The Dataset is the sole authority for current committed application state.

A chat transcript may be useful evidence or input in a particular application, but conversational history itself is transient unless application semantics explicitly accept information from it into the Dataset.

This separation allows application continuity even when:

- a chat session ends,
- a context window is replaced,
- a model invocation is restarted,
- a different Agent instance continues the work,
- transient reasoning state is lost,
- only a bounded representation of prior work is loaded.

## Sufficient State and Governance

Continuity does not require replaying every prior token or reconstructing every intermediate inference.

It requires enough current Dataset state and applicable Ruleset semantics to preserve the application meaning necessary for the next operation.

The derived application defines what "enough" means for its domain.

A bounded representation must preserve the required semantics and remain traceable to the authoritative Ruleset and Dataset sources it represents.


Where multiple Ruleset states may coexist, continuity also requires enough Ruleset identity or traceability to determine which governing semantics apply to the selected Dataset state.

## Missing Authority

When required current state or governing semantics are unavailable, continuity is underspecified for the affected operation.

A later Agent session must not compensate by inventing committed state, transition rules, or application meaning.

The derived application may define recovery, refusal, degraded operation, or other explicit behavior for missing-authority conditions.

## SCF Contract Foundation and SCF

SCF Contract Foundation provides reusable Dataset-side foundational contracts for authority, persistence, and continuity.

SCF — Session Continuity Framework — is the broader Dataset-side realization framework through which those concerns may be realized for ADR-derived applications.

Derived applications specialize these foundations with their own state model and continuity requirements.

## CGI and Continuity

CGI provides the Ruleset-side realization foundation for continuity.

Its concern is ensuring that a later Agent session reasons under the application semantics required to interpret current state and govern further transitions.

Derived applications specialize CGI with their own context, governance, and interpretation rules.

## Agent Replacement

Continuity is an application property rather than the persistence of one particular model instance.

A later session may use another Agent instance, model invocation, or compatible reasoning engine if the derived application's semantics permit it.


The same Agent implementation may also serve multiple independent application instances across different sessions or operations. That reuse does not carry committed state between instances; each instance derives continuity from its own Dataset authority and applicable Ruleset.

The continuing Agent operates from current Dataset state under the applicable Ruleset rather than inheriting authority merely from being the same conversational process.

## Failure and Recovery

Continuity may be disrupted when required state or governing semantics are:

- missing,
- stale,
- invalid,
- conflicting,
- insufficient for the intended operation.

ADR identifies these as consequential conditions but does not impose universal recovery behavior.

Each derived application defines the success, failure, fallback, or recovery semantics appropriate to its domain.


Ruleset evolution can also disrupt continuity when a new governing state changes the interpretation or validity of existing Dataset state. When consequential, the derived application defines compatibility, migration, acceptance, refusal, or recovery semantics before the instance continues under the changed Ruleset.

## Drift and Hallucination

ADR's architecture is intended to reduce uncontrolled drift by making durable application state and governing semantics explicit rather than relying on transient model memory or inference alone.

This structure does not guarantee that an Agent will never hallucinate or reason incorrectly.

Derived applications may define their own validation, review, or conformance measures where those behaviors materially affect the application.

## Derived-Application Responsibility

ADR defines continuity as the relationship among authoritative persistent Dataset state, applicable Ruleset semantics, transient Agent reasoning, and governed transition acceptance across session boundaries.

SCF Contract Foundation, SCF, and CGI provide reusable foundations for realizing that relationship.

Each ADR-derived application defines the concrete state, governance, transition, acceptance, failure, and recovery semantics that make continuity meaningful in its domain.
