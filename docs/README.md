# Documentation Index

Use this index to choose the smallest set of guidance needed for a real decision. The documents are references and decision guides, not evidence that a consuming system passed review.

## Choose a task

| If you need to... | Start with | Expected result |
|---|---|---|
| Decide whether AI belongs in a solution | [AI system decision guide](ai-system-decision-guide.md) | A recorded solution shape, alternatives, evidence plan, and review trigger |
| Approve, revise, scale, or stop an AI initiative | [Adoption and governance](adoption-and-governance.md) | Named owners, pilot gates, scorecard, and an evidence-backed decision |
| Accept AI-generated engineering work | [AI-assisted delivery](ai-assisted-delivery.md) | Bounded context, deterministic checks, approval evidence, and traceability |
| Review an agent runtime design | [Agent runtime](agent-runtime.md) | Explicit component ownership, contracts, failure behavior, and security controls |

See [References](references.md) for the external standards and specifications that inform terminology and review questions.

## Recommended sequence

1. Use the decision guide to choose the least complex credible solution.
2. Apply adoption gates before funding or scaling the work.
3. Apply delivery controls whenever AI proposes engineering artifacts or actions.
4. Apply runtime contracts only when the solution actually uses tools, memory, orchestration, or agents.

## Current limits

The repository does not yet contain complete guidance for RAG, MCP, evaluation systems, operational readiness, or worked implementations. Those gaps are tracked in the [roadmap](../TODO.md). Do not infer missing controls from folder names or planned milestones.

## Evidence and interpretation

Normative words such as **must** or **required** describe a playbook gate. A consuming team still defines system-specific thresholds, owners, policies, and evidence. Contextual recommendations state their conditions; examples must not be promoted into universal architecture rules.
