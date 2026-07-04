# References

These primary and community-maintained references inform the playbook's terminology and review questions. They do not make every recommendation in this repository a requirement of the referenced framework, and their inclusion does not certify compliance.

## Risk and governance

- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework): voluntary risk-management structure for governing, mapping, measuring, and managing AI risk.
- [NIST AI 600-1, Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf): generative-AI-specific risks and actions that complement the AI RMF.

## Application and agent security

- [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/): risk categories including prompt injection, sensitive-information disclosure, supply-chain risk, excessive agency, and unbounded consumption.

## Protocols and observability

- [Model Context Protocol specification](https://modelcontextprotocol.io/specification/): protocol contracts and versioned guidance for clients and servers. Use the version implemented by the consuming system.
- [OpenTelemetry semantic conventions](https://opentelemetry.io/docs/specs/semconv/): shared telemetry naming conventions. Generative-AI conventions may evolve; pin and record the version used by an implementation.

## Use of references

When adding guidance derived from an external source:

1. Link the primary source and identify the relevant version or access date when it can change materially.
2. Separate the source's requirement from this playbook's interpretation.
3. State the conditions, tradeoffs, and evidence needed to apply the guidance.
4. Do not convert a framework category into a claim that a system is secure, compliant, or production-ready.
