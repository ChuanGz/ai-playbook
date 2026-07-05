# AI Engineering Playbook

A vendor-neutral playbook for engineers and technical leaders who must design AI systems, control their failure modes, and grow the professional judgment needed to deliver them.

## What this repository gives you

This playbook turns broad advice such as “use RAG,” “add an agent,” or “evaluate the model” into reviewable engineering decisions. A reader should leave with an artifact they can use: a solution-shape decision, a bounded contract, an evaluation plan, a release gate, or an operational control.

| Reader | Practical value |
|---|---|
| Software developer | Know when ordinary code is enough, how to treat model output safely, and what to test before merging AI-assisted work |
| AI engineer | Design retrieval, tools, memory, and agent behavior as explicit contracts rather than prompt-only behavior |
| Staff or principal engineer | Compare credible alternatives, expose trade-offs, and define evidence that can support an architecture or release decision |
| Architect | Separate system responsibilities and trust boundaries while avoiding unnecessary agent complexity |
| Engineering leader | Set pilot, ownership, approval, scale, and stop gates without pretending that a demo proves value |
| Security or operations reviewer | Review authority, data handling, failure recovery, telemetry, cost, and incident ownership |
| Professional or hiring manager | Map AI roles and competency levels to reviewable evidence rather than titles, tools, or certificates |

The repository does not teach a framework API. It helps readers ask better questions before choosing one and verify the resulting system afterward.

## Status

Version 1.0 provides a stable initial documentation set for AI system decisions, adoption, delivery, retrieval, tools, MCP, agents, evaluation, security, and operations. Stable means the repository's current recommendation under its stated conditions; it does not certify any consuming system.

The playbook documents decision controls and reference contracts. It is not a compliance framework, certification, complete security standard, or proof that any described system is production-ready.

## Start here

- [How to read this playbook](docs/reading-guide.md): choose a short path by experience, role, or immediate problem.
- [AI concepts in plain English](docs/foundations/concepts-in-plain-english.md): understand the terms through one progressively expanded example.
- [Documentation index](docs/README.md): enter by task and understand how the documents fit together.
- [Playbook diagrams](docs/playbook-map.md): see the decision lifecycle and capability/evidence map.
- [System decision guide](docs/foundations/system-decision-guide.md): decide whether the solution needs deterministic software, model inference, retrieval, tools, a workflow, or an agent.
- [AI career framework](docs/career/README.md): choose a role, competency level, transition path, and evidence plan.
- [Eight-milestone roadmap](ROADMAP.md): see completed foundations, remaining work, and release gates.
- [Maintenance policy](MAINTENANCE.md): understand content maturity, review triggers, versioning, and deprecation.
- [Changelog](CHANGELOG.md): review user-visible release changes.

## Setup

No build or runtime setup is required. Read the Markdown files directly.

## Usage

Start with the [AI system decision guide](docs/foundations/system-decision-guide.md), then use the [documentation index](docs/README.md) to apply the relevant controls. Record architecture decisions, thresholds, tests, approvals, and operational evidence in the consuming project; do not treat this repository as evidence that a system passed its own controls.

## Scope

This repository owns reusable AI Engineering system guidance and the professional growth framework needed to apply it: foundations, lifecycle decisions, architecture, assurance, role expectations, competency progression, learning transitions, and evidence standards. It does not own application code, vendor tutorials, generic software-engineering standards, employer-specific job architecture or promotion policy, organization-specific policy, generated output, private business evidence, legal advice, or production-readiness claims.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) before proposing significant work.

For usage questions, use [SUPPORT.md](SUPPORT.md). Report suspected vulnerabilities through [SECURITY.md](SECURITY.md), not a public issue.

## License

Licensed under the [MIT License](LICENSE).
