# AI Playbook Roadmap

This checklist records the completed milestones that make `ai-playbook` a useful, vendor-neutral AI Engineering reference. A checked item has evidence in this repository or its Git history. File presence alone does not count as completion.

## Milestone 1: Repository foundation — Complete

- [x] Create the public `ChuanGz/ai-playbook` repository.
- [x] Establish scope, status, usage, contribution, security, conduct, and license documents.
- [x] Add issue and pull-request templates.
- [x] Add least-privilege CI for Markdown and link validation.
- [x] Publish the baseline to `main` with passing CI.

**Outcome:** the repository has an enforceable OSS baseline and does not claim unsupported maturity.

## Milestone 2: Canonical foundation — Complete

- [x] Rewrite durable adoption and governance guidance into [adoption and governance](docs/lifecycle/adoption-and-governance.md).
- [x] Rewrite AI-specific delivery controls into [AI-assisted delivery](docs/lifecycle/ai-assisted-delivery.md).
- [x] Rewrite agent-runtime contracts into [agent runtime](docs/architecture/agent-runtime.md).
- [x] Review the canonical documents for duplication, unsuitable material, private evidence, and unsupported claims.
- [x] Publish and validate the canonical foundation on the public default branch.
- [x] Keep standalone reusable knowledge tooling, personal corpora, applications, and reference implementations outside this repository; retain bounded knowledge-workflow guidance where it teaches canonical AI Engineering decisions.

**Outcome:** `ai-playbook` has a public-safe canonical foundation with explicit content boundaries.

## Milestone 3: AI system design — Complete

- [x] Define an AI system decision model covering when to use deterministic software, model inference, retrieval, tools, agents, or a combination.
- [x] Define model-selection criteria using capability, quality, latency, cost, data boundary, operational risk, and substitution cost.
- [x] Define contracts for structured output, validation, repair, refusal, timeout, and provider degradation.
- [x] Add an architecture decision template with context, alternatives, consequences, evidence, owner, and review trigger.

**Pass condition:** an engineer can compare credible solution shapes and record a bounded, reviewable decision without assuming that an LLM or agent is always required.

## Milestone 4: Context, retrieval, and knowledge — Complete

- [x] Define context assembly, authority, freshness, provenance, token-budget, and sensitive-data controls.
- [x] Define the RAG lifecycle: source approval, ingestion, parsing, chunking, metadata, indexing, retrieval, reranking, grounding, citation, refresh, and deletion.
- [x] Explain embedding and vector-search tradeoffs, including cases where lexical, relational, or graph retrieval is preferable.
- [x] Define access-control enforcement across ingestion, retrieval, generated answers, cache, and telemetry.
- [x] Define evaluation gates for retrieval relevance, answer support, freshness, leakage, and abstention.

**Pass condition:** a team can design and review a grounded knowledge workflow with traceable sources, bounded access, measurable retrieval quality, and an explicit refresh strategy.

## Milestone 5: Tools, MCP, and agent orchestration — Complete

- [x] Define tool contracts for schemas, capability metadata, authorization, credentials, timeouts, idempotency, side effects, reconciliation, and audit receipts.
- [x] Define MCP client/server trust boundaries, capability discovery, versioning, error handling, and transport-independent controls.
- [x] Expand planning and orchestration guidance for dependency graphs, bounded delegation, concurrency, budgets, cancellation, termination, and human approval.
- [x] Define memory write policy, provenance, isolation, retention, poisoning controls, and deletion.
- [x] Add decision criteria for a workflow, a single agent, or multiple agents.

**Pass condition:** every proposed tool call, delegation, memory write, and side effect has an accountable authorization path, bounded execution contract, and recoverable failure behavior.

## Milestone 6: Evaluation, security, and operations — Complete

- [x] Define evaluation layers for components, tasks, workflows, regressions, safety, and release acceptance.
- [x] Define dataset provenance, representative cases, adversarial cases, scoring limits, human review, and change-triggered reevaluation.
- [x] Define AI-specific threat controls for prompt injection, data leakage, unauthorized tools, memory poisoning, model or dependency supply-chain risk, and audit tampering.
- [x] Define observability for model calls, retrieval, tool effects, approvals, quality, cost, latency, failures, and correlation without logging protected content.
- [x] Define fallback, rate-limit, provider-degradation, rollback, incident, and post-incident evidence requirements.

**Pass condition:** a release decision can cite repeatable evaluation, threat review, operational signals, failure handling, and named residual-risk owners.

## Milestone 7: Application guides and bounded examples — Complete

- [x] Add one end-to-end guide that applies the playbook to a bounded AI-enabled workflow from decision through release review.
- [x] Add a small RAG example only where it clarifies ingestion, retrieval, citations, access control, and evaluation contracts.
- [x] Add a small MCP tool example only where it clarifies schema, authorization, errors, idempotency, and observability.
- [x] Add a small agent workflow example only where it clarifies approval, budget, termination, trace, and reconciliation behavior.
- [x] Keep examples vendor-neutral and prevent them from becoming standalone products or implied reference architectures.
- [x] Keep application code and private business evidence outside the playbook.

**Pass condition:** each example exposes a real engineering decision or failure mode, passes its documented checks, and remains subordinate to a canonical contract.

## Milestone 8: Coherent release — Complete

- [x] Add a task-based documentation index and content-state catalog.
- [x] Define one glossary for model, context, memory, retrieval, tool, MCP, agent, workflow, evaluation, runtime, and approval terminology.
- [x] Remove duplicated or conflicting guidance and define deprecation and supersession rules.
- [x] Establish a primary-reference policy and public [reference index](docs/references/README.md).
- [x] Add decision-lifecycle and capability/evidence diagrams.
- [x] Pass Markdown lint, internal and external link checks, private-evidence review, and unsupported-claim review.
- [x] Align `README.md`, the documentation index, maintenance policy, changelog, and this roadmap.
- [x] Prepare the first release after Milestones 3–7 satisfy their pass conditions.

**Outcome:** readers can enter by role or task, follow consistent terminology, trace important claims, and distinguish documented contracts from system-specific evidence.

## Milestone 9: Career and competency integration — Complete

- [x] Bring the reusable People dimension from `ai-career` into `docs/career/`.
- [x] Define competency levels from fundamentals through distinguished scope.
- [x] Consolidate role profiles into a comparison-oriented role map.
- [x] Preserve focused transition paths without repeating generic software-engineering education.
- [x] Define portfolio evidence that distinguishes decisions and outcomes from activity volume.
- [x] Align repository scope, navigation, reading paths, diagrams, and release notes.

**Outcome:** technical guidance and professional progression now share one canonical playbook, while employer-specific promotion decisions and private assessment evidence remain out of scope.

## Milestone 10: LLM wiki and second-brain guidance — Complete

- [x] Distill the reusable lessons from `ai-llm-wiki` without importing its personal raw corpus or duplicating a standalone engine.
- [x] Document setup commands for repository-local and standalone LLM wikis.
- [x] Explain capture, immutable evidence, ingest, semantic and exact retrieval, grounded query, distillation, and maintenance.
- [x] Define how an LLM wiki supports a provenance-first second brain and where ordinary search or enterprise knowledge systems are preferable.
- [x] Add pass conditions for demonstrating LLM, RAG, and second-brain engineering capability.
- [x] Align repository scope, navigation, career evidence, and release notes.

**Outcome:** a reader can build and assess a source-grounded second brain while keeping runtime tooling and personal knowledge outside the playbook.

## Roadmap rules

- Complete milestones in order unless a later research task is needed to unblock an earlier decision.
- Do not create placeholder documents for unchecked items.
- Do not mark a task complete without a link to repository evidence or a recorded validation result.
- Do not import generic software-engineering guidance, full applications, generated logs, private evidence, stale summaries, or unsupported production claims.
- Update this roadmap in the same change that completes or changes a milestone.
