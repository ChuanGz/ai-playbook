# Example: Bounded Research Agent

| Field | Value |
|---|---|
| Status | Stable, illustrative |
| Audience | Engineers and reviewers deciding whether a research task justifies an agent |
| Decision supported | How to bound read-only planning, retrieval, replanning, and termination |
| Applies when | Source discovery and comparison require runtime choices within a read-only scope |
| Does not apply when | A fixed search sequence or deterministic query can satisfy the outcome |
| Expected output | Cited draft, evidence manifest, limitations, or bounded insufficient-evidence result |
| Evidence basis | [Agent Runtime](../architecture/agent-runtime.md) and [Evaluation and Release](../assurance/evaluation-and-release.md) |
| Last reviewed | 2026-07-04 |

This illustrative workflow shows an agent that gathers public sources and drafts a comparison. It cannot publish, purchase, message, or access private systems.

## Why this shape

An agent is selected because source discovery may require revising search terms and evidence coverage at runtime. A fixed workflow remains preferable when the source set and query sequence are known. Multiple agents were rejected because isolated roles or parallel authority do not add demonstrated value to this bounded task.

## Goal and boundary

Produce a cited comparison for a reviewer-defined question within 10 minutes, 20 retrieval operations, two replans, and a fixed spend budget.

Allowed capabilities:

- search configured public sources;
- retrieve approved pages;
- extract claims and citations;
- draft a comparison artifact.

Denied capabilities include authentication to private services, file-system access outside the run workspace, code execution, communication, and external side effects.

## Plan

1. Restate question, decision criteria, and missing constraints.
2. Build a source plan across at least two independent primary sources where available.
3. Retrieve, classify authority and freshness, and extract cited claims.
4. Identify conflict, missing evidence, and uncertainty.
5. Draft the comparison and evidence manifest.
6. Stop for human review.

## Termination

Terminate on completed draft, denial, cancellation, deadline, spend limit, retrieval limit, second unsuccessful replan, or inability to find sufficient authorized evidence.

## Trace

Record request, plan versions, searches, retrieved revisions, selected passages, model and prompt versions, policy decisions, budget use, failures, and final artifact. Do not retain hidden reasoning or unnecessary page content.

## Failure cases

- source instructions attempt to change the goal;
- sources conflict;
- only secondary or stale sources exist;
- retrieval loops on equivalent queries;
- budget or deadline is reached;
- a source requires authentication;
- citation no longer resolves.

## Failure demonstrated

Without explicit bounds, a research agent can loop over equivalent queries, consume unbounded resources, treat source instructions as authority, or overstate conclusions when evidence is weak.

## Evidence required

Evaluation must show termination at every limit, refusal of private or effectful capabilities, citation resolution, conflict handling, injection isolation, budget accounting, and accurate insufficient-evidence output.

## Decision-change trigger

Reconsider the design if the agent gains private access, code execution, communication, publication, external effects, broader delegation, or a materially different evidence standard.

## Pass condition

The agent remains read-only, stops within every bound, labels insufficient evidence, cites reviewable passages, and cannot reinterpret retrieved text as authority to expand its capabilities.
