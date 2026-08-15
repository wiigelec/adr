# Initial ADR direction

## Collected input

The following direction is preserved from the user-supplied material that initialized GitHub Issue #1. It is recorded as collection evidence and is not converted here into requirements or normative semantics.

ADR is a foundational specification set that AI-driven applications are built on. It describes three components and their relationships:

1. AI agent — reasoning engine
2. Dataset — session continuity and state
3. Ruleset — agent context

ADR also has two perspectives that describe interactions among the three components and the underlying architectural philosophy:

- SCF — Session Continuity Framework / SCF Contract Foundations
- CGI — Context Governance Infrastructure

ADR is primarily a specification basis with no runtime. Applications are derived from ADR specifications and philosophy but are not dependent on ADR to run. ADR describes a functional specification that a compliant derived application must follow.

The primary driver of ADR is to minimize AI-agent drift and hallucination and provide state-driven data for session-to-session initialization and continuity. Derived applications are context-specific and long-data-driven; a single AI chat session is insufficient for processing the amount, type, and top-to-bottom detail of derived-application data.

ADR provides the scaffolding while a derived compliant application provides the ruleset and dataset implementation details that define the application AI-agent context and data-driven state mechanism.

## Provenance

This material was supplied by wiigelec in GitHub Issue #1, `initialize whiteboard`, as the initial ADR product-direction input. Issue #1 is the governing issue for this collection-stage artifact. Repository initialization evidence is recorded in `repo/initializer/handoff.json`.

## Unresolved intent

No additional unresolved product decisions were explicitly supplied with the initial direction. Any ambiguity in the collected statements remains unresolved at the whiteboard stage and shall not be inferred, reconciled, or promoted to product authority during this bounded work.
