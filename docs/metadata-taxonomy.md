# Learning Metadata Taxonomy

| Learning metadata | Value |
|---|---|
| Career level | All levels |
| Topics | taxonomy, learning-navigation |
| Purpose | Classify documents consistently and choose what to learn next |
| Importance | Important |

Every learning document carries four fields directly below its title. The fields answer different questions and must not be collapsed into one score.

## Career level

Career level means **the earliest level at which this knowledge should be usable**, not the maximum seniority of its readers.

| Value | Reader expectation |
|---|---|
| L1 Fundamentals | Explain the concept, its limits, and basic safe use |
| L2 Practitioner | Apply it to a bounded workflow and produce verification evidence |
| L3 Senior | Design systems, compare trade-offs, and own reliability across contexts |
| L4 Lead | Turn it into repeatable team delivery and governance mechanisms |
| L5 Architect | Apply it across systems, organizations, economics, and evolution paths |
| L6 Principal | Create durable portfolio-level leverage and influence |
| L7 Distinguished | Shape enterprise or industry direction with independently recognized impact |
| All levels | Navigation or career material intentionally spans the progression |

A trailing `+` means the document begins at that level and remains directly relevant above it. Higher-level engineers are still accountable for lower-level critical knowledge.

## Topics

Use at least two concrete, searchable keywords. Prefer capability or problem domains such as `RAG`, `evaluation`, `AI-security`, or `observability`; avoid filler such as `AI`, `guide`, or `best-practice` by itself.

## Purpose

State the decision, artifact, or real-world use enabled by the document. This is not a summary of its table of contents.

## Importance

| Value | Meaning | Learning action |
|---|---|---|
| Critical | Missing it can invalidate safety, correctness, release, or core role readiness | Learn and demonstrate it before owning the relevant work |
| Important | Strongly affects quality, maintainability, or professional effectiveness | Learn it when entering the named scope |
| Good to know | Improves navigation, fluency, or efficiency but is not a standalone gate | Read when the use case appears |
| Awareness | Recognize the concept and know where to find deeper guidance | Skim; deepen only when scope requires it |

Importance is contextual. For example, agent-runtime recovery is critical when operating a stateful agent but irrelevant to a deterministic service that has no agent.

## Maintenance rule

When a document changes meaning, review all four fields. Update the indexes when its earliest career level, topics, purpose, or importance changes. Do not raise importance to make a topic look prestigious, and do not infer proficiency from reading alone; the career framework requires reviewable evidence.
