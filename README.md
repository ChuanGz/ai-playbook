# AI Engineering Playbook

A vendor-neutral playbook for engineers and technical leaders who must decide where AI belongs, control its failure modes, and require evidence before adoption or release.

## Status

Version 1.0 provides a stable initial documentation set for AI system decisions, adoption, delivery, retrieval, tools, MCP, agents, evaluation, security, and operations. Stable means the repository's current recommendation under its stated conditions; it does not certify any consuming system.

The playbook documents decision controls and reference contracts. It is not a compliance framework, certification, complete security standard, or proof that any described system is production-ready.

## Start here

- [Documentation index](docs/README.md): enter by task and understand how the documents fit together.
- [Playbook diagrams](docs/diagrams.md): see the decision lifecycle and capability/evidence map.
- [System decision guide](docs/foundations/system-decision-guide.md): decide whether the solution needs deterministic software, model inference, retrieval, tools, a workflow, or an agent.
- [Eight-milestone roadmap](TODO.md): see completed foundations, remaining work, and release gates.
- [Maintenance policy](MAINTENANCE.md): understand content maturity, review triggers, versioning, and deprecation.
- [Changelog](CHANGELOG.md): review user-visible release changes.

## Setup

No build or runtime setup is required. Read the Markdown files directly.

## Usage

Start with the [AI system decision guide](docs/foundations/system-decision-guide.md), then use the [documentation index](docs/README.md) to apply the relevant controls. Record architecture decisions, thresholds, tests, approvals, and operational evidence in the consuming project; do not treat this repository as evidence that a system passed its own controls.

## Scope

This repository owns reusable AI Engineering decision guidance and reference contracts. It does not own application code, vendor tutorials, generic software-engineering standards, career frameworks, organization-specific policy, generated output, private business evidence, legal advice, or production-readiness claims.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) before proposing significant work.

For usage questions, use [SUPPORT.md](SUPPORT.md). Report suspected vulnerabilities through [SECURITY.md](SECURITY.md), not a public issue.

## License

Licensed under the [MIT License](LICENSE).
