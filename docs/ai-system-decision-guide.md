# AI System Decision Guide

Use this guide before selecting a model, retrieval system, tool protocol, workflow engine, or agent framework. The goal is to choose the least complex solution that can satisfy the required outcome and failure constraints.

## 1. Define the decision

Record:

- the user or business outcome and who accepts it;
- inputs, outputs, data classification, and permitted side effects;
- quality, latency, cost, availability, and freshness constraints;
- failures that must be prevented, detected, or recoverable;
- deterministic checks and human decisions already available;
- the evidence required before release and the event that triggers review.

If the outcome or acceptance evidence is undefined, technology selection is premature.

## 2. Choose a solution shape

| Shape | Use when | Avoid when | Minimum evidence |
|---|---|---|---|
| Deterministic software | Rules and outputs can be specified and tested directly | The task requires interpretation of genuinely variable language or media | Tests prove the required behavior and failure boundaries |
| Model inference | The output requires bounded interpretation, classification, extraction, transformation, or generation | A deterministic rule can meet the outcome more safely or cheaply | Representative evaluation, schema validation, refusal behavior, and fallback |
| Retrieval plus model | The answer depends on approved, changing, or source-citable knowledge | The required data already fits a deterministic query or the corpus cannot be governed | Retrieval and answer-support evaluation, provenance, access control, freshness, and abstention |
| Model plus tools | The system must read live state or perform a bounded external capability | Read-only model output satisfies the outcome or side effects cannot be authorized and reconciled | Typed schema, authorization, scoped credential, idempotency, timeout, effect receipt, and audit |
| Deterministic workflow | Steps, dependencies, retries, and approvals are known in advance | The path genuinely requires runtime interpretation or replanning | State transitions, retry and compensation policy, approval binding, and recovery tests |
| Agent | The system must select or revise steps under uncertainty within bounded capabilities | A fixed workflow can satisfy the outcome, or budgets and termination cannot be enforced | Goal and capability boundary, evaluation, tool controls, budget, termination, trace, and human escalation |
| Multiple agents | Independent bounded roles must operate concurrently or require distinct permissions or context | Role labels merely split one prompt, or coordination cost has no measured benefit | Isolation, delegation limits, join semantics, conflict handling, total budget, and comparison with a simpler design |

Start at the top of the table and move downward only when evidence shows the simpler shape cannot satisfy the outcome.

## 3. Select a model or provider

Evaluate candidates against the recorded use case, not a general leaderboard:

- capability on representative and adversarial cases;
- structured-output reliability and refusal behavior;
- latency distribution and throughput under the expected workload;
- total operating cost, including retries, retrieval, review, and failure recovery;
- data handling, retention, regional, contractual, and access constraints;
- observability, versioning, rate limits, availability, and degradation behavior;
- substitution cost created by provider-specific prompts, tools, formats, or features.

Provider portability is a tradeoff, not an automatic requirement. Accept coupling when a provider-specific capability creates evidenced value greater than its migration and concentration risk; record the decision and review trigger.

## 4. Define the output contract

For every model boundary, record:

- input schema and allowed context sources;
- output schema, size limits, and validation rules;
- handling for invalid, partial, unsafe, unsupported, or refused output;
- retry eligibility, attempt limit, deadline, and cost budget;
- fallback behavior and the condition requiring human review;
- model, prompt, tool, retrieval, policy, and schema versions needed for traceability.

Repair invalid output only within a bounded attempt and budget. Do not retry policy denial, unsupported capability, or unchanged invalid input as if it were transient failure.

## 5. Record the architecture decision

Use this minimum record:

```markdown
# Decision: <short title>

## Context and outcome
<Who needs what result, under which constraints?>

## Decision drivers
<Quality, risk, data, latency, cost, operability, and ownership forces.>

## Options considered
<Include the simplest deterministic option and credible AI alternatives.>

## Decision
<Selected shape, boundaries, and why it wins under these conditions.>

## Consequences and risks
<Benefits, coupling, new failure modes, operational cost, and residual risks.>

## Validation
<Evaluation set, tests, thresholds, approvals, and operational evidence required.>

## Owner and review trigger
<Accountable owner and changes that require reconsideration.>
```

The decision passes review only when alternatives are credible, thresholds are owned, and validation can falsify the selected approach.

## 6. Continue through the playbook

- Apply [adoption and governance](adoption-and-governance.md) before piloting or scaling.
- Apply [AI-assisted delivery](ai-assisted-delivery.md) to generated engineering artifacts.
- Apply [agent runtime](agent-runtime.md) only when the selected shape requires agent capabilities.

## Boundaries

This guide does not select a vendor, establish organization policy, replace threat modeling, or certify production readiness. The consuming system owns its thresholds, legal and compliance review, implementation evidence, and release decision.
