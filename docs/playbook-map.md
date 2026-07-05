# Playbook Diagrams

| Learning metadata | Value |
|---|---|
| Career level | L1 Fundamentals |
| Topics | AI-lifecycle, system-map |
| Purpose | See how decisions, delivery, and operations connect |
| Importance | Good to know |

These diagrams show how the playbook fits together. They describe document responsibilities, not a deployable system architecture.

For a guided entry point, use [How to read this playbook](reading-guide.md). For the capability progression from deterministic code to agents, use [AI concepts in plain English](foundations/concepts-in-plain-english.md).

## Decision and operating lifecycle

```mermaid
flowchart LR
    D["Decide"] --> A["Adopt or pilot"]
    A --> B["Build with controls"]
    B --> E["Evaluate"]
    E --> R{"Release decision"}
    R -->|Release| O["Operate"]
    R -->|Revise| B
    R -->|Stop| X["Retire or reject"]
    O --> I{"Evidence review"}
    I -->|Improve| D
    I -->|Continue| O
    I -->|Retire| X
```

Use:

- [System decision guide](foundations/system-decision-guide.md) for **Decide**.
- [Adoption and governance](lifecycle/adoption-and-governance.md) for **Adopt or pilot**.
- [AI-assisted delivery](lifecycle/ai-assisted-delivery.md) and architecture references for **Build**.
- [Evaluation and release](assurance/evaluation-and-release.md) for **Evaluate** and **Release decision**.
- [Observability and operations](assurance/observability-and-operations.md) for **Operate** and evidence review.

## Capability and evidence map

```mermaid
flowchart TB
    F["Foundations<br/>principles, terms, decisions"]
    L["Lifecycle<br/>adoption and delivery"]
    A["Architecture<br/>context, retrieval, tools, MCP, agents"]
    S["Assurance<br/>evaluation, security, operations"]
    G["Guides<br/>end-to-end application"]
    E["Examples<br/>bounded contracts"]
    C["Career<br/>roles, progression, evidence"]
    P["Consuming project evidence<br/>ADRs, tests, approvals, traces, incidents"]

    F --> L
    F --> A
    L --> S
    A --> S
    F --> G
    L --> G
    A --> G
    S --> G
    G --> E
    G --> P
    E --> P
    S --> P
    F --> C
    L --> C
    A --> C
    S --> C
    C --> P
```

The playbook defines reusable questions and gates. Only the consuming project can produce evidence that its implementation passes them.
