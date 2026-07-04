# Documentation Index

Use this index to choose the smallest set of guidance needed for a real decision. The documents are references and decision guides, not evidence that a consuming system passed review.

## Content map

| Area | Responsibility | Current content |
|---|---|---|
| Foundations | Durable principles, terms, and solution-selection decisions | [Principles](foundations/principles.md), [system decision guide](foundations/system-decision-guide.md), [decision record](foundations/decision-record-template.md) |
| Lifecycle | Adoption and engineering-delivery gates | [Adoption and governance](lifecycle/adoption-and-governance.md), [AI-assisted delivery](lifecycle/ai-assisted-delivery.md) |
| Architecture | Runtime, retrieval, tool, protocol, and agent boundaries | [Context, retrieval, and knowledge](architecture/context-retrieval-and-knowledge.md), [agent runtime](architecture/agent-runtime.md) |
| Assurance | Evaluation, security, observability, and release evidence | Planned in the [roadmap](../TODO.md) |
| Guides | End-to-end application of multiple contracts | Planned in the [roadmap](../TODO.md) |
| Examples | Small artifacts that expose a decision or failure mode | Planned in the [roadmap](../TODO.md) |
| References | Public sources and repository interpretation rules | [References](references/README.md) |

## Choose a task

| If you need to... | Start with | Expected result |
|---|---|---|
| Decide whether AI belongs in a solution | [System decision guide](foundations/system-decision-guide.md) | A recorded solution shape, alternatives, evidence plan, and review trigger |
| Approve, revise, scale, or stop an AI initiative | [Adoption and governance](lifecycle/adoption-and-governance.md) | Named owners, pilot gates, scorecard, and an evidence-backed decision |
| Accept AI-generated engineering work | [AI-assisted delivery](lifecycle/ai-assisted-delivery.md) | Bounded context, deterministic checks, approval evidence, and traceability |
| Review an agent runtime design | [Agent runtime](architecture/agent-runtime.md) | Explicit component ownership, contracts, failure behavior, and security controls |
| Design a grounded knowledge workflow | [Context, retrieval, and knowledge](architecture/context-retrieval-and-knowledge.md) | Governed sources, context manifest, retrieval choices, evaluation gates, refresh, and deletion |

See [References](references/README.md) for the external standards and specifications that inform terminology and review questions. See [MAINTENANCE.md](../MAINTENANCE.md) for maturity, review, change, and deprecation rules.

## Recommended sequence

1. Use the decision guide to choose the least complex credible solution.
2. Apply adoption gates before funding or scaling the work.
3. Apply delivery controls whenever AI proposes engineering artifacts or actions.
4. Apply runtime contracts only when the solution actually uses tools, memory, orchestration, or agents.

## Current limits

The repository does not yet contain complete guidance for RAG, MCP, evaluation systems, operational readiness, or worked implementations. Those gaps are tracked in the [roadmap](../TODO.md). Do not infer missing controls from folder names or planned milestones.

## Evidence and interpretation

Normative words such as **must** or **required** describe a playbook gate. A consuming team still defines system-specific thresholds, owners, policies, and evidence. Contextual recommendations state their conditions; examples must not be promoted into universal architecture rules.
