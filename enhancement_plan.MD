# Enhancement Plan

## Purpose

Demonstrate that independent engineers can apply the playbook's AI contracts to
real release decisions without maintainer interpretation.

## Current evidence and gap

The playbook has coherent architecture, assurance, lifecycle, career, and
knowledge-workflow guidance with validated documentation. Its stable labels are
based on internal review; executable evaluation evidence and independent AI
engineering and security review are still absent.

## Enhancement sequence

### E1 — Build vendor-neutral evaluation fixtures

- Add bounded fixtures for grounded answers, approval-gated tools, and the
  bounded research agent.
- Include dataset provenance, representative and adversarial cases, thresholds,
  abstention, cost and latency capture, and regression comparison.
- Keep provider adapters replaceable and application code out of the playbook.

**Exit evidence:** each fixture produces a repeatable release or stop decision
from documented inputs, thresholds, and limitations.

### E2 — Run independent implementation reviews

- Give three teams only one system brief and the relevant playbook route.
- Require a decision record, threat model, evaluation set, release decision, and
  operational response plan.
- Compare high-risk findings and record where reviewers disagree.

**Exit evidence:** reviewers consistently identify critical authority, data,
evaluation, and failure risks; oral maintainer interpretation is unnecessary.

### E3 — Conduct AI engineering and security review

- Review prompt injection, data leakage, tool authorization, memory poisoning,
  supply-chain exposure, audit integrity, degradation, and incident ownership.
- Publish sanitized findings and dispositions, including accepted residual risk.
- Correct canonical guidance where two or more reviewers misapply it.

**Exit evidence:** every material finding has an owner, decision, evidence, and
review trigger; the review does not equate checklist completion with safety.

### E4 — Add compatibility stewardship

- Maintain a dated matrix for fast-changing MCP and agent-runtime assumptions.
- Track source, tested behavior, compatibility boundary, and next review date.
- Deprecate stale examples without turning the playbook into vendor docs.

**Exit evidence:** time-sensitive claims are traceable, dated, and reviewed on a
defined trigger.

## Measures

| Measure | Target |
|---|---|
| Repeatable example evaluation fixtures | 3 |
| Independent system reviews | 3 |
| Material review findings with disposition | 100% |
| Undated fast-changing compatibility claims | 0 |

## Non-goals

- Expanding topic breadth before current contracts are independently applied.
- Shipping a production application or personal corpus in this repository.
- Treating agreement between reviewers as proof of system correctness.

## Review trigger

Review after each external assessment, material interface change, fixture
regression, or incident-derived learning contribution.
