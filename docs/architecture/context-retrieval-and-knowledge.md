# Context, Retrieval, and Knowledge

Use this reference when a model needs information beyond the current request. It separates ephemeral context assembly from governed knowledge storage and defines when retrieval-augmented generation is justified.

## Decide whether retrieval is needed

Prefer a deterministic query or direct document link when it can satisfy the outcome. Add retrieval plus generation when the task requires interpreting multiple approved sources, natural-language synthesis, or cited answers over changing knowledge.

Do not use RAG to compensate for unclear source ownership, missing access control, poor data quality, or an undefined acceptance test. Retrieval makes those failures harder to see; it does not repair them.

## Context contract

Every model call should be able to produce a context manifest containing:

- request, tenant, actor, purpose, and policy version;
- source identifier, revision, capture time, authority, and sensitivity;
- retrieval query, filters, ranking method, and score where meaningful;
- included chunks and reasons for exclusion or truncation;
- token or size budget and reduction steps;
- prompt, model, retrieval, embedding, and schema versions.

Context is an ephemeral projection. Durable source content and approved memory remain authoritative.

## Knowledge lifecycle

### 1. Approve sources

Record owner, purpose, authority, license or permission, data classification, audience, update path, retention, and deletion obligation. A URL being reachable does not grant permission to ingest or redistribute it.

### 2. Capture and parse

Preserve source identity and revision before transformation. Record parser version and failures. Reject or quarantine content when structural loss would make citations misleading, such as dropped table headers or detached footnotes.

### 3. Segment

Choose boundaries that preserve the unit needed for a decision: section, procedure, record, message, or code symbol. Fixed-size chunks are acceptable only when evaluation shows they preserve enough meaning.

Store parent-child relationships so a retrieved fragment can be inspected in its surrounding context. Avoid overlap that inflates duplicate evidence without improving recall.

### 4. Enrich metadata

Keep metadata required for filtering and explanation: source, revision, owner, time, language, content type, sensitivity, access scope, validity period, and stable location. Do not generate authoritative metadata from model inference alone.

### 5. Index

Version the transformation, embedding, and index schema. Make reindexing repeatable from approved source material. An index is derived state and must not become the only copy of knowledge.

### 6. Retrieve and rerank

Apply authorization filters before content reaches a model. Retrieve enough candidates to preserve recall, then rerank and deduplicate within a bounded latency and cost budget. Record why the final evidence set was selected.

### 7. Generate and cite

Require the answer contract to distinguish sourced claims, inference, uncertainty, and refusal. Citations must resolve to the supporting passage available to the authorized user, not merely a document title.

### 8. Refresh and delete

Define how source change, expiry, permission change, correction, and deletion propagate through parsed artifacts, indexes, caches, saved answers, and evaluation sets. Measure deletion completion rather than assuming an index rebuild removed every derivative.

## Retrieval choices

| Method | Prefer when | Limitation to test |
|---|---|---|
| Deterministic database query | Schema and predicates represent the question | Natural-language ambiguity may not map cleanly to fields |
| Lexical search | Exact terms, identifiers, rare names, or legal wording matter | Synonyms and conceptual matches may be missed |
| Embedding similarity | Semantic paraphrase and concept matching matter | Scores are model-dependent and can hide exact constraints |
| Hybrid retrieval | Both exact and semantic matches affect the answer | Fusion weights add tuning and explanation cost |
| Graph traversal | Relationships and bounded hops are the decision unit | Graph construction and entity resolution can introduce false edges |
| Reranking | Initial retrieval has acceptable recall but weak ordering | Added model latency, cost, and possible ranking drift |

Choose from evaluation evidence. A vector database is not a prerequisite for RAG, and cosine similarity is not a quality metric for the final answer.

## Access-control model

Enforce the same decision across:

- source capture and transformation;
- metadata and index records;
- retrieval filters and reranking inputs;
- model context and generated output;
- citations, caches, traces, saved answers, and exports;
- deletion, retention, and subject-access workflows.

Fail closed when identity, tenant, policy, or classification is missing. Never ask a model to decide whether a retrieved passage is authorized.

## Evaluation gates

Build an evaluation set from real question types, difficult source boundaries, permission differences, stale content, conflicting sources, and answerable versus unanswerable cases.

| Gate | Pass evidence |
|---|---|
| Retrieval relevance | Supporting evidence appears within the reviewed candidate set |
| Retrieval coverage | Required evidence is not systematically missed across question classes |
| Answer support | Material claims are entailed by cited passages or labeled as inference |
| Citation accuracy | Each citation resolves to the exact supporting context |
| Freshness | Expired or superseded sources do not win retrieval after the defined propagation window |
| Access isolation | Cross-user and cross-tenant denial tests prevent retrieval and derivative leakage |
| Abstention | Unanswerable or insufficiently supported questions produce the defined refusal or escalation |
| Robustness | Malicious or irrelevant retrieved instructions cannot authorize actions or override system policy |

Set thresholds per consequence and compare against a simpler baseline. Reevaluate when sources, parsers, chunking, metadata, embeddings, ranking, prompts, models, or policy change materially.

## Failure handling

- Return a bounded no-evidence result when retrieval fails; do not let the model fill the gap silently.
- Surface conflicting authoritative sources and route ownership disputes to a human.
- Quarantine malformed or suspicious sources before indexing.
- Preserve the last known valid index only when policy and freshness constraints permit it.
- Make partial deletion, stale cache, citation failure, and index drift observable.

## Review checklist

- [ ] The use case requires retrieval rather than a deterministic query or direct source.
- [ ] Every source has authority, permission, owner, classification, freshness, and deletion rules.
- [ ] Segmentation preserves decision-relevant meaning.
- [ ] Authorization is enforced before model access and across derivatives.
- [ ] The context manifest can explain what was included and why.
- [ ] Evaluation covers relevance, support, citation, freshness, isolation, abstention, and injection.
- [ ] Refresh and deletion have measurable completion behavior.
- [ ] The system fails safely when evidence is absent, stale, conflicting, or unauthorized.

## Related references

Use the [NIST and OWASP references](../references/README.md) for broader risk and LLM application-security context. This document defines repository guidance, not compliance with those frameworks.
