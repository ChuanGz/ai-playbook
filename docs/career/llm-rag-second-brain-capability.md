# LLM, RAG, and Second-Brain Capability

Use this evidence checklist to assess demonstrated capability. It is not a self-attestation based on reading, setup completion, or tool usage.

## Evidence levels

| Result | Meaning |
|---|---|
| Not demonstrated | No reviewable artifact or only a tutorial copy exists |
| Demonstrated | A bounded artifact works and the engineer can explain decisions and limits |
| Sustained | Evidence covers multiple sources or contexts, maintenance, failures, and measurable outcomes |

## LLM engineering

- [ ] **Behavior contract:** define input, context, output schema, refusal, and failure behavior. Pass when tests exercise normal, ambiguous, unsafe, and malformed cases.
- [ ] **Model limits:** explain probabilistic output, hallucination, context limits, and why generated confidence is not evidence. Pass when the design includes verification or safe abstention.
- [ ] **Traceability:** record relevant prompt, model, configuration, source, and output versions. Pass when a result can be reproduced or its drift explained.
- [ ] **Evaluation:** create representative cases, rubric or deterministic checks, and acceptance thresholds. Pass when results support a release, revise, or stop decision.
- [ ] **Human control:** place approval and escalation according to consequence. Pass when denied and escalated paths are tested.

## RAG and retrieval

- [ ] **Source governance:** record authority, permission, revision, sensitivity, freshness, retention, and deletion behavior. Pass when every indexed source has an accountable lifecycle.
- [ ] **Ingestion design:** preserve raw evidence and choose segmentation that retains decision-relevant meaning. Pass when a citation can resolve to the exact supporting context.
- [ ] **Retrieval choice:** compare deterministic, lexical, semantic, hybrid, or graph retrieval. Pass when the selected method beats a simpler baseline for named question types.
- [ ] **Embedding judgment:** explain what embedding similarity can and cannot establish. Pass when exact constraints and authorization are enforced outside similarity scoring.
- [ ] **Grounded generation:** distinguish sourced claims, inference, uncertainty, and abstention. Pass when material claims are entailed by cited passages.
- [ ] **Retrieval evaluation:** measure relevance, coverage, citation accuracy, freshness, access isolation, and abstention. Pass when failures are observable and trigger corrective action.

## Second-brain engineering

- [ ] **Layered knowledge model:** separate temporary capture, immutable sources, curated notes, maps, and saved queries. Pass when each layer has a clear authority and maintenance rule.
- [ ] **Provenance:** link durable claims to raw sources or exact repository revisions. Pass when a reviewer can inspect support without trusting the generated summary.
- [ ] **Atomic distillation:** create focused concepts and entities without duplicating existing notes. Pass when notes can be reused across more than one query or map.
- [ ] **Navigability:** maintain indexes, maps, and meaningful links. Pass when a new reader can locate source, concept, and related evidence without knowing filenames.
- [ ] **Maintenance:** detect broken links, duplicates, stale sources, conflicts, orphans, and mutable evidence. Pass when a review ends with zero unresolved errors or explicitly owned content decisions.
- [ ] **Compounding use:** save reusable answers and feed corrections back into notes. Pass when later questions reuse prior structure while preserving source verification.

## Minimum demonstration project

Build one wiki using the [second-brain guide](../guides/build-an-llm-wiki-second-brain.md), then present:

1. At least three authorized sources with revisions or capture dates.
2. Source cards, summaries, atomic concepts, entities, and one topic map.
3. One query requiring semantic matching and one requiring exact matching.
4. A grounded answer with citations and a deliberate insufficient-evidence result.
5. A retrieval comparison or failure analysis.
6. A maintenance report covering links, duplicates, provenance, and stale content.
7. A short decision record explaining architecture, trade-offs, security boundaries, and what would justify adding embeddings or a vector store.

The capability is **demonstrated** when every artifact is reviewable and the engineer can explain failures and alternatives. It is **sustained** only after the workflow remains useful and maintainable across multiple source sets or real projects.
