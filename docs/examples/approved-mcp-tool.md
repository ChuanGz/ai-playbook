# Example: Approval-Gated MCP Tool

This illustrative contract shows a consequential tool exposed through MCP. It does not depend on a specific SDK or transport.

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

## Pass condition

The model cannot submit a purchase, broaden approval, access credentials, or cause duplicate drafts after timeout. Every accepted effect has an actor, digest, idempotency key, and receipt.
