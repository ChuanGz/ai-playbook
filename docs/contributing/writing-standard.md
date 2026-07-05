# Writing Standard

| Learning metadata | Value |
|---|---|
| Career level | L3 Senior |
| Topics | documentation, engineering-judgment |
| Purpose | Write maintainable decision-oriented guidance |
| Importance | Important |

This standard preserves a careful, precise, evidence-led voice across the playbook.

## Document contract

Every canonical guide or reference must make these fields discoverable near its beginning:

| Field | Required answer |
|---|---|
| Status | Draft, Stable, or Deprecated |
| Audience | Who makes or reviews the decision |
| Decision supported | The concrete choice, task, or gate the document enables |
| Applies when | Conditions that justify using the guidance |
| Does not apply when | Boundaries and simpler alternatives |
| Expected output | The artifact, evidence, or decision produced |
| Evidence basis | Repository evidence and public sources supporting the guidance |
| Last reviewed | ISO date of the latest content review |

Use a compact table when it improves scanning. Do not repeat the same paragraph under several labels.

## Reasoning pattern

Lead with the real problem, then explain:

1. why the problem changes an engineering outcome;
2. the credible options;
3. conditions favoring each option;
4. the recommended choice under named conditions;
5. consequences and tradeoffs;
6. expected failure modes;
7. evidence needed to accept the choice;
8. the event that requires review.

Prefer:

> Use a deterministic workflow when transitions and approvals are known, because it makes recovery and authority reviewable. Add runtime replanning only when evaluation shows that fixed transitions cannot satisfy the task.

Avoid:

> Agentic workflows are a best practice for complex tasks.

The first statement names conditions, reasoning, evidence, and an escalation boundary. The second hides all four.

## Claims and normative language

- **Must** or **required:** a repository gate tied to a named failure or necessary evidence.
- **Should:** a contextual recommendation with a credible exception.
- **May:** an optional mechanism whose value depends on context.
- **Principle:** a durable constraint with boundaries and tradeoffs.
- **Example:** an illustration, never proof that a design works in production.

Do not use “best practice,” “secure,” “scalable,” “reliable,” “compliant,” or “production-ready” without defining the context and evidence that makes the claim testable.

## Examples

An example must expose judgment. Include:

- context and desired outcome;
- selected design;
- credible rejected alternative;
- reason for the boundary;
- failure demonstrated;
- evidence required;
- condition that would change the decision.

Keep examples small. Do not create fictional metrics, incidents, customers, or production results.

## Checklists

Every item must prevent a named failure or require observable evidence. Replace decorative items such as “ensure quality” with a pass condition such as “material claims resolve to authorized supporting passages.”

## Structure and naming

- Use US English and lowercase kebab-case filenames.
- Name files after the decision or task, not the tool used to write them.
- Let the folder provide category context; avoid redundant suffixes such as `-example` inside `examples/`.
- Use one H1 matching the reader-facing title.
- Prefer the smallest useful document; split only for a different reader goal or ownership boundary.
- Update the nearest section index and the root documentation index in the same change.

## Review gate

- [ ] The document contract is complete and accurate.
- [ ] The recommendation names conditions, alternatives, tradeoffs, and failures.
- [ ] Normative statements have a reason and observable evidence.
- [ ] Examples expose judgment without invented results.
- [ ] Claims follow the [Evidence Policy](evidence-policy.md).
- [ ] Navigation, terminology, maturity state, and review date are current.
