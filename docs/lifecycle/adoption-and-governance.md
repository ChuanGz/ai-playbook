# Adoption and Governance

| Learning metadata | Value |
|---|---|
| Career level | L4 Lead |
| Topics | AI-adoption, governance |
| Purpose | Pilot, scale, revise, or stop initiatives |
| Importance | Critical |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Business owners, engineering leaders, architects, and governance reviewers |
| Decision supported | Whether an AI initiative should pilot, scale, revise, or stop |
| Applies when | An initiative has shared users, protected data, material cost, or consequential behavior |
| Does not apply when | A low-risk personal experiment has no shared data or effects; scale controls proportionally |
| Expected output | Owned pilot boundaries, scorecard, evidence, and decision |
| Evidence basis | Repository lifecycle controls and [NIST references](../references/README.md#risk-and-governance) |
| Last reviewed | 2026-07-04 |

Use this guide to decide whether an AI-enabled workflow has enough ownership, evidence, and control to proceed. Tool activity is not an outcome, and a demonstration is not a validated pilot.

## Applicability

Use the full lifecycle for funded pilots, shared services, protected data, customer-facing behavior, or workflows with material side effects. For a low-risk personal experiment, keep the same questions but scale the evidence to the consequence: name the outcome, constrain data and actions, record failures, and decide whether to continue. Organization-specific legal, compliance, privacy, and security policy takes precedence.

## Lifecycle

Move through this sequence:

`assess -> baseline -> select -> design -> pilot -> evaluate -> transfer -> scale, revise, or stop`

Each stage requires an accountable owner, entry criteria, evidence, and exit criteria. Standardize only after real delivery evidence shows value without unacceptable quality, security, privacy, or compliance regression.

## Pilot entry gate

A pilot may start only when all of the following are recorded:

- a named business owner, technical lead, users, and bounded workflow;
- metric definitions, data sources, owners, baseline period, and target;
- permitted data, context, models, tools, and side effects;
- human approval points, failure tolerance, and stop conditions;
- a time box and a receiving team expected to own the practice.

Missing baseline data must remain missing; do not reconstruct favorable estimates after execution.

## Scorecard

| Dimension | Evidence | Decision signal |
|---|---|---|
| Value | Accepted outcome per unit cost | Outcome improves enough to justify continued cost. |
| Delivery | Lead time and rework | Improvement does not hide extra review or correction work. |
| Quality | Acceptance and escaped defects | Quality is stable or improves. |
| Risk | Policy violations and severity | Residual risk has an accountable owner. |
| Adoption | Eligible work using the approved practice | Usage is bounded to suitable work, not maximized blindly. |
| Independence | Operation without central support | Ownership transfers to the receiving team. |
| Operations | Failures and manual intervention | Operational burden is visible and acceptable. |

Decide **scale** when target value is met, quality and risk do not regress, and ownership transfers. Decide **revise** only for a named, time-bounded correction with a credible value signal. Decide **stop** when value is absent, risk is unacceptable, ownership is missing, or specialist dependence persists.

## Accountability

| Decision | Accountable owner | Required evidence |
|---|---|---|
| Use-case approval and funding | Business owner | Outcome, scope, baseline, and risk acceptance |
| Data and access boundary | Security or privacy owner | Classification, allowed sources, retention, and access policy |
| Architecture and output verification | Technical lead | Architecture decision, tests, review, and citations where required |
| Side-effect approval | Business owner | Actor, exact action digest, and approval record |
| Runtime integration | Technical lead | Contract, failure, security, and operational evidence |
| Scale, revise, or stop | Business owner | Completed scorecard and decision rationale |

One accountable owner is required per decision. Human accountability is not transferred to a model, agent, or vendor.

## Architecture decisions

Material decisions record context, drivers, credible alternatives, selected approach, consequences, evidence, risks, owner, and review date. Evaluate models and tools against the use case and preserve provider substitution where its cost is justified. An approval applies only to the exact artifact or action reviewed and expires when that artifact changes materially.

## Exit gate

A pilot is complete only when the scorecard is populated, failures and rejected output are recorded, the receiving team demonstrates operation without central support, and the business owner records a scale, revise, or stop decision.

## Related references

The [NIST AI Risk Management Framework and Generative AI Profile](../references/README.md#risk-and-governance) provide broader risk-management context. This playbook's lifecycle and scorecard are project guidance, not a claim of NIST conformance.
