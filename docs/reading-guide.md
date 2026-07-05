# How to Read This Playbook

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Readers who need a useful path through the repository without reading every document |
| Decision supported | Which small set of documents to read for the reader's current task |
| Applies when | Entering the playbook for the first time or returning with a specific problem |
| Does not apply when | Looking up the exact meaning of one term; use the glossary instead |
| Expected output | A reading path and one concrete artifact or decision |
| Evidence basis | Current repository structure and the outputs promised by each canonical document |
| Last reviewed | 2026-07-04 |

This is a working playbook, not a book. Start with a question, follow one path, and stop when you have the artifact needed for the next review.

## The five-minute orientation

1. Read [AI concepts in plain English](foundations/concepts-in-plain-english.md) if terms such as grounding, RAG, tool use, or agent are unclear.
2. Use the [system decision guide](foundations/system-decision-guide.md) to choose the least complex credible solution.
3. Open only the architecture document for capabilities the solution actually uses.
4. Use [evaluation and release](assurance/evaluation-and-release.md) before treating a prototype as releasable.
5. Store decisions, tests, approvals, and operational evidence in the consuming project. This repository supplies the questions and contracts, not proof that your system passed them.

## Choose a path

### Software developer: “I need to add AI safely”

Read:

1. [Concepts in plain English](foundations/concepts-in-plain-english.md)
2. [System decision guide](foundations/system-decision-guide.md)
3. [Bounded AI workflow guide](guides/take-a-bounded-ai-workflow-to-release.md)
4. The closest [worked example](examples/README.md)

Leave with: an output contract, failure cases, deterministic checks, and a small evaluation set.

### AI engineer: “I need to design the runtime”

Read:

1. [System decision guide](foundations/system-decision-guide.md)
2. [Context, retrieval, and knowledge](architecture/context-retrieval-and-knowledge.md)
3. [Tools, MCP, memory, and orchestration](architecture/tools-mcp-and-orchestration.md)
4. [Agent runtime](architecture/agent-runtime.md) only if runtime planning or recovery is actually required
5. [Evaluation and release](assurance/evaluation-and-release.md)

Leave with: component boundaries, typed contracts, authority limits, evaluation gates, and failure behavior.

### Staff engineer or architect: “I need to make or review a decision”

Read:

1. [Principles](foundations/principles.md)
2. [System decision guide](foundations/system-decision-guide.md)
3. [Decision record template](foundations/decision-record-template.md)
4. The relevant [architecture](architecture/README.md) and [assurance](assurance/README.md) sections

Leave with: alternatives, decision drivers, consequences, validation evidence, and a trigger to revisit the decision.

### Engineering leader: “I need to approve a pilot or scale decision”

Read:

1. [Adoption and governance](lifecycle/adoption-and-governance.md)
2. [Evaluation and release](assurance/evaluation-and-release.md)
3. [Observability and operations](assurance/observability-and-operations.md)

Leave with: an owner, baseline, target, pilot boundary, stop conditions, release evidence, and operating review.

### Security reviewer or operator: “I need to bound consequences”

Read:

1. [Security and governance](assurance/security-and-governance.md)
2. [Tools, MCP, memory, and orchestration](architecture/tools-mcp-and-orchestration.md)
3. [Observability and operations](assurance/observability-and-operations.md)
4. [Evaluation and release](assurance/evaluation-and-release.md)

Leave with: trust boundaries, denied-action tests, revocation and recovery paths, telemetry, and named incident ownership.

### Professional or hiring manager: “I need to assess growth into an AI role”

Read:

1. [Career roadmap](career/roadmap.md)
2. [AI role map](career/roles.md)
3. The closest [transition path](career/transition-paths.md)
4. [Project evidence](career/project-evidence.md)

Leave with: a target role, current competency level, first material gap, and an evidence plan that can be reviewed without relying on titles or certificates.

### Engineer or learner: “I need to build a source-grounded second brain”

Read:

1. [Concepts in plain English](foundations/concepts-in-plain-english.md)
2. [Context, retrieval, and knowledge](architecture/context-retrieval-and-knowledge.md)
3. [Build an LLM wiki as a second brain](guides/build-an-llm-wiki-second-brain.md)
4. [LLM, RAG, and second-brain capability](career/llm-rag-second-brain-capability.md)

Leave with: a working ingest-query-maintain loop, source-grounded answers, and reviewable evidence of the decisions and skills involved.

## How to use a page

Canonical pages begin with a small contract. Read **Applies when**, **Does not apply when**, and **Expected output** first. Then:

- treat **must** as a playbook gate that needs observable evidence;
- treat **should** as a recommendation that may have a reasoned exception;
- adapt illustrative examples rather than copying them as production architecture;
- follow a related reference when you need to verify the source, protocol, or security category;
- record local thresholds and evidence in the consuming project.

## What counts as support

The playbook uses three kinds of support, and they should not be confused:

- **Official source:** a framework, protocol, or security reference supports terminology or a concrete review question. The annotated [references](references/README.md) explain why each source is useful.
- **Transferable reasoning:** a recommendation connects a named failure to a control and states where the recommendation stops applying.
- **Illustrative example:** a small artifact shows how a contract can work. It improves understanding but does not prove production success.

Proof that a real system is effective, safe, or ready to release must come from that system: versioned evaluations, test results, approvals, traces, incidents, user outcomes, and operating measurements. The playbook shows what evidence to request; it must not invent that evidence.

## A simple reading test

After reading, answer four questions:

1. What decision changed or became clearer?
2. What artifact will be created or reviewed?
3. What failure does the guidance prevent or expose?
4. What evidence would make the decision change?

If none can be answered, the page has not yet helped with the current problem. Choose a task from the [documentation index](README.md) instead of continuing sequentially.
