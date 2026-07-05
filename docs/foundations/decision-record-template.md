# AI Architecture Decision Record

| Learning metadata | Value |
|---|---|
| Career level | L3 Senior |
| Topics | architecture-decisions, evidence |
| Purpose | Record consequential AI design choices |
| Importance | Important |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Decision authors, reviewers, and accountable technical owners |
| Decision supported | How to record and review a material AI architecture choice |
| Applies when | A choice changes capability, authority, risk, cost, or operational responsibility |
| Does not apply when | The change is editorial and does not alter a decision contract |
| Expected output | A versioned decision record with evidence and review trigger |
| Evidence basis | [System Decision Guide](system-decision-guide.md) and [Maintenance Policy](../../MAINTENANCE.md) |
| Last reviewed | 2026-07-04 |

Copy this template into the consuming repository for a material AI system decision. Remove instructional text that does not apply, but do not omit a section merely because evidence is unavailable; record the gap and owner.

```markdown
# Decision: <short title>

- Status: proposed | accepted | deprecated | superseded
- Owner: <accountable person or role>
- Date: <YYYY-MM-DD>
- Review trigger: <event, threshold, or date>

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

## Rollback or retirement

<How to disable, replace, migrate, or remove the capability safely.>

## Evidence

<Public or repository-local links to experiments, reviews, incidents, and results.>
```

## Acceptance gate

The record is acceptable when:

- the outcome and accountable owner are named;
- alternatives include a simpler credible design;
- new failure modes and operational costs are visible;
- thresholds and evidence can falsify the decision;
- rollback or retirement is feasible or its absence is explicitly accepted;
- the review trigger is observable.
