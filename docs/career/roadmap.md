# AI Career Roadmap

| Learning metadata | Value |
|---|---|
| Career level | All levels |
| Topics | AI-career, skill-progression |
| Purpose | Identify the next capability and evidence gate |
| Importance | Important |

Use this role-neutral map to choose the next capability and its evidence gate. Skills are ordered by leverage; tools remain optional implementation choices.

```mermaid
flowchart TD
    L1["L1 Fundamentals<br/>software foundations → AI limits → responsible use"]
    L2["L2 Practitioner<br/>context → evaluation → integration → observability"]
    L3["L3 Senior<br/>system design → reliability → trade-offs → mentoring"]
    L4["L4 Lead<br/>direction → multi-team delivery → capability building"]
    L5["L5 Architect<br/>cross-system design → governance → evolution"]
    L6["L6 Principal<br/>portfolio leverage → organizational influence"]
    L7["L7 Distinguished<br/>enterprise or industry direction"]

    L1 -->|"Bounded feature + explained limits"| L2
    L2 -->|"Evaluated operational outcome"| L3
    L3 -->|"Sustained system and team outcomes"| L4
    L3 -->|"Cross-system decision scope"| L5
    L4 -->|"Mechanisms adopted across teams"| L5
    L5 -->|"Durable portfolio impact"| L6
    L6 -->|"Broad independently recognized impact"| L7
```

| Level | Primary capability | Evidence gate |
|---|---|---|
| L1 Fundamentals | Software delivery, AI limitations, prompting basics, responsible use | Deliver a bounded AI feature, explain limitations, and show tests |
| L2 Practitioner | Context engineering, evaluation, integration, traceability, human oversight | Own an evaluated workflow with production-relevant operational evidence |
| L3 Senior | AI system design, trade-offs, evaluation strategy, mentoring, incident learning | Sustain system and team outcomes across more than one context |
| L4 Lead | Direction, decomposition, multi-team alignment, delivery governance, capability building | Teams improve through mechanisms that persist without constant author support |
| L5 Architect | Cross-system architecture, adoption framing, governance mechanisms, economics, operating model | Architecture is adopted across teams and produces measured outcomes |
| L6 Principal | Portfolio strategy, reusable mechanisms, long-horizon planning, senior-leader development | Demonstrate durable impact beyond one program |
| L7 Distinguished | Enterprise or industry direction, original practice, succession and external contribution | Demonstrate broad, sustained, independently recognized impact |

## What AI changes

```mermaid
flowchart LR
    A["Lower scarcity value<br/>syntax, routine CRUD, boilerplate, API recall"]
    B["Required bridge<br/>implementation literacy and debugging"]
    C["Growing leverage<br/>architecture, distributed systems, AI engineering,<br/>domain knowledge, decisions, verification"]
    A --> B --> C
```

The left-hand skills remain necessary, but generation makes them easier to produce. Career leverage shifts toward framing, consequence-aware design, domain judgment, and verification. Engineers must still read, debug, secure, and operate generated implementation.

## Use the roadmap

1. Select a target role and level.
2. Preserve competencies already supported by evidence.
3. Identify the first missing high-leverage capability.
4. Choose work that produces reviewable evidence for that gap.
5. Advance only when the gate is sustained at the required scope.
