# ADR Candidate Functional Set

## Status

Candidate functional-set direction. Directional and non-normative.

## Metadata

```json
{
  "artifact_id": "adr.functional-set",
  "artifact_type": "functional-set",
  "document_slug": "adr-functional-set",
  "filename_stem": "adr-functional-set",
  "root_path": "product/docs/overview/",
  "title": "ADR Candidate Functional Set",
  "product_id": "adr",
  "authority_category": "directional",
  "lifecycle_status": "candidate",
  "governing_issue": "#5",
  "required_content_areas": {
    "capability_boundary": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ],
    "included_intent": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ],
    "exclusions": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ],
    "dependencies": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ],
    "integration_foundation": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ],
    "end_to_end_usability": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ],
    "analyzed_alternatives": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ],
    "decomposition_handoff": [
      "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md"
    ]
  },
  "controlling_documents": [
    "product/docs/overview/ADR-ANALYSIS.md"
  ],
  "predecessor_documents": [
    "product/docs/overview/ADR-ANALYSIS.md"
  ],
  "evidence": [
    "product/docs/overview/adr-analysis/01-foundational-analysis.md",
    "product/docs/overview/ADR-WHITEBOARD.md",
    "product/docs/overview/adr-whiteboard/01-initial-direction.md"
  ],
  "subordinate_chunks": [
    {
      "order": 1,
      "path": "product/docs/overview/adr-functional-set/01-governed-agent-initialization-and-continuity.md",
      "title": "Governed agent initialization and continuity",
      "coverage": [
        "capability_boundary",
        "included_intent",
        "exclusions",
        "dependencies",
        "integration_foundation",
        "end_to_end_usability",
        "analyzed_alternatives",
        "decomposition_handoff"
      ]
    }
  ],
  "successor_action": "Review the exact candidate boundary for explicit user approval. Do not begin decomposition while lifecycle status remains candidate.",
  "schema_version": "1"
}
```

## Overview

This candidate functional set records the analysis-favored ADR FS0/core boundary: governed agent initialization and continuity. It remains directional and non-normative and does not establish exact product behavior, interfaces, schemas, implementation architecture, or release readiness.

## Chunk index

- [Governed agent initialization and continuity](adr-functional-set/01-governed-agent-initialization-and-continuity.md)

## Relationships

This candidate succeeds the [ADR Product Analysis](./ADR-ANALYSIS.md) and preserves traceability to its declared whiteboard evidence.

## Next authorized action

Review this exact candidate boundary. Explicit user approval is required before lifecycle status may become `approved` or decomposition handoff may be declared ready.

## Discoverability

- [Product overview index](./README.md)
