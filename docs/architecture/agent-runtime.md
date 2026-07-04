# Agent Runtime

This reference defines vendor-neutral boundaries for agents that plan, use models and tools, retain memory, and perform controlled side effects. Model output is an untrusted proposal; durable state and accepted evidence remain authoritative.

## Applicability

Use this complete reference profile for stateful, recoverable, side-effecting, multi-step agents. A read-only or single-turn assistant may implement only the relevant boundaries, provided omitted components are explicitly out of scope and their guarantees are unnecessary. Do not add orchestration, durable memory, or distributed execution merely to resemble this model; each component must answer a demonstrated failure or operating need.

## Component responsibilities

| Component | Owns | Must not own |
|---|---|---|
| Request | Identity, validation, normalization, and constraints | Planning |
| Agent | Versioned definition, capability, budget, and delegation boundary | Workflow scheduling |
| Context | Authorized, relevant, bounded input projection with provenance | Durable knowledge |
| Memory | Governed retrieval and explicit persistence | Prompt rendering |
| Planning | Versioned dependency graph, success criteria, risk, and compensation | Side effects |
| Model | Provider abstraction, routing, inference, and usage record | Business policy |
| Tools | Typed capability descriptors, adapters, credentials, and effect receipts | Retry scheduling |
| Execution | One authorized step, lease, checkpoint, validation, and reconciliation | Cross-run coordination |
| Orchestration | Durable scheduling, dependencies, concurrency, approval suspension, and delegation | Tool implementation |
| Governance | Authorization, policy, budget, approval, and audit obligations | Workflow ownership |
| Observability | Correlated events, logs, traces, metrics, cost, and audit export | Operational truth |

## Required contracts

Every boundary publishes its schema version and supported capabilities. Envelopes carry tenant, actor, run, trace, deadline, idempotency, and configuration-version metadata where applicable. Breaking schema or semantic changes require a new major contract version; consumers reject unsupported versions.

Context is ephemeral and reproducible from a manifest. Memory writes are explicit, attributable, sensitivity-classified, tenant-scoped, and governed by retention. Plans reference capabilities rather than credentials. Tool descriptors declare permissions, side effects, timeout, data classes, idempotency support, and compensation capability.

## Execution model

Persist a run before dispatch. An executor obtains a fenced lease, loads the checkpoint and immutable configuration snapshot, obtains a policy decision, performs one model or tool call through an adapter, validates the result, commits durable state with an outbox event, and releases the lease. Configuration snapshots prevent mid-run drift; outbox delivery keeps state and emitted events consistent.

Child agents receive isolated state, goals, permissions, and budgets. Bound delegation depth, cycles, concurrency, and total resource use.

## Failure handling

| Failure | Required response |
|---|---|
| Invalid input or output | Reject; do not retry unchanged input. |
| Policy denial or expired approval | Fail closed or suspend for a new exact approval. |
| Transient dependency failure | Retry with bounded exponential backoff, jitter, and deadline. |
| Permanent dependency failure | Stop and return an actionable failure. |
| Lost lease or checkpoint conflict | Recover from durable state and fence stale workers. |
| Ambiguous external side effect | Reconcile by idempotency key or status lookup before retry. |
| Unsupported claim or failed evaluation | Reject output or require accountable human review. |
| Exhausted budget, time, or concurrency | Cancel or return a clearly bounded partial result. |

Every terminal failure records its class, component, retryability, evidence, policy and configuration versions, and correlation identifiers. Compensation is explicit and is not assumed to be equivalent to rollback.

## Security controls

- Treat external content as untrusted and preserve provenance through retrieval and context assembly.
- Authorize typed tool calls against allowlists and scoped credentials; model output cannot authorize itself.
- Minimize and classify data across context, models, memory, tools, artifacts, and telemetry.
- Validate, attribute, version, and, where required, approve durable memory writes.
- Protect repeated effects with action digests, idempotency keys, and reconciliation.
- Apply least privilege to agents and delegation.
- Enforce budget, quota, deadline, cancellation, retention, and tenant boundaries.
- Keep audit records append-only and access-controlled; redact or reference sensitive content in telemetry.

## Operability evidence

Trace an accepted outcome to the request, plan version, configuration snapshot, model usage, tool receipts, policy decisions, approvals, checkpoints, failures, cost, and final evidence. Telemetry failure must not corrupt run state. A runtime is not production-ready merely because these contracts are documented; each implementation must prove them under its own load, failure, recovery, security, and operational constraints.

## Related references

Use the [OWASP, MCP, and OpenTelemetry references](../references/README.md#application-and-agent-security) when the implementation introduces LLM-specific threats, MCP boundaries, or shared telemetry conventions. These sources complement rather than validate the runtime design.
