# AI Engineering Principles

| Learning metadata | Value |
|---|---|
| Career level | L1 Fundamentals |
| Topics | AI-engineering, risk |
| Purpose | Apply durable constraints to AI decisions |
| Importance | Critical |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Engineers, architects, reviewers, and technical leaders |
| Decision supported | Which constraints should govern an AI-enabled system decision |
| Applies when | AI may affect software behavior, data, decisions, or external actions |
| Does not apply when | A consuming policy or law requires stricter controls; those take precedence |
| Expected output | Explicit decision constraints and review questions |
| Evidence basis | Repository architecture and assurance contracts; public sources in [References](../references/README.md) |
| Last reviewed | 2026-07-04 |

These principles constrain decisions across the playbook. They are not implementation recipes; each consuming system still owns thresholds, policy, and evidence.

## Prefer the least complex credible system

Start with deterministic software. Add model inference, retrieval, tools, workflow state, memory, or agents only when a simpler design cannot satisfy a named outcome or failure constraint.

**Tradeoff:** simplicity can limit capability, but unnecessary AI components add probabilistic behavior, cost, attack surface, and operational burden.

## Treat model output as untrusted input

Validate model output before it influences durable state, protected data, external effects, or user decisions. Prompts cannot replace authorization, schema validation, or policy enforcement.

**Boundary:** low-consequence creative output may use lighter review, but its consumer still decides whether the result is acceptable.

## Bind authority to deterministic controls

Identity, permissions, budgets, approvals, and effect boundaries belong to code and policy outside the model. Authorization applies to the exact actor, action, resource, and material version reviewed.

**Failure prevented:** a model cannot grant itself capability, reinterpret a denial, or broaden an approval through generated text.

## Preserve evidence, not hidden reasoning

Record inputs needed for reproduction, source provenance, configuration versions, tool receipts, approvals, tests, outcomes, and failures. Do not require or retain private chain-of-thought.

**Tradeoff:** traceability consumes storage and can expose data, so retention and redaction must be explicit.

## Evaluate outcomes and failure behavior

Measure whether the system completes the accepted task under representative, edge, unsafe, and degraded conditions. Activity, token volume, fluent output, and demonstrations are not outcome evidence.

## Design for change and refusal

Models, data, providers, protocols, and policies change. Version material boundaries, define review triggers, and make refusal, fallback, rollback, and retirement normal system behavior.

## Keep humans accountable at consequential boundaries

Assign a named human owner for architecture, protected-data use, risk acceptance, release, and material side effects. Human approval is meaningful only when the approver can inspect the artifact, understand consequences, and refuse.

## Make claims proportional to evidence

Do not describe a design as secure, scalable, compliant, reliable, or production-ready without the relevant system-specific tests and operating evidence. Repository guidance can define a gate; it cannot pass the gate for a consuming system.
