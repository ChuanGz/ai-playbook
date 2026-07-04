# Maintenance Policy

This policy keeps the playbook useful as models, protocols, regulations, and engineering practice change. It governs repository content; it does not impose policy on consuming systems.

## Content states

| State | Meaning | Required evidence |
|---|---|---|
| Draft | Useful for review but incomplete or not yet exercised across contexts | Named gap, bounded claims, and review owner |
| Stable | Suitable as the current repository recommendation | Clear scope, alternatives, failure modes, verification, and maintained sources |
| Deprecated | Retained temporarily because readers may still depend on it | Replacement link, reason, deprecation date, and removal condition |

The documentation index is the source of truth for document state. A file is not stable merely because it is on `main`.

## Review triggers

Review affected guidance when any of these occur:

- a referenced specification, threat model, or major dependency changes materially;
- implementation evidence contradicts a recommendation;
- a term or contract changes meaning;
- a security incident exposes a missing or ineffective control;
- a document has not been reviewed for 12 months;
- a maintainer can no longer explain the problem the document solves.

Time-based review does not require rewriting stable content. It requires confirming sources, links, boundaries, and continued decision value.

Section indexes record the current content state. Canonical documents record their own last-reviewed date. A review that changes neither guidance nor evidence may update the date with a commit explaining what was checked.

## Change classes

- **Patch:** clarity, links, examples, or corrections that do not change a decision contract.
- **Minor:** backward-compatible guidance, patterns, or controls.
- **Major:** renamed concepts, removed contracts, reversed recommendations, or changed mandatory gates.

Record user-visible changes in GitHub releases once releases begin. Before the first release, the default branch is explicitly pre-release.

## Deprecation

Do not silently delete stable guidance. Mark it deprecated, identify the replacement, explain the changed conditions, and retain it for at least one minor release unless keeping it creates a security or legal risk. Remove it when the stated condition is met.

## Ownership and evidence

The accepting maintainer owns repository consistency. Contributors own the accuracy and provenance of their change. External references must be public, primary where practical, versioned or dated when they can drift, and clearly separated from this repository's interpretation.

## Maintenance checks

A maintenance change passes when:

- navigation, maturity state, and affected terminology agree;
- Markdown, internal links, external links, and repository-hygiene checks pass;
- no private evidence, machine output, unsupported maturity claim, or stale duplicate is introduced;
- changed guidance identifies its scope, alternatives, failure behavior, and validation;
- deprecations identify a replacement and removal condition.
