# Example: Approval-Gated MCP Tool

| Field | Value |
|---|---|
| Status | Stable, illustrative |
| Audience | Engineers and security reviewers exposing consequential capabilities through MCP |
| Decision supported | How to separate model selection, authorization, approval, and effect execution |
| Applies when | A model may propose a reversible external side effect |
| Does not apply when | A deterministic UI or direct API can satisfy the task without model selection |
| Expected output | One attributable draft effect or a typed non-effect result |
| Evidence basis | [Tools, MCP, Memory, and Orchestration](../architecture/tools-mcp-and-orchestration.md) |
| Last reviewed | 2026-07-04 |

This illustrative contract shows a consequential tool exposed through MCP. It does not depend on a specific SDK or transport.

## Why this shape

The model may translate natural-language intent into draft arguments, but deterministic controls own validation, authorization, approval, credentials, and execution. Allowing the model to approve or submit was rejected because generated text cannot establish accountable authority.

## Capability

`purchase.create_draft` creates a draft purchase request. It cannot approve or submit the purchase.

## Descriptor

```json
{
  "name": "purchase.create_draft",
  "version": "1.0",
  "side_effect": "reversible_draft",
  "required_permission": "purchase:draft:create",
  "approval_class": "amount_and_supplier",
  "timeout_seconds": 10,
  "idempotency": "required"
}
```

## Invocation controls

1. Validate supplier, currency, amount, lines, tenant, and request version.
2. Authorize the authenticated actor and tenant outside the model.
3. Render the exact draft and action digest for human review.
4. Bind approval to actor, supplier, currency, amount, lines, and digest.
5. Issue a scoped credential and invoke with idempotency key.
6. Return a typed draft identifier and effect receipt.
7. If the response times out, query status by idempotency key before retry.

## Errors

| Code | Meaning | Retry |
|---|---|---|
| `invalid_arguments` | Schema or business validation failed | No, until input changes |
| `denied` | Actor or policy denied the action | No |
| `approval_required` | Exact approval is absent or expired | Resume after approval |
| `dependency_unavailable` | Draft service is temporarily unavailable | Bounded retry |
| `effect_unknown` | Invocation outcome is ambiguous | Reconcile; do not invoke again blindly |

## Failure demonstrated

A timeout can occur after the external system creates the draft. Blind retry may duplicate the effect, so the contract requires an idempotency key and status reconciliation.

## Evidence required

Tests must show denial outside permission scope, approval invalidation after argument changes, credential isolation, bounded retry, timeout reconciliation, and one receipt per accepted effect.

## Decision-change trigger

Review the contract when the tool gains irreversible behavior, higher-value amounts, new data classes, different authentication, remote transport, or a submit capability.

## Pass condition

The model cannot submit a purchase, broaden approval, access credentials, or cause duplicate drafts after timeout. Every accepted effect has an actor, digest, idempotency key, and receipt.
