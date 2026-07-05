# References

| Learning metadata | Value |
|---|---|
| Career level | L2 Practitioner+ |
| Topics | standards, source-validation |
| Purpose | Verify claims against maintained primary sources |
| Importance | Important |

| Field | Value |
|---|---|
| Status | Stable |
| Audience | Readers validating terminology, controls, and external source basis |
| Decision supported | Which public sources inform a material repository claim |
| Applies when | Guidance relies on an external framework, specification, or convention |
| Does not apply when | A link is offered as general reading without supporting a claim |
| Expected output | Public source, version or review date, informed claim, and bounded interpretation |
| Evidence basis | Primary public sources listed below |
| Last reviewed | 2026-07-04 |

These official and community-maintained sources help a reader verify terminology, protocols, and risk categories. They are optional follow-up reading: start with the short introduction named in each section, then open a specification only when implementing or reviewing that boundary.

The links intentionally avoid academic papers. A source appears here only when it explains a concept used by the playbook or supports a concrete review question. Inclusion does not turn every playbook recommendation into a requirement of that source and does not certify compliance.

## Start with the approachable sources

| When you need to understand... | Read this first | Why it helps |
|---|---|---|
| AI risk as an engineering process | [NIST AI RMF Playbook](https://airc.nist.gov/airmf-resources/playbook/) | Organizes practical actions around govern, map, measure, and manage |
| Common LLM application failures | [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) | Names recognizable failure categories and gives prevention guidance |
| What MCP connects | [MCP introduction](https://modelcontextprotocol.io/docs/getting-started/intro) | Explains hosts, clients, servers, tools, resources, and prompts before the protocol detail |
| What observability means | [OpenTelemetry observability primer](https://opentelemetry.io/docs/concepts/observability-primer/) | Introduces traces, metrics, and logs in operational language |

Use these pages to understand the idea. Use the more exact references below when recording a decision, implementing a protocol, or validating a control.

## Risk and governance

- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework), reviewed 2026-07-04: voluntary risk-management structure for governing, mapping, measuring, and managing AI risk.
- [NIST AI RMF Playbook](https://airc.nist.gov/airmf-resources/playbook/), reviewed 2026-07-04: suggested actions for applying the framework. Start here for examples; use the framework when exact category language matters.
- [NIST AI 600-1, Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf), reviewed 2026-07-04: generative-AI-specific risks and actions that complement the AI RMF.

## Application and agent security

- [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/), reviewed 2026-07-04: risk categories including prompt injection, sensitive-information disclosure, supply-chain risk, excessive agency, and unbounded consumption.

## Protocols and observability

- [MCP introduction](https://modelcontextprotocol.io/docs/getting-started/intro), reviewed 2026-07-04: an approachable explanation of the protocol's participants and primitives.
- [Model Context Protocol specification](https://modelcontextprotocol.io/specification/), reviewed 2026-07-04: protocol contracts and versioned guidance for implementers. Use the version implemented by the consuming system.
- [OpenTelemetry observability primer](https://opentelemetry.io/docs/concepts/observability-primer/), reviewed 2026-07-04: an accessible introduction to telemetry and observability.
- [OpenTelemetry semantic conventions](https://opentelemetry.io/docs/specs/semconv/), reviewed 2026-07-04: exact shared telemetry names for implementers. Generative-AI conventions may evolve; pin and record the version used by an implementation.

## Use of references

When adding guidance derived from an external source:

1. Link the primary source and identify the relevant version or access date when it can change materially.
2. Separate the source's requirement from this playbook's interpretation.
3. State the conditions, tradeoffs, and evidence needed to apply the guidance.
4. Do not convert a framework category into a claim that a system is secure, compliant, or production-ready.

Prefer an official introduction or worked example over a research paper when both support the same reader need. Link a dense specification only when precision, compatibility, or conformance requires it.
