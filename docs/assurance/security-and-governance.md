# Security and Governance

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Security, privacy, governance, architecture, and engineering reviewers |
| Decision supported | Whether deterministic controls and ownership address material AI threats |
| Applies when | Models, retrieval, tools, memory, agents, or external providers cross trust boundaries |
| Does not apply when | Used as a substitute for applicable security, legal, privacy, or compliance review |
| Expected output | Threat map, controls, verification, owners, and bounded exceptions |
| Evidence basis | Repository threat controls; [NIST and OWASP references](../references/README.md) |
| Last reviewed | 2026-07-04 |

Use this reference to connect AI-specific threats to deterministic controls and accountable decisions. It complements, but does not replace, the consuming organization's security, privacy, legal, and compliance processes.

## Trust boundaries

Review user input, retrieved content, prompts, models, providers, tools, MCP peers, memory, artifacts, telemetry, evaluation data, operators, and external systems as distinct boundaries. Data crossing one boundary does not inherit trust from another.

## Threat and control map

| Threat | Required control | Verification |
|---|---|---|
| Direct or indirect prompt injection | Isolate untrusted content; keep authorization and policy outside prompts | Hostile-content tests cannot change permissions or protected instructions |
| Sensitive-data disclosure | Classify, minimize, authorize, redact, retain, and delete across every derivative | Cross-role and cross-tenant denial tests plus telemetry review |
| Improper output handling | Validate and encode output before queries, rendering, code, paths, or commands | Injection and malformed-output tests at the downstream boundary |
| Excessive agency | Tool allowlist, least privilege, budgets, approvals, and termination | Attempts beyond scope fail closed and are attributable |
| Memory or knowledge poisoning | Source authority, provenance, validation, versioning, correction, and deletion | Untrusted claims cannot become approved durable instruction or fact |
| Supply-chain compromise | Pin and review models, actions, packages, tools, servers, datasets, and artifacts | Provenance and integrity checks cover build and runtime dependencies |
| Duplicate or ambiguous effects | Action digest, idempotency, receipt, and reconciliation | Timeout-after-effect tests do not repeat the effect blindly |
| Audit tampering | Append-only protected records and separation of duties | Unauthorized mutation fails and gaps are detected |
| Resource exhaustion | Quotas, deadlines, concurrency, rate, token, step, and spend limits | Adversarial and accidental loops terminate within bounds |
| Misleading or unsupported output | Grounding, evaluation, uncertainty, refusal, and human escalation | Unsupported high-impact claims are rejected or escalated |

## Governance decisions

Assign accountable owners for use-case approval, data and access, architecture, model and provider selection, tool authority, evaluation thresholds, release, incidents, exceptions, and retirement. One owner may cover multiple decisions, but no material decision may be owned by a model or unnamed group.

Record policy and approval versions. Approval binds to the exact actor, purpose, data, action, resource, amount where relevant, and material artifact version. Reevaluate when any bound fact changes.

## Data handling

Map data from capture through prompts, provider processing, retrieval indexes, caches, memory, artifacts, telemetry, evaluation sets, exports, backups, and deletion. Document residency, retention, training use, subprocessors, access, encryption, and incident obligations from the applicable contracts and policy.

Do not log secrets, raw credentials, hidden reasoning, or unnecessary personal data. Redaction must occur before data enters a less trusted sink.

## Exceptions

An exception records scope, reason, rejected alternatives, compensating controls, approver, evidence, expiry, and rollback. Exceptions expire automatically and cannot silently become the default architecture.

## Security review gate

- [ ] Assets, actors, boundaries, data classes, and material side effects are mapped.
- [ ] Model output cannot authorize itself or directly cross a protected boundary.
- [ ] Retrieval, memory, tools, and telemetry enforce tenant and access isolation.
- [ ] Dependency and model provenance are reviewable.
- [ ] Abuse, injection, leakage, denial, and resource-exhaustion cases are tested.
- [ ] Approvals and exceptions are exact, attributable, and expiring.
- [ ] Incident reporting, containment, evidence preservation, and revocation are ready.

## Related references

Use the [NIST and OWASP references](../references/README.md) for broader risk-management and LLM application-security context. Passing this checklist is not a security or compliance certification.
