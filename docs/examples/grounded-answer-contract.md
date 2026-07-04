# Example: Grounded Answer Contract

This illustrative contract exposes the decisions required for a read-only RAG answer. It is not a complete application or production architecture.

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

## Pass condition

The example passes only when supported answers cite exact authorized passages, unsupported questions abstain, denied data never reaches model or output, and stale or deleted sources stop appearing within the owned propagation window.
