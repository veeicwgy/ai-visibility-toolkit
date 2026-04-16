---
name: geo-fix-negative
description: >
  Use when the user has a wrong, negative, outdated, or competitor-only LLM answer and needs a structured repair plan. Covers negative-type classification, source tracing, authority coverage, channel-specific repair actions, and regression checks.
---

# geo-fix-negative

Use this skill to turn a bad model answer into a repair backlog instead of reacting ad hoc.

## Trigger

Use this skill when an LLM answer contains any of the following:

1. factual error;
2. negative recommendation against the product;
3. outdated product description;
4. competitor-only recommendation in a strategic query.

## Workflow

### 1. Classify the problem

Assign the answer to one of four types: information error, negative evaluation, outdated information, or competitor insertion.

### 2. Trace the likely source

Collect cited links when available. If links are missing, list the highest-probability authority and community sources that may be shaping the answer.

### 3. Choose the repair path

| Type | Primary action |
|---|---|
| Information error | correct source pages and publish authority coverage |
| Negative evaluation | reframe suitable scenarios and publish comparison content |
| Outdated information | add versioned updates and refresh FAQ or changelog pages |
| Competitor insertion | build comparison and alternative-query coverage |

### 4. Plan regression checks

Set the exact queries, models, and time window for validating whether the answer improves.

## Outputs

| Output | Description |
|---|---|
| Problem type | one of the four negative categories |
| Repair actions | source fixes, content moves, authority pages, feedback actions |
| Regression plan | repeat checks for the affected queries |

## Handoff

Preserve the bad answer, its classification, the suspected sources, and the repair actions already completed.

## Next Best Skill

If the next task is to quality-check the newly repaired content, use `geo-content-check`.
