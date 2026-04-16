---
name: geo-content-check
description: >
  Use when the user wants to quality-check a draft before publishing it for GEO impact. Covers citation friendliness, Q&A structure, factual density, entity clarity, authority signals, and release readiness for developer-tool or open-source content.
---

# geo-content-check

Use this skill to decide whether a draft is ready to influence LLM answers.

## Trigger

Use this skill before publishing a tutorial, comparison article, FAQ page, changelog summary, or product page update.

## Quick Start

Prepare the draft, the target models, and the official entity truth.

## Workflow

### 1. Check structure

Confirm the draft contains a clear title, short opening definition, section hierarchy, and at least one extractable block such as Q&A, comparison table, checklist, or code sample.

### 2. Check facts and authority signals

Confirm the draft includes version, official links, product name, and any claims that need direct evidence.

### 3. Check entity clarity

Verify that the product name, organization name, repository name, domain, SDK names, and hosted service names are not mixed together.

### 4. Check citation friendliness

Prefer answer-shaped sections, direct comparisons, complete code examples, and concise capability statements.

### 5. Return a go / revise decision

Summarize the biggest blockers and the exact fixes required before publishing.

## Outputs

| Output | Description |
|---|---|
| GEO readiness verdict | go, revise, or block |
| Issue list | missing signals, weak structure, entity ambiguity, thin evidence |
| Revision priorities | top fixes before publish |

## Handoff

Preserve the final verdict, the top three issues, and the target channels or models.

## Next Best Skill

If the draft is blocked because of negative framing or wrong facts, use `geo-fix-negative`.
