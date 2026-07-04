# Evidence Policy

This policy defines how claims are supported and how external material enters the playbook.

## Evidence order

Prefer evidence in this order:

1. reproducible behavior or maintained contracts in the affected system;
2. reviewed incidents, experiments, evaluation results, and operating evidence;
3. explicit requirements, constraints, and accepted decisions;
4. primary specifications, standards, and authoritative documentation;
5. transferable engineering reasoning with assumptions labeled.

Popularity, vendor marketing, fluent generated text, unsourced summaries, and repository file counts are not evidence of effectiveness.

## Citation placement

Place a source near the material claim it supports. A generic references section does not establish which statement came from which source.

For a source likely to change, record the relevant version or review date. Link to the primary source rather than a search result or secondary summary when practical.

## Source record

For material external guidance, capture:

- source title and public URL;
- owner or standards body;
- relevant version or publication date;
- date reviewed;
- claim or decision informed;
- repository interpretation and its boundary.

Do not copy extensive source text. Summarize the relevant constraint and preserve attribution.

## Evidence classification

- **Observed:** directly reproduced or measured in a stated context.
- **Source-backed:** supported by a cited specification or authoritative publication.
- **Reasoned:** derived from engineering constraints with assumptions visible.
- **Illustrative:** used only to expose a decision or failure mode.
- **Unknown:** material evidence is unavailable; the gap and owner are explicit.

Do not present reasoned or illustrative content as observed production truth.

## Private and sensitive evidence

Do not publish credentials, personal data, customer information, private business evidence, internal repository history, machine paths, or confidential incidents. Replace them with public, minimal, non-identifying evidence only when the claim remains valid. Otherwise omit the claim.

## Review gate

- [ ] Material claims identify their evidence class.
- [ ] Public sources are authoritative, relevant, and linked near the claim.
- [ ] Drift-prone sources include a version or review date.
- [ ] Repository interpretation is separated from source requirements.
- [ ] No private, sensitive, inaccessible, or fabricated evidence is required.
- [ ] Uncertainty and evidence gaps are visible.
