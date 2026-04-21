![AI Visibility Toolkit](assets/logo.svg)

# AI Visibility Toolkit

> 监控 ChatGPT、Claude、Gemini 等大模型如何描述你的 developer tool、API、SDK 或 open-source 项目。

[![CI](https://github.com/veeicwgy/ai-visibility-toolkit/actions/workflows/ci.yml/badge.svg)](https://github.com/veeicwgy/ai-visibility-toolkit/actions/workflows/ci.yml)
![Release](https://img.shields.io/github/v/release/veeicwgy/ai-visibility-toolkit)
![License](https://img.shields.io/github/license/veeicwgy/ai-visibility-toolkit)

如果你更喜欢 agent workflow，可以直接安装配套的 [ClawHub skill](https://clawhub.ai/veeicwgy/ai-visibility-toolkit)。

**AI Visibility Toolkit** 是一个面向 developer tools、API、SDK 与 open-source 项目的 **AI 可见性监控与修复工作流**。
它不是通用内容生成器，而是一套把 **Query Pool 设计、答案监控、四指标打分、repair loop、activation 分析与 T+7/T+14 回归验证** 串起来的可复现系统。

For English, see [`README.md`](README.md).

## 为什么需要这个仓库

如果你的团队已经开始关注“LLM 会不会提到我、会不会说错我、会不会推荐我、修完后会不会变好”，这个仓库的目标就是把这条链路变成可执行、可复盘、可对比的流程。

| 你要回答的问题 | 这个仓库提供的能力 |
|---|---|
| 模型有没有提到你的产品 | Query Pool + raw responses |
| 提到时是否准确、是否正向 | 四指标打分框架 |
| 应该去哪里修复信息源 | placement / repair 视角 |
| 安装、API 调用、agent 采用有没有改善 | activation metrics + funnel-stage 切片 |
| 修复动作是否真的改善了模型回答 | T+7 / T+14 回归验证 |

## 30 秒开始路径

第一次使用，按这个顺序即可。

```bash
git clone https://github.com/veeicwgy/ai-visibility-toolkit.git
cd ai-visibility-toolkit
bash install.sh
make doctor
bash quickstart.sh
```

## 第一次会先看到什么

第一次跑完后，优先看下面这些输出。

| 输出 | 路径 | 为什么重要 |
|---|---|---|
| 原始回答 | `data/runs/quickstart-run/raw_responses.jsonl` | 查看多模型原始回答证据 |
| 打分草稿 | `data/runs/quickstart-run/score_draft.jsonl` | 进入人工复核与补标流程 |
| 周报快照 | `data/runs/sample-run/weekly_report.md` | 直接理解团队可消费的周报形态 |
| Sciverse 样例摘要 | `data/runs/sciverse-sample-run/summary.json` | 查看 scientific API 场景下的 funnel-stage 切片 |
| 排行榜快照 | `assets/leaderboard-sample.png` | 快速理解默认多模型对比 |

## 新手优先文档

如果你是第一次接触 AI 可见性监控，请先读这几个入口。

| 文档 | 用途 |
|---|---|
| `docs/for-beginners.md` | 5 分钟上手版，先跑通、先看结果 |
| `docs/getting-started.md` | 长版入门，解释输出、模式和团队使用方式 |
| `docs/activation-metrics.md` | 把“被提到”延伸到安装、调用与 agent 采用 |

## 应该选哪种模式

| 你的状态 | 推荐模式 | 入口 |
|---|---|---|
| 没有 API key，只想先看整个流程 | Quickstart replay | `bash quickstart.sh` |
| 已经从外部聊天产品拿到回答，想导入评估 | Manual paste mode | `python -m ai_visibility run --manual-responses ...` |
| 想做真实、持续、多模型监控 | API collection mode | `python -m ai_visibility run --query-pool ... --model-config ...` |

## 核心命令

| 命令 | 作用 |
|---|---|
| `bash install.sh` | 创建 `.venv` 并安装依赖 |
| `make doctor` | 检查 Python、依赖、样例文件与输出目录是否可用 |
| `bash quickstart.sh` | 运行零 API 成本的新手演示 |
| `make sample-report` | 重建样例报告与图表 |
| `make sample-report-sciverse` | 重建 Sciverse API 样例周报 |
| `python -m ai_visibility run ...` | 运行自定义 Query Pool 监控 |

> 兼容说明：旧 CLI 别名仍然保留，方便兼容已有自动化。

## 默认样例输入

| 文件 | 作用 |
|---|---|
| `data/query-pools/mineru-example.json` | 默认 Query Pool 示例 |
| `data/query-pools/sciverse-api-integration-example.json` | scientific API / agent workflow Query Pool 示例 |
| `data/models.sample.json` | 最小单模型配置 |
| `data/models.multi.sample.json` | 默认多模型配置 |
| `data/manual.sample.json` | 最小手工回答样例 |
| `data/manual.multi.sample.json` | 多模型手工回答样例 |

## 仓库定位

请把它理解为：

> **AI Visibility Workflow for Developer Tools**
>
> 它关注的是 **monitoring、scoring、repair、activation 与 regression**，而不是泛化营销文案生成。

## 继续阅读

| 主题 | 路径 |
|---|---|
| 5 分钟上手 | `docs/for-beginners.md` |
| 长版入门 | `docs/getting-started.md` |
| English README | `README.md` |
| 根 skill | `SKILL.md` |
| Scientific product visibility | `playbooks/scientific-product-visibility.md` |
