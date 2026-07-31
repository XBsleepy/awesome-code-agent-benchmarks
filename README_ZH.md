# Awesome Code Agent Benchmarks（中文）

[English](./README_EN.md) | [中文](./README_ZH.md)

窗口：**2026-05-01 → 2026-07-31** · 厂商官方发版/模型卡里仍在报的 Code Agent 榜  
格式：`名称 | 简介 | 模型与分数 | 榜单链接` · 模型主页见文末  
说明：分数多为厂商自报；**不同 harness / 多 Agent 不可直比**。不含 HumanEval / LiveCodeBench 等单题生成评测。

---

## 榜单

| 名称 | 简介 | 模型与分数 | 榜单链接 |
|------|------|------------|----------|
| **Terminal-Bench 2.1** | 隔离终端中完成多步骤真实任务（写代码、配置、调试、数据处理、ML、安全等）。覆盖厂商最广。 | GPT-5.6 Sol **88.8%**（Sol Ultra 多 Agent **91.9%**, Codex）· Kimi K3 **88.3%** (Kimi Code) · Grok 4.5 **83.3%** · DeepSeek-V4-Flash **82.7%*** · GLM-5.2 **81.0%** (Terminus-2) / **82.7%** (Claude Code) · Gemini 3.6 Flash **78.0%** · Gemini 3.5 Flash **76.2%** · Seed2.1 Pro **71.0%** / Turbo **67.6%** · MiniMax M3 **66.0%** · Opus 4.8 有报但正文无绝对分 · *Flash 正式版：DeepSeek Harness minimal / max effort* | [tbench.ai/2.1](https://www.tbench.ai/news/terminal-bench-2-1) |
| **DeepSWE v1.1** | 113 个原创长周期 SWE 任务（91 仓 / 5 语言）；人工验证器，降低公开 PR 污染。增长最快的新榜。 | GPT-5.6 Sol **72.7%** · Kimi K3 **67.5%** (Kimi Code; mini-SWE-agent **67.3%**) · DeepSeek-V4-Flash **54.4%*** · Grok 4.5 **53%** · Gemini 3.6 Flash **49%** · GLM-5.2 **46.2%** · *Flash 正式版自报 DeepSWE（changelog 未标 v1.1）* | [Leaderboard](https://deepswe.datacurve.ai/) · [论文](https://arxiv.org/abs/2607.07946) |
| **SWE-Bench Pro** | 1865 任务 / 41 专业仓；多文件长周期。仍被广泛报，但 OpenAI 审计估计约 **30%** 任务破损，勿作唯一结论。 | Grok 4.5 **64.7%** · GPT-5.6 Sol **64.6%** · GLM-5.2 **62.1%** · Qwen3.7-Max **60.6%** · MiniMax M3 **59.0%** · Gemini 3.6 Flash **58.7%** / 3.5 Flash **55.1%** · *(OpenAI 引述)* Fable 5 **80.0%** · Opus 4.8 **69.2%** | [Scale 榜](https://labs.scale.com/leaderboard/swe_bench_pro_public) · [OpenAI 审计](https://openai.com/index/separating-signal-from-noise-coding-evaluations/) |
| **AA Coding Agent Index v1.1** | 第三方综合指数：通过率 + token + 时延 + 成本。是**模型×harness**组合分。 | GPT-5.6 Sol **80.0** / Terra **77.4** / Luna **74.6** · *(OpenAI 引述)* Fable 5 **77.2** · Opus 4.8 **72.5** · Opus 5 发版强调该指数但无绝对分 | [方法](https://artificialanalysis.ai/methodology/coding-agents-benchmarking) · [排行](https://artificialanalysis.ai/agents/coding-agents) |
| **ProgramBench** | 按自然语言从零构建完整程序（无脚手架/细粒度提示）。 | Kimi K3 **77.8** · GLM-5.2 **63.7** · Seed2.1 Pro `0/1/50.3` · Turbo `0/0/49.4`（官网三字段，未擅自解读） | [programbench.com](https://programbench.com/) |
| **NL2Repo** | 高层需求 → 端到端仓库开发（架构/多文件/交付）。中国厂商更常报。 | DeepSeek-V4-Flash **54.2*** · GLM-5.2 **48.9** · Seed2.1 Pro **47.0** / Turbo **43.7** · *(GLM 引述)* Qwen3.7-Max **47.2** · *Flash 正式版* | 见文末模型页（榜无统一官网） |
| **SWE-Atlas** | 仓库级调试；Seed 标为 Debugging。 | Seed2.1 Pro **35.2** · Turbo **30.6** | 见 [Seed2.1](https://seed.bytedance.com/en/seed2_1) |
| **SWE-Marathon** | 20 个超长周期任务（重建库、编译器、语言服务器、ML 工程等，常需数小时）。 | Kimi K3 **42.0%*** · Grok 4.5 **29.0%** · GLM-5.2 **13.0%** · *K3 为 v1.1 前 H20 校准分支，勿与最终榜混排* | [swe-marathon.org](https://www.swe-marathon.org/) |
| **FrontierSWE** | 超长开放式工程；用 Dominance 等相对指标。 | Kimi K3 **81.2** Dominance · GLM-5.2 **74.4**（2026-06-16 发布口径；Kimi 7/16 重算为 **67.3**） | [frontierswe.com](https://www.frontierswe.com/) · [GitHub](https://github.com/Proximal-Labs/frontier-swe) |
| **Frontier-Bench v0.1** | Scale/Harbor 高难度通用 Agent 环境（曾称 TB3 方向）。≠ Cognition FrontierCode。 | Claude Opus 5：宣称超 Opus 4.8 两倍 / 新 SOTA；发版页**无绝对分** | [Scale 介绍](https://labs.scale.com/blog/frontier-bench-harder-tasks-for-better-agents) · [Harbor](https://hub.harborframework.com/datasets/frontier-bench/frontier-bench/latest) |
| **CursorBench 3.2** | Cursor 官方 IDE Agent 评测：真实会话中的歧义、多文件任务；同时报分 / 成本 / token / steps。取各模型**最佳 effort**。 | Fable 5 Max **70.5%** · Opus 5 Max **70.0%** · GPT-5.6 Sol Max **67.2%** · Grok 4.5 High **66.7%*** · GPT-5.6 Terra Max **64.9%** · Opus 4.8 Max **62.3%** · Sonnet 5 Max **61.5%** · GPT-5.6 Luna Max **61.1%** · Kimi K3 Max **60.8%** · Composer 2.5 **56.1%** · GLM 5.2 Max **55.0%** · Gemini 3.6 Flash High **53.5%** · Kimi K2.7 Code **49.7%** · Gemini 3.5 Flash **48.8%** · *Grok：训练含早期 Cursor 代码快照，分数存疑* | [CursorBench](https://cursor.com/cn/cursorbench) · [方法](https://cursor.com/blog/cursorbench) |
| **FrontierCode 1.1** | Cognition：功能 + 可合并性/风格/回归（维护者是否愿合 PR）。 | Fable 5：宣称最高 · Opus 5：接近 Fable、成本约一半 · Sonnet 5：已入 1.1 榜 | [排行](https://cognition.com/frontiercode) · [1.1](https://cognition.com/blog/frontier-code-1.1) |

### Preview 对照（DeepSeek-V4，2026-04-26）

| 名称 | 简介 | 模型与分数 | 链接 |
|------|------|------------|------|
| Terminal-Bench **2.0** / SWE Verified / Pro / Multilingual | Preview 仍用「TB2.0 + SWE 三件套」；正式 Flash（0731）已改报 TB2.1 / DeepSWE / NL2Repo | V4-Pro Max：TB2.0 **67.9** · Verified **80.6** · Pro **55.4** · Multilingual **76.2** · V4-Flash Max：Verified **79.0** · Pro **52.6** · TB2.0 **56.9** | [HF V4-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash) |

---

## 模型主页

| 模型 | 日期 | 页面 |
|------|------|------|
| OpenAI GPT-5.6 | 2026-07-09 | https://openai.com/index/gpt-5-6/ |
| Anthropic Claude Opus 4.8 | 2026-05-28 | https://www.anthropic.com/news/claude-opus-4-8 |
| Anthropic Claude Fable 5 / Mythos 5 | 2026-06-09 | https://www.anthropic.com/news/claude-fable-5-mythos-5 |
| Anthropic Claude Sonnet 5 | 2026-06-30 | https://www.anthropic.com/news/claude-sonnet-5 |
| Anthropic Claude Opus 5 | 2026-07-24 | https://www.anthropic.com/news/claude-opus-5 |
| Google Gemini 3.5 Flash | 2026-05-19 | https://deepmind.google/models/model-cards/gemini-3-5-flash/ |
| Google Gemini 3.6 Flash | 2026-07-21 | https://deepmind.google/models/gemini/flash/ |
| xAI Grok 4.5 | 2026-07-16 | https://x.ai/news/grok-4-5 |
| Moonshot Kimi K3 | 2026-07-27 | https://huggingface.co/moonshotai/Kimi-K3 |
| Z.ai GLM-5.2 | 2026-06-16 | https://huggingface.co/zai-org/GLM-5.2-FP8 |
| 字节 Seed2.1 / 豆包 | 2026-06-23 | https://seed.bytedance.com/en/seed2_1 · [发版博客](https://seed.bytedance.com/en/blog/seed2-1-officially-released-advancing-ai-productivity) |
| MiniMax M3 | 2026-06-01 | https://www.minimax.io/blog/minimax-m3 |
| Qwen3.7-Max / Plus | 2026-05 | https://qwen.ai/blog?id=qwen3.7 |
| DeepSeek-V4-Flash（正式版 / 0731，API public beta） | 2026-07-31 | https://api-docs.deepseek.com/updates/ |
| DeepSeek-V4 Preview（Pro / Flash） | 2026-04-26 | https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash |
