# Documentation Index

Use this index to choose the smallest set of guidance needed for a real decision. The documents are references and decision guides, not evidence that a consuming system passed review.

New to the subject? Start with [How to read this playbook](reading-guide.md), then use [AI concepts in plain English](foundations/concepts-in-plain-english.md). You do not need to read the repository front to back.

## Content map

| Area | State | Responsibility | Current content |
|---|---|---|---|
| Foundations | Stable | Durable principles, terms, and solution-selection decisions | [Concepts in plain English](foundations/concepts-in-plain-english.md), [principles](foundations/principles.md), [glossary](foundations/glossary.md), [system decision guide](foundations/system-decision-guide.md), [decision record](foundations/decision-record-template.md) |
| Lifecycle | Stable | Adoption and engineering-delivery gates | [Adoption and governance](lifecycle/adoption-and-governance.md), [AI-assisted delivery](lifecycle/ai-assisted-delivery.md) |
| Architecture | Stable | Runtime, retrieval, tool, protocol, and agent boundaries | [Context, retrieval, and knowledge](architecture/context-retrieval-and-knowledge.md), [tools, MCP, memory, and orchestration](architecture/tools-mcp-and-orchestration.md), [agent runtime](architecture/agent-runtime.md) |
| Assurance | Stable | Evaluation, security, observability, and release evidence | [Evaluation and release](assurance/evaluation-and-release.md), [security and governance](assurance/security-and-governance.md), [observability and operations](assurance/observability-and-operations.md) |
| Guides | Stable | End-to-end application of multiple contracts | [Bounded AI workflow to release review](guides/take-a-bounded-ai-workflow-to-release.md) |
| Examples | Stable | Small artifacts that expose a decision or failure mode | [Grounded answer](examples/grounded-answer.md), [approval-gated MCP tool](examples/approval-gated-mcp-tool.md), [bounded agent](examples/bounded-research-agent.md) |
| References | Stable | Public sources and repository interpretation rules | [References](references/README.md) |

## Choose a task

| If you need to... | Start with | Expected result |
|---|---|---|
| Understand the vocabulary before making a design decision | [Concepts in plain English](foundations/concepts-in-plain-english.md) | A mental model of inference, context, RAG, tools, workflows, agents, MCP, and evaluation |
| Decide whether AI belongs in a solution | [System decision guide](foundations/system-decision-guide.md) | A recorded solution shape, alternatives, evidence plan, and review trigger |
| Approve, revise, scale, or stop an AI initiative | [Adoption and governance](lifecycle/adoption-and-governance.md) | Named owners, pilot gates, scorecard, and an evidence-backed decision |
| Accept AI-generated engineering work | [AI-assisted delivery](lifecycle/ai-assisted-delivery.md) | Bounded context, deterministic checks, approval evidence, and traceability |
| Review an agent runtime design | [Agent runtime](architecture/agent-runtime.md) | Explicit component ownership, contracts, failure behavior, and security controls |
| Design a grounded knowledge workflow | [Context, retrieval, and knowledge](architecture/context-retrieval-and-knowledge.md) | Governed sources, context manifest, retrieval choices, evaluation gates, refresh, and deletion |
| Expose tools or orchestrate agents | [Tools, MCP, memory, and orchestration](architecture/tools-mcp-and-orchestration.md) | Typed capabilities, explicit trust boundaries, governed state, bounded delegation, and termination |
| Decide whether a change can release | [Evaluation and release](assurance/evaluation-and-release.md) | Versioned cases, thresholds, failures, exceptions, rollback, and approval evidence |
| Review threats and authority | [Security and governance](assurance/security-and-governance.md) | Trust boundaries, deterministic controls, data handling, and owned exceptions |
| Prepare for operation and incidents | [Observability and operations](assurance/observability-and-operations.md) | User-impact signals, degradation, recovery, cost control, and incident ownership |
| Take one workflow through the playbook | [Bounded AI workflow guide](guides/take-a-bounded-ai-workflow-to-release.md) | A reviewable path from outcome framing to release, revise, pilot, or stop |

## Choose a role

| Role | Recommended path |
|---|---|
| Engineering leader | [Adoption and governance](lifecycle/adoption-and-governance.md) → [evaluation and release](assurance/evaluation-and-release.md) → [observability and operations](assurance/observability-and-operations.md) |
| Architect | [Principles](foundations/principles.md) → [system decision guide](foundations/system-decision-guide.md) → [architecture](architecture/README.md) → [assurance](assurance/README.md) |
| AI engineer | [System decision guide](foundations/system-decision-guide.md) → [architecture](architecture/README.md) → [bounded workflow guide](guides/take-a-bounded-ai-workflow-to-release.md) |
| Security reviewer | [Security and governance](assurance/security-and-governance.md) → [tools and MCP](architecture/tools-mcp-and-orchestration.md) → [evaluation and release](assurance/evaluation-and-release.md) |
| Operator or SRE | [Agent runtime](architecture/agent-runtime.md) → [observability and operations](assurance/observability-and-operations.md) → [evaluation and release](assurance/evaluation-and-release.md) |
| Contributor | [Writing standard](contributing/writing-standard.md) → [evidence policy](contributing/evidence-policy.md) → [contributing](../CONTRIBUTING.md) → [maintenance policy](../MAINTENANCE.md) |

See [References](references/README.md) for the external standards and specifications that inform terminology and review questions. See [MAINTENANCE.md](../MAINTENANCE.md) for maturity, review, change, and deprecation rules.

See [Playbook map](playbook-map.md) for the decision lifecycle and capability/evidence map.

## Recommended sequence

1. Use the decision guide to choose the least complex credible solution.
2. Apply adoption gates before funding or scaling the work.
3. Apply delivery controls whenever AI proposes engineering artifacts or actions.
4. Apply runtime contracts only when the solution actually uses tools, memory, orchestration, or agents.

## Boundaries

The repository defines reusable guidance and bounded examples. It does not provide a complete application, select a vendor, establish organization policy, certify compliance, or prove production readiness. The [roadmap](../ROADMAP.md) records the completed initial scope and remains the place for future milestone changes.

## Evidence and interpretation

Normative words such as **must** or **required** describe a playbook gate. A consuming team still defines system-specific thresholds, owners, policies, and evidence. Contextual recommendations state their conditions; examples must not be promoted into universal architecture rules.
