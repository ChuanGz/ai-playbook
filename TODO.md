# AI Playbook Roadmap

This checklist presents the eight milestones required to make `ai-playbook` a useful, vendor-neutral AI Engineering reference. A checked item has evidence in this repository or its Git history. File presence alone does not count as completion.

## Milestone 1: Repository foundation — Complete

- [x] Create the public `ChuanGz/ai-playbook` repository.
- [x] Establish scope, status, usage, contribution, security, conduct, and license documents.
- [x] Add issue and pull-request templates.
- [x] Add least-privilege CI for Markdown and link validation.
- [x] Publish the baseline to `main` with passing CI.

**Outcome:** the repository has an enforceable OSS baseline and does not claim unsupported maturity.

## Milestone 2: Canonical foundation — Complete

- [x] Rewrite durable adoption and governance guidance into [adoption and governance](docs/adoption-and-governance.md).
- [x] Rewrite AI-specific delivery controls into [AI-assisted delivery](docs/ai-assisted-delivery.md).
- [x] Rewrite agent-runtime contracts into [agent runtime](docs/agent-runtime.md).
- [x] Review the canonical documents for duplication, unsuitable material, private evidence, and unsupported claims.
- [x] Publish and validate the canonical foundation on the public default branch.
- [x] Keep career guidance, reusable knowledge tooling, applications, and reference implementations outside this repository.

**Outcome:** `ai-playbook` has a public-safe canonical foundation with explicit content boundaries.

## Milestone 3: AI system design — Complete

- [x] Define an AI system decision model covering when to use deterministic software, model inference, retrieval, tools, agents, or a combination.
- [x] Define model-selection criteria using capability, quality, latency, cost, data boundary, operational risk, and substitution cost.
- [x] Define contracts for structured output, validation, repair, refusal, timeout, and provider degradation.
- [x] Add an architecture decision template with context, alternatives, consequences, evidence, owner, and review trigger.

**Pass condition:** an engineer can compare credible solution shapes and record a bounded, reviewable decision without assuming that an LLM or agent is always required.

## Milestone 4: Context, retrieval, and knowledge

- [ ] Define context assembly, authority, freshness, provenance, token-budget, and sensitive-data controls.
- [ ] Define the RAG lifecycle: source approval, ingestion, parsing, chunking, metadata, indexing, retrieval, reranking, grounding, citation, refresh, and deletion.
- [ ] Explain embedding and vector-search tradeoffs, including cases where lexical, relational, or graph retrieval is preferable.
- [ ] Define access-control enforcement across ingestion, retrieval, generated answers, cache, and telemetry.
- [ ] Define evaluation gates for retrieval relevance, answer support, freshness, leakage, and abstention.

**Pass condition:** a team can design and review a grounded knowledge workflow with traceable sources, bounded access, measurable retrieval quality, and an explicit refresh strategy.

## Milestone 5: Tools, MCP, and agent orchestration

- [ ] Define tool contracts for schemas, capability metadata, authorization, credentials, timeouts, idempotency, side effects, reconciliation, and audit receipts.
- [ ] Define MCP client/server trust boundaries, capability discovery, versioning, error handling, and transport-independent controls.
- [ ] Expand planning and orchestration guidance for dependency graphs, bounded delegation, concurrency, budgets, cancellation, termination, and human approval.
- [ ] Define memory write policy, provenance, isolation, retention, poisoning controls, and deletion.
- [ ] Add decision criteria for a workflow, a single agent, or multiple agents.

**Pass condition:** every proposed tool call, delegation, memory write, and side effect has an accountable authorization path, bounded execution contract, and recoverable failure behavior.

## Milestone 6: Evaluation, security, and operations

- [ ] Define evaluation layers for components, tasks, workflows, regressions, safety, and release acceptance.
- [ ] Define dataset provenance, representative cases, adversarial cases, scoring limits, human review, and change-triggered reevaluation.
- [ ] Define AI-specific threat controls for prompt injection, data leakage, unauthorized tools, memory poisoning, model or dependency supply-chain risk, and audit tampering.
- [ ] Define observability for model calls, retrieval, tool effects, approvals, quality, cost, latency, failures, and correlation without logging protected content.
- [ ] Define fallback, rate-limit, provider-degradation, rollback, incident, and post-incident evidence requirements.

**Pass condition:** a release decision can cite repeatable evaluation, threat review, operational signals, failure handling, and named residual-risk owners.

## Milestone 7: Application guides and bounded examples

- [ ] Add one end-to-end guide that applies the playbook to a bounded AI-enabled workflow from decision through release review.
- [ ] Add a small RAG example only where it clarifies ingestion, retrieval, citations, access control, and evaluation contracts.
- [ ] Add a small MCP tool example only where it clarifies schema, authorization, errors, idempotency, and observability.
- [ ] Add a small agent workflow example only where it clarifies approval, budget, termination, trace, and reconciliation behavior.
- [ ] Label provider-specific adapters and prevent examples from becoming standalone products or implied reference architectures.
- [ ] Use application repositories only as cited evidence after validating the relevant claim; do not copy application code or private business evidence.

**Pass condition:** each example exposes a real engineering decision or failure mode, passes its documented checks, and remains subordinate to a canonical contract.

## Milestone 8: Coherent release

- [x] Add an initial task-based documentation index and extend it as new canonical content is completed.
- [ ] Define one glossary for model, context, memory, retrieval, tool, MCP, agent, workflow, evaluation, runtime, and approval terminology.
- [ ] Remove duplicated or conflicting guidance and record any superseded document.
- [x] Establish a primary-reference policy and initial public [reference index](docs/references.md); continue adding source-level provenance with new guidance.
- [ ] Pass Markdown lint, internal and external link checks, secret and private-evidence review, and unsupported-claim review.
- [ ] Confirm that `README.md`, the documentation index, and this roadmap describe the same ownership boundaries and status.
- [ ] Tag the first release only when Milestones 3–7 satisfy their pass conditions and final CI passes.

**Outcome:** readers can enter by role or task, follow consistent terminology, trace important claims, and distinguish documented contracts from system-specific evidence.

## Roadmap rules

- Complete milestones in order unless a later research task is needed to unblock an earlier decision.
- Do not create placeholder documents for unchecked items.
- Do not mark a task complete without a link to repository evidence or a recorded validation result.
- Do not import generic software-engineering guidance, full applications, generated logs, private evidence, stale summaries, or unsupported production claims.
- Update this roadmap in the same change that completes or changes a milestone.
