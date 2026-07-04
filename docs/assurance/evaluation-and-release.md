# Evaluation and Release

| Field | Value |
|---|---|
| Status | Stable |
| Audience | AI engineers, QA, reviewers, risk owners, and release owners |
| Decision supported | Whether an AI-enabled change has enough evidence to release |
| Applies when | A material model, retrieval, tool, workflow, policy, or user-impact change is proposed |
| Does not apply when | A change cannot affect a documented decision contract or runtime behavior |
| Expected output | Versioned evaluation evidence, thresholds, failures, exceptions, and release decision |
| Evidence basis | Repository component, task, workflow, security, regression, and operations contracts |
| Last reviewed | 2026-07-04 |

Use this reference to decide whether an AI-enabled change has enough evidence to proceed. Evaluation must test the accepted task and its failures, not only model output in isolation.

## Evaluation layers

| Layer | Question | Evidence |
|---|---|---|
| Component | Does retrieval, model output, or a tool boundary satisfy its contract? | Labeled cases, schema checks, retrieval measures, tool tests |
| Task | Can a user complete the bounded outcome? | End-to-end success, correction, refusal, and escalation cases |
| Workflow | Do state, approvals, retries, and recovery behave correctly? | Fault injection, replay, cancellation, and side-effect reconciliation |
| Safety and security | Can expected misuse or hostile input escape controls? | Abuse cases, authorization tests, isolation tests, red-team findings |
| Regression | Did a material change degrade accepted behavior? | Versioned baseline comparison with reviewed thresholds |
| Operations | Can the system meet its service and cost constraints under expected conditions? | Load, latency, availability, budget, degradation, and recovery evidence |

## Evaluation-set contract

Record purpose, owner, source, collection method, permission, classification, representativeness, known gaps, labeling process, disagreement handling, version, and retention. Keep release tests separate from exploratory tuning data where practical to reduce overfitting.

Include normal, boundary, ambiguous, unanswerable, unsafe, adversarial, stale, denied, timeout, malformed, and dependency-degraded cases. Weight cases by consequence and expected frequency; do not hide a severe failure inside one average score.

## Measures and judgment

Use deterministic measures where the contract is deterministic. Use human or model-assisted judgment only with a rubric, examples, disagreement process, and periodic calibration. A model judge cannot validate authority, business acceptance, or side effects it cannot observe.

Report distributions and failure classes, not only averages. Set thresholds before the release run and name the owner who may accept an exception.

## Change-triggered evaluation

Rerun affected layers when model, prompt, context policy, source corpus, parser, embedding, retrieval, reranker, tool, protocol, schema, policy, workflow, dependency, or user population changes materially.

Map each change to the contracts it can affect. Avoid both extremes: rerunning everything without reason and testing only the changed file while ignoring downstream behavior.

## Release evidence

A release record identifies:

- change and affected contracts;
- evaluation-set and system versions;
- thresholds, actual results, failures, and accepted exceptions;
- security, privacy, and operational review where applicable;
- approver, deployment boundary, fallback, rollback, and monitoring plan;
- unresolved risk, owner, expiry, and follow-up.

## Release gate

- [ ] Outcome and affected users are explicit.
- [ ] Representative and consequence-weighted cases pass owned thresholds.
- [ ] Severe failures are reported separately from aggregate scores.
- [ ] Authorization, isolation, refusal, and unsafe-input tests pass.
- [ ] Workflow failure, retry, cancellation, and reconciliation are tested where relevant.
- [ ] Latency, cost, rate, and dependency-degradation behavior are acceptable.
- [ ] Known gaps and exceptions have owners and expiry.
- [ ] Fallback, rollback, monitoring, and incident ownership are ready.

A failed gate requires revision, a bounded documented exception by the accountable owner, or a stop decision. Fluency, demonstrations, and prior model reputation cannot substitute for release evidence.
