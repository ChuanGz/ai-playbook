# Example: Grounded Answer Contract

| Learning metadata | Value |
|---|---|
| Career level | L2 Practitioner |
| Topics | RAG, grounding |
| Purpose | Return cited answers with explicit uncertainty |
| Importance | Critical |

| Field | Value |
|---|---|
| Status | Stable, illustrative |
| Audience | Engineers and reviewers designing a read-only grounded-answer capability |
| Decision supported | Which minimum contract makes a cited answer reviewable |
| Applies when | Approved, changing documents must support a natural-language answer |
| Does not apply when | A deterministic query or direct document navigation satisfies the outcome |
| Expected output | Authorized cited answer or explicit abstention |
| Evidence basis | [Context, Retrieval, and Knowledge](../architecture/context-retrieval-and-knowledge.md) |
| Last reviewed | 2026-07-04 |

This illustrative contract exposes the decisions required for a read-only RAG answer. It is not a complete application or production architecture.

## Why this shape

The selected design uses retrieval plus generation because the answer may require synthesis across approved documents while preserving citations. A deterministic database query was rejected for this example because the source material is narrative and the required answer is explanatory. If questions can be mapped reliably to structured fields, the deterministic query becomes preferable.

## Outcome

Answer an authorized user's policy question using only currently approved documents. Return citations or abstain.

## Input

```json
{
  "question": "string, 1..2000 characters",
  "user_id": "authenticated subject",
  "tenant_id": "authorized tenant",
  "purpose": "policy_lookup"
}
```

## Output

```json
{
  "status": "answered | insufficient_evidence | denied | unavailable",
  "answer": "string or null",
  "citations": [
    {
      "source_id": "stable identifier",
      "revision": "source revision",
      "passage_id": "authorized supporting passage"
    }
  ],
  "limitations": ["string"]
}
```

## Controls

- Authorization filters run before retrieval and again before citation rendering.
- The context manifest records source revisions, filters, selected passages, and model configuration.
- Material claims require cited support; inference is labeled.
- Conflicting authoritative documents produce `insufficient_evidence` and escalation.
- Source expiry or permission removal propagates to index, cache, and saved answer.

## Evaluation cases

- answerable question with one authoritative source;
- answer requiring two consistent sources;
- unanswerable question;
- stale and superseded source;
- conflicting sources;
- cross-tenant source;
- retrieved prompt injection;
- retrieval outage.

## Failure demonstrated

Retrieval can return relevant-looking but unauthorized, stale, conflicting, or instruction-bearing content. The answer contract therefore requires authorization before model access, exact supporting citations, and abstention when evidence is insufficient.

## Evidence required

Evaluation must show answer support, citation accuracy, cross-tenant isolation, stale-source removal, injection resistance, and abstention on unanswerable cases. No fictional pass rate is assumed.

## Decision-change trigger

Reconsider this design when the corpus, access model, answer consequence, retrieval method, model, citation requirements, or source freshness obligations change materially.

## Pass condition

The example passes only when supported answers cite exact authorized passages, unsupported questions abstain, denied data never reaches model or output, and stale or deleted sources stop appearing within the owned propagation window.
