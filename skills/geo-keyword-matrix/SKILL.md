---
name: geo-keyword-matrix
description: >
  Use when the user wants to turn a product description into a GEO keyword matrix and Query Pool. Covers task-scenario mapping, multilingual keyword expansion, three-level clustering, competitor comparison queries, and model-validation loops for developer tools and open-source projects.
---

# geo-keyword-matrix

Use this skill to build the keyword foundation for GEO monitoring and content planning.

## Trigger

Use this skill when the user has product context but does not yet have a robust Query Pool.

## Workflow

### 1. Extract product truth

List the product category, main user jobs, core capabilities, entity relationships, languages, and key competitors.

### 2. Build scenario matrix

Translate user jobs into realistic search or prompt language in Chinese and English.

### 3. Cluster into three layers

| Layer | Purpose |
|---|---|
| Core | broad anchor terms |
| Scenario | high-intent problem-solution terms |
| Long-tail | high-conversion tutorial and comparison terms |

### 4. Turn keywords into Query Pool seeds

Create brand, capability, ecosystem, competitor, and negative queries.

### 5. Validate with model responses

Check whether the target product appears, how it appears, and which competitor dominates each scene.

## Outputs

| Output | Description |
|---|---|
| Scenario matrix | user jobs to bilingual query language |
| Three-layer keyword set | core, scenario, and long-tail clusters |
| Query Pool seeds | reusable monitoring prompts |
| Validation notes | where the brand is missing or weak |

## Handoff

Preserve the product truth summary, top scenarios, priority keywords, and Query Pool version.

## Next Best Skill

After the Query Pool is ready, use `geo-monitor`.
