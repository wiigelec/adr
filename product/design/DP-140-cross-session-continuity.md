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

Continuity is grounded in persistent Dataset state interpreted under the applicable Ruleset.

It does not require the prior chat transcript to function as the application's authoritative memory.

## Continuity Model

A later Agent session can continue prior application work when it can obtain:

- applicable Ruleset semantics,
- relevant current Dataset state,
- any new user input or other application-authorized information needed for the current operation.

The Agent reasons from that governed condition and may participate in a further valid state transition.

The continuity loop is therefore:

1. read relevant current Dataset state,
2. establish applicable Ruleset semantics,
3. reason with current input,
4. perform any valid governed transition,
5. persist the resulting Dataset state,
6. allow a later session to repeat the process.

## Durable State, Not Conversational Memory

The Dataset is the durable representation of current application state.

A chat transcript may be useful evidence or input in a particular application, but ADR does not require conversational history itself to be the state authority.

This separation allows application continuity even when:

- a chat session ends,
- a context window is replaced,
- a model invocation is restarted,
- a different Agent instance continues the work,
- only a bounded representation of prior work is loaded.

## Sufficient State and Governance

Continuity does not require replaying every prior token or reconstructing every intermediate inference.

It requires enough current Dataset state and applicable Ruleset semantics to preserve the application meaning necessary for the next operation.

The derived application defines what "enough" means for its domain.

## SCF and Continuity

SCF provides the Dataset-side foundation for continuity.

Its concern is maintaining persistent state and the contracts necessary for that state to remain meaningful across Agent sessions.

Derived applications specialize SCF with their own state model and continuity requirements.

## CGI and Continuity

CGI provides the Ruleset-side foundation for continuity.

Its concern is ensuring that a later Agent session reasons under the application semantics required to interpret current state and govern further transitions.

Derived applications specialize CGI with their own context, governance, and interpretation rules.

## Agent Replacement

Continuity is an application property rather than the persistence of one particular model instance.

A later session may use another Agent instance, model invocation, or compatible reasoning engine if the derived application's semantics permit it.

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

## Drift and Hallucination

ADR's architecture is intended to reduce uncontrolled drift by making durable application state and governing semantics explicit rather than relying on transient model memory or inference alone.

This structure does not guarantee that an Agent will never hallucinate or reason incorrectly.

Derived applications may define their own validation, review, or conformance measures where those behaviors materially affect the application.

## Derived-Application Responsibility

ADR defines continuity as the relationship among persistent Dataset state, applicable Ruleset semantics, and Agent reasoning across session boundaries.

SCF and CGI provide reusable foundations for realizing that relationship.

Each ADR-derived application defines the concrete state, governance, transition, failure, and recovery semantics that make continuity meaningful in its domain.
