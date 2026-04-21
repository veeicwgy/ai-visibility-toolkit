---
name: visibility-monitor
description: >
  Use when the user wants to run or design AI visibility monitoring for a developer tool, API, SDK, or open-source project. Covers Query Pool execution, evidence logging, four-metric scoring, weekly reporting, anomaly detection, and action prioritization across multiple LLMs and languages.
---

# visibility-monitor

Use this skill to turn repeated model checks into a consistent visibility monitoring workflow.

## Trigger

Use this skill when the user already has, or is ready to create, a Query Pool and wants to know:

1. whether the product is being mentioned;
2. whether mentions are positive, neutral, or negative;
3. whether the model understands the product's capabilities;
4. whether the model understands the product's ecosystem and integrations.

## Quick Start

### Choose the right runner

| Runner | API Type | Works with | Use when |
|---|---|---|---|
| `scripts/run_monitor.py` | Responses API | OpenAI models only | GPT-4o, GPT-4.1 and variants |
| `scripts/run_chat_completions.py` | Chat Completions API | Any OpenAI-compatible provider | Claude, Gemini, DeepSeek, Qwen, MiniMax, GLM, or any gateway |

**For multi-model coverage across providers, always use `run_chat_completions.py`.**

```bash
export OPENAI_API_KEY=<your-key>
export OPENAI_BASE_URL=<gateway-url>

python scripts/run_chat_completions.py \
    --query-pool data/query-pools/mineru-example.json \
    --model-config data/models.sample.json \
    --out-dir data/runs/my-run
```

Then annotate scores and generate the report:

```bash
python -m ai_visibility report \
    --input data/runs/my-run/raw_responses.jsonl \
    --output-dir data/runs/my-run
```

## Outputs

| Output | Description |
|---|---|
| Monitoring summary | overall run snapshot |
| Four-metric score table | mention, positive mention, capability, ecosystem |
| Anomaly list | urgent issues by model and query |
| Action backlog | next content, repair, and verification moves |

## Next Best Skill

If the main issue is missing or weak content, use `visibility-content-check`.

If the main issue is negative or wrong answers, use `visibility-repair`.
