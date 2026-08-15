# ADR Product Decomposition

## Status

Directional product decomposition derived from the approved ADR functional set. Non-normative.

## Metadata

```json
{
  "artifact_id": "adr.decomposition",
  "artifact_type": "product-decomposition",
  "document_slug": "adr-decomposition",
  "filename_stem": "adr-decomposition",
  "root_path": "product/docs/decompositions/",
  "title": "ADR Product Decomposition",
  "product_id": "adr",
  "authority_category": "directional",
  "lifecycle_status": "accepted",
  "governing_issue": "#9",
  "controlling_functional_set": "product/docs/overview/ADR-FUNCTIONAL-SET.md",
  "controlling_documents": ["product/docs/overview/ADR-FUNCTIONAL-SET.md"],
  "predecessor_documents": ["product/docs/overview/ADR-FUNCTIONAL-SET.md"],
  "evidence": ["product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md","product/docs/overview/ADR-ANALYSIS.md","product/docs/overview/ADR-WHITEBOARD.md"],
  "product_area_inventory": [
    {"id":"ADR-PA-CTX","title":"Ruleset context governance","chunk":"product/docs/decompositions/adr-decomposition/01-ruleset-context-governance.md"},
    {"id":"ADR-PA-STATE","title":"Persistent dataset state","chunk":"product/docs/decompositions/adr-decomposition/02-persistent-dataset-state.md"},
    {"id":"ADR-PA-INIT","title":"Agent initialization","chunk":"product/docs/decompositions/adr-decomposition/03-agent-initialization.md"},
    {"id":"ADR-PA-CONT","title":"Cross-session continuity","chunk":"product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"}
  ],
  "required_content_areas": {
    "product_areas": ["product/docs/decompositions/adr-decomposition/01-ruleset-context-governance.md","product/docs/decompositions/adr-decomposition/02-persistent-dataset-state.md","product/docs/decompositions/adr-decomposition/03-agent-initialization.md","product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"],
    "dependencies": ["product/docs/decompositions/adr-decomposition/01-ruleset-context-governance.md","product/docs/decompositions/adr-decomposition/02-persistent-dataset-state.md","product/docs/decompositions/adr-decomposition/03-agent-initialization.md","product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"],
    "exclusions": ["product/docs/decompositions/adr-decomposition/01-ruleset-context-governance.md","product/docs/decompositions/adr-decomposition/02-persistent-dataset-state.md","product/docs/decompositions/adr-decomposition/03-agent-initialization.md","product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"],
    "cross_cutting_concerns": ["product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"],
    "unresolved_decisions": ["product/docs/decompositions/adr-decomposition/01-ruleset-context-governance.md","product/docs/decompositions/adr-decomposition/02-persistent-dataset-state.md","product/docs/decompositions/adr-decomposition/03-agent-initialization.md","product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"],
    "stopping_criteria": ["product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"],
    "planning_handoff": ["product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"],
    "downstream_specification_families": ["product/docs/decompositions/adr-decomposition/01-ruleset-context-governance.md","product/docs/decompositions/adr-decomposition/02-persistent-dataset-state.md","product/docs/decompositions/adr-decomposition/03-agent-initialization.md","product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md"]
  },
  "permitted_chunk_roles": ["product-area"],
  "subordinate_chunks": [
    {"order":1,"path":"product/docs/decompositions/adr-decomposition/01-ruleset-context-governance.md","title":"Ruleset context governance","product_area_id":"ADR-PA-CTX"},
    {"order":2,"path":"product/docs/decompositions/adr-decomposition/02-persistent-dataset-state.md","title":"Persistent dataset state","product_area_id":"ADR-PA-STATE"},
    {"order":3,"path":"product/docs/decompositions/adr-decomposition/03-agent-initialization.md","title":"Agent initialization","product_area_id":"ADR-PA-INIT"},
    {"order":4,"path":"product/docs/decompositions/adr-decomposition/04-cross-session-continuity.md","title":"Cross-session continuity","product_area_id":"ADR-PA-CONT"}
  ],
  "successor_action": "Review and accept this directional decomposition, then begin separately governed normative product-specification work starting with required Level 0 shared semantics and the identified Level 1 product concepts.",
  "schema_version": "1"
}
```

## Decomposition obligations

This decomposition partitions the approved ADR functional-set boundary without changing it. The product areas collectively cover ruleset-defined context, persistent dataset state, initialization of reasoning from both, and preservation of continuity across sessions.

The decomposition remains directional and non-normative. It does not decide exact encodings, schemas, APIs, prompting, retrieval, storage, state-transition mechanics, conformance thresholds, runtime architecture, or release criteria.

## Product-area index

1. [ADR-PA-CTX — Ruleset context governance](adr-decomposition/01-ruleset-context-governance.md)
2. [ADR-PA-STATE — Persistent dataset state](adr-decomposition/02-persistent-dataset-state.md)
3. [ADR-PA-INIT — Agent initialization](adr-decomposition/03-agent-initialization.md)
4. [ADR-PA-CONT — Cross-session continuity](adr-decomposition/04-cross-session-continuity.md)

## Dependency direction

`ADR-PA-CTX` + `ADR-PA-STATE` → `ADR-PA-INIT` → `ADR-PA-CONT`.

Shared product-wide interpretation, identity, authority, and lifecycle semantics that are necessary across these areas belong in future Level 0 product specifications rather than being duplicated in individual areas.

## Cross-cutting concerns

SCF and CGI remain cross-cutting perspectives over the interaction and philosophy of the decomposed areas. This decomposition does not promote either into an independently governed specification family.

Drift/hallucination reduction remains a product motivation and later conformance concern, not a decomposition-level measurable requirement.

## Unresolved decisions

Exact ruleset structure, dataset semantics, state mutation rules, context construction, bounded projection strategy, agent invocation semantics, continuity recovery behavior, conformance measures, and whether SCF/CGI warrant independent normative artifacts remain unresolved.

## Stopping criteria

Decomposition is complete when the approved functional-set boundary is covered by stable coherent product areas, dependency direction is explicit, unresolved semantics are visible, and downstream normative specification families can be identified without selecting implementation architecture or defining exact behavior.

## Planning handoff

The next lifecycle stage is separately governed product-specification work. Normative product specifications must be accepted before any implementation plan is accepted.

## Next authorized action

Review this decomposition as the directional basis for later product specifications. Do not create specifications or implementation plans under Issue #9.
