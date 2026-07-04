# Glossary

These definitions keep terms consistent inside this repository. A consuming system may use different names, but it should map them explicitly when applying the contracts.

## Core terms

**Actor**  
An authenticated human, service, or workload identity accountable for a request or action. A model is not an authority-bearing actor by itself.

**Agent**  
A bounded runtime identity that can interpret a goal, select or revise steps, and use configured capabilities within policy, budget, and termination constraints.

**Approval**  
An attributable decision authorizing an exact material artifact or action. Approval is invalid when a bound actor, target, argument, amount, policy, or version changes.

**Artifact**  
A versioned input or output stored outside transient model context, such as a document, plan, evaluation result, generated file, or effect receipt.

**Capability**  
A bounded operation available to a workflow or agent. A capability becomes usable only after version resolution, validation, authorization, and credential binding.

**Context**  
The ephemeral, authorized projection assembled for one reasoning or execution step. Context may contain request data, instructions, retrieved passages, tool schemas, and state references.

**Effect receipt**  
An attributable record that an external side effect was accepted, rejected, or remains ambiguous, including the action digest and idempotency information needed for reconciliation.

**Evaluation**  
A repeatable process that compares component, task, workflow, safety, regression, or operational behavior against owned criteria and thresholds.

**Grounding**  
Constraining and assessing output against authorized supporting evidence. Grounding does not guarantee truth when sources are wrong, stale, incomplete, or misinterpreted.

**Idempotency key**  
A stable identifier used by a capability to recognize repeated attempts for the same intended effect. It reduces duplicates but does not replace status reconciliation.

**Memory**  
Governed durable state retrieved or written across steps or runs. Memory is distinct from ephemeral context and must support provenance, access, retention, correction, and deletion.

**Model**  
A probabilistic inference dependency accessed through a versioned contract. Its output is an untrusted proposal until validated and accepted.

**MCP**  
Model Context Protocol, a versioned protocol for exchanging resources, prompts, and tools between clients and servers. Protocol compatibility does not establish trust or authorization.

**Orchestration**  
Durable coordination of run state, dependencies, concurrency, leases, approvals, deadlines, cancellation, delegation, and terminal outcomes.

**Plan**  
A versioned dependency graph of bounded steps, success criteria, permissions, budgets, deadlines, retry classes, approvals, and compensation where possible.

**Policy decision**  
An attributable `allow`, `deny`, or `require approval` result derived from immutable facts and a versioned policy.

**Provenance**  
Evidence of where content, data, configuration, or an artifact came from, including a stable source identifier and material version.

**RAG**  
Retrieval-augmented generation: selecting external evidence for model context before generating an output. Retrieval, authorization, generation, citation, and evaluation remain separate responsibilities.

**Reconciliation**  
Determining the actual external state after an ambiguous operation before deciding whether to retry, compensate, escalate, or stop.

**Run**  
One durable execution instance from accepted request to terminal state, identified and correlated across its plans, steps, model calls, retrieval, tools, approvals, and artifacts.

**Tool**  
A typed adapter to an external capability. A tool descriptor informs selection; deterministic controls authorize and execute it.

**Workflow**  
A defined sequence or graph of steps and state transitions. A deterministic workflow follows known transitions; an agentic workflow may revise a bounded plan at runtime.

## Normative language

**Must** and **required** identify a playbook gate. **Should** identifies a contextual recommendation whose exceptions need reasoning. **May** identifies an optional mechanism. These words do not override the consuming system's law, contract, or organizational policy.
