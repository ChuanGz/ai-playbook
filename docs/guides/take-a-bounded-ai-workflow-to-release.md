# Guide: Take a Bounded AI Workflow to Release Review

| Learning metadata | Value |
|---|---|
| Career level | L3 Senior |
| Topics | AI-delivery, release-engineering |
| Purpose | Take one bounded workflow to release review |
| Importance | Critical |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Cross-functional engineering teams preparing a bounded AI workflow for review |
| Decision supported | Whether to release, revise, narrow, pilot, or stop one workflow |
| Applies when | A team can name the outcome, owner, data boundary, and consequence of failure |
| Does not apply when | The task is still exploratory and has no observable acceptance outcome |
| Expected output | Decision record, contracts, evaluation, risk review, and release evidence |
| Evidence basis | Canonical foundation, lifecycle, architecture, and assurance documents |
| Last reviewed | 2026-07-04 |

This guide helps an experienced team apply the playbook to one AI-enabled workflow. It does not prescribe a vendor or guarantee release approval.

## Prerequisites

- a named user outcome and accountable owner;
- access to the consuming repository's architecture, security, privacy, test, and release processes;
- permission to use the intended data and dependencies;
- a bounded experiment environment with no unapproved external effects.

## 1. Frame the outcome

Write the user, trigger, accepted result, rejected result, protected data, permitted actions, consequence of error, latency and cost constraints, and human escalation path.

Stop if acceptance cannot be observed. A prompt is not a requirement.

## 2. Choose the least complex shape

Use the [system decision guide](../foundations/system-decision-guide.md). Compare deterministic software, model inference, retrieval, tools, workflow, and agent options. Record the decision with the [decision template](../foundations/decision-record-template.md).

Stop if the selected shape wins only because it is fashionable or easier to demonstrate.

## 3. Establish adoption boundaries

Apply [adoption and governance](../lifecycle/adoption-and-governance.md): owner, baseline, target, data boundary, approval points, stop conditions, pilot duration, receiving team, and scale/revise/stop decision.

For a low-risk internal experiment, scale ceremony to consequence but retain outcome, data, failure, and ownership boundaries.

## 4. Define system contracts

Select only the relevant references:

- retrieval or changing knowledge: [context, retrieval, and knowledge](../architecture/context-retrieval-and-knowledge.md);
- tools, MCP, memory, workflow, or delegation: [tools, MCP, memory, and orchestration](../architecture/tools-mcp-and-orchestration.md);
- stateful recoverable agents: [agent runtime](../architecture/agent-runtime.md).

Record schemas, versions, authority, budgets, deadlines, idempotency, refusal, fallback, termination, and deletion behavior before implementation.

## 5. Build the evaluation set first

Use [evaluation and release](../assurance/evaluation-and-release.md). Include representative success, ambiguity, missing evidence, unsafe request, denied action, malformed output, timeout, dependency degradation, and recovery cases.

Set owned thresholds before the release run. Keep severe failures visible rather than averaging them away.

## 6. Implement with delivery controls

Apply [AI-assisted delivery](../lifecycle/ai-assisted-delivery.md) to generated code, configuration, prompts, tests, or documentation. Treat generated work as a proposal and preserve the consuming repository's normal review path.

## 7. Review threats and operations

Use [security and governance](../assurance/security-and-governance.md) to map boundaries, authority, data, dependencies, misuse, and exceptions. Use [observability and operations](../assurance/observability-and-operations.md) to define outcome signals, degradation, recovery, budgets, rollback, and incident ownership.

Stop if the team cannot revoke authority, explain a material effect, or recover from the expected failure modes.

## 8. Run the release review

Present:

- architecture decision and affected contracts;
- evaluation versions, thresholds, results, and failures;
- security, privacy, and operational evidence;
- deployment scope, fallback, rollback, and monitoring;
- known gaps, exception owners, and expiry;
- pilot or release approver and decision.

The decision is release, revise, run a narrower pilot, or stop. “The model looked good” is not a release state.

## Verification

- [ ] A reviewer can trace every material decision to an owner and evidence.
- [ ] A simpler design was considered fairly.
- [ ] Data, authority, effects, cost, and termination are bounded.
- [ ] Evaluation covers success and consequence-relevant failures.
- [ ] Fallback, rollback, incident, correction, and deletion paths are usable.
- [ ] The release record states what remains unknown.

## Failure handling

If a gate fails, do not fill it with generic prose. Reduce scope, collect missing evidence, change the architecture, add a bounded exception, or stop. Record the decision in the consuming project.
