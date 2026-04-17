---
name: geo-monitor-toolkit
description: >
  Use when the user wants a GEO monitoring operating system for a developer tool, API, SDK, or open-source project. Covers keyword matrix and Query Pool design, four-metric monitoring, model-specific content placement, GEO content checks, negative-answer repair, and T+7 or T+14 regression validation.
license: MIT
allowed-tools: Read, Write, Edit, Bash
metadata:
  openclaw:
    emoji: "📈"
    author: "Manus AI"
    homepage: "https://github.com/veeicwgy/geo-monitor-toolkit"
---

# geo-monitor-toolkit

Use this skill as the **main GEO workflow router** for developer tools and open-source products.

## Trigger

Use this skill when the task is any of the following:

1. generate a GEO keyword matrix and Query Pool from product truth;
2. monitor how multiple LLMs mention, recommend, or misunderstand a product;
3. plan model-specific content placement based on datasource patterns;
4. check whether a draft page, FAQ, changelog, or case study is GEO-ready;
5. repair wrong, negative, outdated, or competitor-only answers;
6. verify whether a repair action improved metrics at T+7 or T+14.

## GEO Strategy

Always keep the workflow in this order:

| Stage | Goal |
|---|---|
| Keyword strategy | turn product truth into scenario matrix, three-layer keywords, and Query Pool seeds |
| Monitoring | score mention, positive mention, capability accuracy, and ecosystem accuracy |
| Placement | map each target model to likely datasource channels and publication surfaces |
| Repair | classify bad answers into information error, negative evaluation, outdated information, or competitor insertion |
| Regression | compare follow-up runs and check whether metrics improved after action |

## Input Contract

Prepare as many of the following as possible before execution.

| Input | Examples |
|---|---|
| Product truth | README, docs, changelog, integrations, positioning |
| GEO evidence | raw answers, screenshots, copied responses, cited links |
| Monitoring scope | models, languages, regions, dates, repeated query set |
| Publishing targets | docs, blog, GitHub, Q&A, partner channels |

## Workflow Router

Choose the next sub-skill according to the user's immediate need.

| Situation | Next Skill |
|---|---|
| Need keyword matrix and Query Pool | `geo-keyword-matrix` |
| Need weekly monitoring, evidence logging, and report output | `geo-monitor` |
| Need pre-publish GEO QA for content | `geo-content-check` |
| Need to repair bad answers and define regression checks | `geo-fix-negative` |

## Required Reading Order

For a full GEO program, read these repository documents in sequence:

1. `playbooks/geo-workflow-architecture.md`
2. `playbooks/keyword-strategy.md`
3. `playbooks/monitoring-system.md`
4. `playbooks/model-datasources.md`
5. `playbooks/content-platform-map.md`
6. `playbooks/negative-fix-sop.md`

## Output Contract

Always preserve the following outputs.

| Output | Description |
|---|---|
| Query foundation | scenario matrix, keyword layers, Query Pool |
| Monitoring outputs | raw evidence, score draft, summary, report, leaderboard or overview |
| GEO action plan | content placement priorities and repair backlog |
| Regression record | T+7 and T+14 comparisons after key fixes |

## Handoff Rules

At the end of each run, preserve:

1. which product was optimized;
2. which models and languages were in scope;
3. which queries are reused in weekly tracking;
4. what the top three GEO weaknesses are;
5. what actions are already completed and what still needs validation.
