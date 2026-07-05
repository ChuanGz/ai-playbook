# Tools, MCP, Memory, and Orchestration

| Learning metadata | Value |
|---|---|
| Career level | L3 Senior |
| Topics | MCP, orchestration |
| Purpose | Connect models to tools with bounded authority |
| Importance | Critical |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | AI engineers, platform engineers, architects, and security reviewers |
| Decision supported | How a model may use capabilities, state, workflows, delegation, and MCP boundaries |
| Applies when | A system reads live state, writes memory, performs effects, or coordinates multiple steps |
| Does not apply when | A direct deterministic operation or read-only model response satisfies the outcome |
| Expected output | Typed capability, authority, state, orchestration, and termination contracts |
| Evidence basis | Repository runtime controls and current [MCP specification reference](../references/README.md#protocols-and-observability) |
| Last reviewed | 2026-07-04 |

Use this reference when a model can access external capabilities, persist information, execute multiple steps, or delegate work. The design goal is bounded authority and recoverable execution, not maximum autonomy.

## Choose the execution model

| Model | Use when | Do not escalate when |
|---|---|---|
| Direct function call | One deterministic capability satisfies the request | A model is unnecessary for argument selection |
| Model-selected tool | Natural-language intent must map to one bounded capability | A fixed UI or rule can select the action safely |
| Deterministic workflow | Steps, dependencies, retries, and approvals are known | Replanning is not required |
| Single agent | Runtime interpretation or replanning is necessary within one authority boundary | A workflow can represent all valid paths |
| Multiple agents | Roles require isolated permissions, context, budgets, or parallel ownership | Labels only divide one prompt or add coordination theater |

Require measured benefit before moving downward. Compare quality, latency, cost, failure recovery, and operator burden against the simpler design.

## Tool contract

Every tool descriptor must define:

- stable name, version, purpose, and accountable owner;
- typed input and output schemas with size limits;
- required identity, permissions, data classes, and credential scope;
- whether the operation is read-only, reversible, compensatable, or irreversible;
- timeout, cancellation, idempotency, retry, and reconciliation behavior;
- rate, concurrency, cost, and resource limits;
- error taxonomy and safe user-visible messages;
- audit receipt fields and sensitive-data handling;
- deprecation and compatibility policy.

Tool descriptions help a model select a capability; they do not authorize use. Validate arguments and policy after selection and before credential issuance.

## Invocation sequence

1. Resolve the exact tool version and schema.
2. Validate arguments independently of the model.
3. Evaluate actor, tenant, resource, purpose, policy, budget, and side-effect class.
4. Bind human approval to an immutable action digest when required.
5. Issue a short-lived, least-privilege credential after authorization.
6. Invoke with deadline, cancellation, correlation, and idempotency metadata.
7. Validate the result and persist an effect receipt.
8. Reconcile ambiguous outcomes before any retry.
9. Redact telemetry and release credentials.

An approval expires when material arguments, actor, target, amount, policy, or tool version changes.

## MCP boundary

MCP standardizes context and capability exchange; it does not establish trust. Treat every client, server, transport, descriptor, resource, prompt, and tool result as a separate boundary.

### Client responsibilities

- connect only to configured server identities and supported protocol versions;
- present server capabilities without implying they are trusted or authorized;
- enforce local policy before exposing content or invoking a tool;
- obtain user consent for material data disclosure and side effects;
- isolate server-provided text from system instructions;
- bound response size, redirect behavior, time, and resource use.

### Server responsibilities

- authenticate callers where the transport and deployment require it;
- authorize every protected resource and tool independently;
- validate inputs and avoid shell, path, query, or template injection;
- keep credentials server-side and scope downstream access;
- return typed errors without secrets or internal stack data;
- advertise capability and protocol versions accurately;
- record attributable, privacy-aware audit events.

### Transport considerations

Local process transport inherits the security of executable discovery, package installation, environment variables, working directories, and operating-system permissions. Remote transport additionally requires endpoint identity, secure transport, authorization, origin and redirect controls, and denial-of-service protection.

Do not assume that local means trusted or that protocol compatibility means server safety.

## Memory policy

Separate:

- **working state:** temporary data needed by the current run;
- **episodic records:** attributable outcomes from prior runs;
- **semantic knowledge:** governed facts or source-derived representations;
- **procedural memory:** approved instructions or reusable workflows.

A memory write is an explicit state-changing operation. Record tenant, actor, source, purpose, sensitivity, confidence where relevant, schema version, retention, expiry, and supersession relationship.

Reject hidden reasoning, unverified model claims, secrets, and cross-tenant data. Require review or approval for procedural instructions and high-impact facts. Support correction, tombstone, deletion propagation, and conflict handling.

## Planning and orchestration

A plan is a versioned dependency graph with step goals, inputs, success criteria, permissions, budgets, deadlines, retry classes, approval classes, and compensation where possible.

The orchestrator must:

- persist accepted run state before dispatch;
- schedule only dependency-ready and authorized steps;
- use leases or fencing to prevent stale workers committing results;
- checkpoint at recoverable boundaries;
- bound fan-out, concurrency, delegation depth, total steps, and total spend;
- suspend durably for approval rather than hold an in-memory process;
- distinguish cancellation, failure, partial completion, and successful completion;
- reconcile external state before retrying an ambiguous effect.

Replanning creates a new plan version. It cannot expand authority, budget, or side-effect scope without a new policy decision and approval where required.

## Delegation and multiple agents

Delegate a scoped subgoal, immutable context references, explicit capabilities, budget, deadline, output schema, and return channel. Child agents must not inherit every parent credential or mutable prompt.

Define:

- maximum depth, breadth, duration, and aggregate budget;
- isolation of state, memory, tools, and telemetry;
- join behavior for missing, conflicting, or late results;
- which actor owns the final decision and side effect;
- cancellation propagation and orphan cleanup;
- conflict resolution that does not rely on agents voting themselves more authority.

## Termination controls

A run terminates when it succeeds, reaches an unrecoverable failure, is denied, is cancelled, exceeds time or budget, reaches a step or delegation limit, or cannot improve after a bounded replan count.

Termination must release leases and credentials, persist final state, reconcile pending effects, mark partial artifacts, emit a terminal event, and identify any required human follow-up.

## Review checklist

- [ ] The design uses the simplest execution model that meets the outcome.
- [ ] Tool schemas, authority, effects, retry, reconciliation, and audit receipts are explicit.
- [ ] MCP compatibility is separated from trust and authorization.
- [ ] Memory writes are governed state changes with correction and deletion behavior.
- [ ] Plans and replans cannot silently expand permissions or budgets.
- [ ] Delegation isolates context, capability, state, and total resource use.
- [ ] Every loop has a measurable termination condition.
- [ ] Ambiguous effects are reconciled before retry.
- [ ] Cancellation and terminal failure leave recoverable, auditable state.

## Related references

Use the current [Model Context Protocol specification](../references/README.md#protocols-and-observability) for wire and protocol behavior. The authorization and runtime controls in this document remain the consuming system's responsibility.
