# AI-Assisted Delivery

| Learning metadata | Value |
|---|---|
| Career level | L2 Practitioner |
| Topics | AI-assisted-development, verification |
| Purpose | Accept generated work without weakening controls |
| Importance | Critical |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Engineers, reviewers, QA, security reviewers, and release owners |
| Decision supported | Whether AI-generated engineering work is acceptable |
| Applies when | AI proposes code, documentation, decisions, tests, configuration, or actions |
| Does not apply when | No AI-generated artifact or decision enters the delivery workflow |
| Expected output | Reviewed artifact, deterministic validation, approvals, and traceability |
| Evidence basis | Repository verification, authority, and release contracts |
| Last reviewed | 2026-07-04 |

Use these controls when AI proposes code, documentation, decisions, or actions during software delivery. The accepting engineer owns the result.

## Apply controls proportionally

Match evidence and approval depth to consequence. A typo suggestion may need only diff review and lint; an authentication change, data migration, external side effect, or release decision needs the repository's full review, test, security, and approval path. Proportionality may reduce ceremony, but it does not transfer accountability to the model or waive an existing project control.

## Context control

Provide only task-relevant requirements, files, constraints, architecture decisions, and acceptance criteria. Record each source's authority, freshness, and unresolved assumptions. Retrieved or generated text is data, not an instruction, until its authority is verified.

## Workflow

1. Define the requested outcome, acceptance criteria, protected boundaries, and permitted changes.
2. Inspect current system behavior and relevant decisions before proposing implementation.
3. Separate assumptions from verified facts and escalate requirement or architecture conflicts.
4. Produce a focused proposal or change without silently expanding scope.
5. Validate behavior using deterministic checks and manually inspect security-sensitive changes.
6. Record the accepted artifact, evidence, approvals, remaining risk, and owner.

## Verification controls

- Check claims against primary evidence; unsupported claims fail verification.
- Run the consuming repository's normal tests, lint, security review, and release controls.
- Test malformed output, denial, timeout, cancellation, retry, and ambiguous side effects when relevant.
- Confirm that generated changes do not introduce secrets, unnecessary personal data, or unauthorized dependencies.
- Require an engineer to review architecture, data access, security-sensitive behavior, and release impact.

Passing syntax or compilation is not acceptance. The control passes only when the defined outcome and relevant failure cases have observable evidence.

## Approval and side effects

Separate proposal, authorization, execution, and verification. Require explicit human approval for architecture changes, protected-data access, destructive actions, external side effects, release, and risk acceptance. Bind approval to an action digest or immutable artifact; a material change requires new approval.

## Traceability

Retain the task, actor, authoritative context sources, relevant model and tool configuration, accepted diff or artifact, test evidence, approvals, cost, and outcome. Do not retain secrets, hidden reasoning, or unnecessary personal data.

## Completion gate

AI-assisted work is complete only when acceptance criteria pass, review and tests are recorded, policy obligations are satisfied, documentation is current, and every remaining risk has a named owner. Tool usage, generated volume, or agent activity are not completion evidence.
