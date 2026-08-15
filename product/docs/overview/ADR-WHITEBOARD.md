# ADR Product Whiteboard

## Status

Active collection-stage product whiteboard. Evidentiary and non-normative.

## Metadata

```json
{
  "artifact_id": "adr.whiteboard",
  "artifact_type": "overview-whiteboard",
  "document_slug": "adr-whiteboard",
  "filename_stem": "adr-whiteboard",
  "root_path": "product/docs/overview/",
  "title": "ADR Product Whiteboard",
  "product_id": "adr",
  "authority_category": "evidentiary",
  "lifecycle_status": "active",
  "governing_issue": "#1",
  "required_content_areas": {
    "collected_input": [
      "product/docs/overview/adr-whiteboard/01-initial-direction.md"
    ],
    "provenance": [
      "product/docs/overview/adr-whiteboard/01-initial-direction.md"
    ],
    "unresolved_intent": [
      "product/docs/overview/adr-whiteboard/01-initial-direction.md"
    ]
  },
  "controlling_documents": [],
  "predecessor_documents": [],
  "evidence": [
    "repo/initializer/handoff.json",
    "README.md"
  ],
  "subordinate_chunks": [
    {
      "order": 1,
      "path": "product/docs/overview/adr-whiteboard/01-initial-direction.md",
      "title": "Initial ADR direction",
      "coverage": [
        "collected_input",
        "provenance",
        "unresolved_intent"
      ]
    }
  ],
  "successor_action": "Retain this whiteboard as collection evidence. Analysis requires separately governed successor authorization after this bounded whiteboard-initialization issue is completed.",
  "schema_version": "1"
}
```

## Overview

This composite document records the initial user-supplied ADR product direction before interpretation. It is collection evidence only and does not establish product requirements, approved functional direction, decomposition, specifications, implementation planning, or implementation semantics.

## Chunk index

- [Initial ADR direction](adr-whiteboard/01-initial-direction.md)

## Relationships

This whiteboard bootstraps from governing Issue #1 and repository initialization evidence. It intentionally declares no controlling or predecessor development documents.

## Next authorized action

Complete and review the bounded whiteboard-initialization work authorized by Issue #1. Do not advance to analysis or any later lifecycle stage under this issue.

## Discoverability

- [Product overview index](./README.md)
