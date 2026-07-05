# Observability and Operations

| Learning metadata | Value |
|---|---|
| Career level | L3 Senior |
| Topics | observability, operations |
| Purpose | Detect, diagnose, and recover AI failures |
| Importance | Critical |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Operators, SREs, platform engineers, AI engineers, and incident owners |
| Decision supported | Whether an AI-enabled workflow is observable, recoverable, and operable within bounds |
| Applies when | A workflow has runtime dependencies, cost, user impact, or consequential failures |
| Does not apply when | Telemetry is treated as authoritative state or requires collecting unjustified sensitive data |
| Expected output | Owned signals, objectives, degradation, recovery, cost, and incident controls |
| Evidence basis | Repository runtime and release contracts; [OpenTelemetry reference](../references/README.md#protocols-and-observability) |
| Last reviewed | 2026-07-04 |

Use this reference to operate AI-enabled workflows without confusing telemetry with authoritative state or collecting more sensitive content than the operation requires.

## Operational signals

Correlate signals across request, run, step, model, retrieval, tool, policy, approval, memory, artifact, and outcome boundaries.

| Signal area | Minimum useful evidence |
|---|---|
| Outcome | Accepted, rejected, corrected, escalated, abandoned, and unresolved tasks |
| Quality | Evaluation result, unsupported claim, refusal, fallback, and human override |
| Retrieval | Query class, source revisions, selected evidence, empty result, freshness, and access denial |
| Model | Provider and model version, latency, usage, structured-output failure, refusal, retry, and fallback |
| Tool | Tool version, action digest, authorization, duration, receipt, error class, and reconciliation |
| Workflow | Plan version, state transitions, queue time, lease, retry, checkpoint, cancellation, and terminal state |
| Governance | Policy version, allow, deny, approval request, decision, exception, and budget result |
| Resources | Cost, tokens, requests, steps, concurrency, storage, and operator intervention |

Reference sensitive payloads by protected artifact identifier where possible. Sampling must not remove audit evidence required for consequential actions.

## Service objectives

Define objectives from user impact: task completion, correctness, freshness, safe refusal, end-to-end latency, recovery, and bounded cost. Provider uptime or model-call latency alone does not describe workflow reliability.

Set thresholds from the consuming system's requirements and baseline. This playbook does not supply universal percentages or latency targets.

## Degradation and fallback

For model, retrieval, tool, policy, queue, storage, or telemetry degradation, choose explicitly among retry, alternate provider, reduced capability, cached result, deterministic fallback, human queue, read-only mode, or fail closed.

A fallback must preserve data and authorization constraints. A cheaper or available model is not a valid fallback if it cannot satisfy the output or safety contract.

## Retry and recovery

Retry only classified transient failures within deadline and budget. Do not retry denial, invalid unchanged input, unsupported capability, exhausted approval, or ambiguous external effect. Recover workflows from durable state, fence stale workers, and reconcile effects before resuming.

## Cost controls

Apply per-request and aggregate budgets for model use, retrieval, tools, steps, delegation, duration, and operator review. Alert on outcome-adjusted cost and abnormal growth, not token count alone. A run that stays under budget but fails the task is not efficient.

## Incident response

An AI incident may involve harmful output, data leakage, unauthorized action, poisoned knowledge, evaluation escape, runaway cost, provider change, or inability to explain an effect.

1. Contain access, tools, memory writes, deployment, or affected traffic.
2. Preserve versions, manifests, receipts, policy decisions, and relevant protected evidence.
3. Identify affected users, data, actions, and derivative stores.
4. Revoke credentials and approvals; correct or tombstone poisoned state.
5. Recover through a tested fallback or rollback.
6. Add the failure to evaluation and update the responsible contract.

## Operational readiness gate

- [ ] User-impact objectives and owned thresholds exist.
- [ ] Terminal outcomes, failures, approvals, effects, quality, and cost are correlated.
- [ ] Sensitive telemetry is minimized, redacted, retained, and access-controlled.
- [ ] Dependency degradation has a tested, policy-preserving response.
- [ ] Retries, reconciliation, recovery, cancellation, and rollback are tested.
- [ ] Budgets terminate runaway execution and expose operator burden.
- [ ] Incident containment, evidence, revocation, correction, and communication are owned.

## Related references

Use the [OpenTelemetry reference](../references/README.md#protocols-and-observability) when adopting shared semantic conventions. Pin the convention version used by the implementation; evolving conventions are not operational state.
