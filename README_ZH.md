# Awesome Code Agent Benchmarks（中文）

[English](./README_EN.md) | [中文](./README_ZH.md)

窗口：**2026-05-01 → 2026-08-03** · 厂商官方发版/模型卡里仍在报的 Code Agent 榜  
格式：`名称 | 简介 | 模型与分数 | 榜单链接` · 模型主页见文末  
说明：分数多为厂商自报；**不同 harness / 多 Agent 不可直比**。不含 HumanEval / LiveCodeBench 等单题生成评测。

---

## 榜单

| 名称 | 简介 | 模型与分数 | 榜单链接 |
|------|------|------------|----------|
| **Terminal-Bench 2.1** | 隔离终端中完成多步骤真实任务（写代码、配置、调试、数据处理、ML、安全等）。覆盖厂商最广。 | GPT-5.6 Sol **88.8%**（Sol Ultra 多 Agent **91.9%**, Codex）· Kimi K3 **88.3%** (Kimi Code) · Qwen3.8-Max **86.6%*** · Opus 4.8 **85.0%*** · Grok 4.5 **83.3%** · DeepSeek-V4-Flash **82.7%*** · GLM-5.2 **81.0%** · Gemini 3.6 Flash **78.0%** · Gemini 3.5 Flash **76.2%** · Seed2.1 Pro **71.0%** / Turbo **67.6%** · MiniMax M3 **66.0%** · Flash Preview **63.3** · Pro Preview **67.9** · *Qwen/Flash/Opus 为厂商表；Flash 测自 DeepSeek Harness minimal / max effort* | [tbench.ai/2.1](https://www.tbench.ai/news/terminal-bench-2-1) |
| **DeepSWE v1.1** | 113 个原创长周期 SWE 任务（91 仓 / 5 语言）；人工验证器，降低公开 PR 污染。增长最快的新榜。 | GPT-5.6 Sol **72.7%** · Kimi K3 **67.5%** · Opus 4.8 **59.0%*** · Qwen3.8-Max **56.6%*** · DeepSeek-V4-Flash **54.4%*** · Grok 4.5 **53%** · Gemini 3.6 Flash **49%** · GLM-5.2 **46.2%** · Flash Preview **7.3** · Pro Preview **9.8** · *Qwen 官方表标为 DeepSWE 1.1；0731 表自报 DeepSWE（未标 v1.1）* | [Leaderboard](https://deepswe.datacurve.ai/) · [论文](https://arxiv.org/abs/2607.07946) |
| **SWE-Bench Pro** | 1865 任务 / 41 专业仓；多文件长周期。仍被广泛报，但 OpenAI 审计估计约 **30%** 任务破损，勿作唯一结论。 | *(OpenAI 引述)* Fable 5 **80.0%** · Opus 4.8 **69.2%** · Qwen3.8-Max **67.7%*** · Grok 4.5 **64.7%** · GPT-5.6 Sol **64.6%** · GLM-5.2 **62.1%** · Qwen3.7-Max **60.6%** · MiniMax M3 **59.0%** · Gemini 3.6 Flash **58.7%** / 3.5 Flash **55.1%** | [Scale 榜](https://labs.scale.com/leaderboard/swe_bench_pro_public) · [OpenAI 审计](https://openai.com/index/separating-signal-from-noise-coding-evaluations/) |
| **AA Coding Agent Index v1.1** | 第三方综合指数：通过率 + token + 时延 + 成本。是**模型×harness**组合分。 | GPT-5.6 Sol **80.0** / Terra **77.4** / Luna **74.6** · *(OpenAI 引述)* Fable 5 **77.2** · Opus 4.8 **72.5** · Opus 5 发版强调该指数但无绝对分 | [方法](https://artificialanalysis.ai/methodology/coding-agents-benchmarking) · [排行](https://artificialanalysis.ai/agents/coding-agents) |
| **ProgramBench** | 按自然语言从零构建完整程序（无脚手架/细粒度提示）。 | Kimi K3 **77.8** · GLM-5.2 **63.7** · Seed2.1 Pro `0/1/50.3` · Turbo `0/0/49.4`（官网三字段，未擅自解读） | [programbench.com](https://programbench.com/) |
| **NL2Repo** | 高层需求 → 端到端仓库开发（架构/多文件/交付）。中国厂商更常报。 | Opus 4.8 **69.7*** · Qwen3.8-Max **55.9*** · DeepSeek-V4-Flash **54.2*** · GLM-5.2 **48.9** · Qwen3.7-Max **47.2** · Seed2.1 Pro **47.0** / Turbo **43.7** · Flash/Pro Preview **35.5** · *Qwen/Opus/Flash 为厂商表* | 见文末模型页（榜无统一官网） |
| **Toolathlon-Verified** | 多工具 / MCP Agent（108 题）；**2026-06-30 起 Verified 新系列，不可与旧版混比**。 | **官方独立榜 Pass@1**：[toolathlon.xyz](https://toolathlon.xyz/docs/leaderboard) · Kimi K3 max **76.5** · Opus 4.8 max **76.2** · Muse Spark 1.1 **75.6** · GPT-5.5 xhigh **73.5** · Sonnet 5 max **71.6** · Gemini 3.5 Flash **67.3** · Gemini 3.1 Pro **61.1** · GLM-5.2 max **59.9** · V4-Pro max **55.9** · V4-Flash max **50.9** · *另：Qwen3.8-Max 自报 **72.5**；DeepSeek 0731 自报 Flash **70.3** / Opus 4.8 **76.2**（厂商 harness ≠ 官方 Default Agent）· Kimi 模型卡另报 Fable 5 **77.9** / GPT-5.6 Sol **74.9*** | [Leaderboard](https://toolathlon.xyz/docs/leaderboard) |
| **Cybergym** | 网络安全漏洞复现 / 利用向 Agent 评测。 | GPT-5.6 Sol **~84.5%** *(聚合榜)* · Mythos 5 / Preview **~83–84%** · GPT-5.5 **81.8%** *[OpenAI](https://openai.com/index/introducing-gpt-5-5/)* · Opus 4.8 **~78%** *(Anthropic System Card 口径)* · Opus 4.7 **73.1%** · Seed2.1 Pro **~70%** · GLM-5.1 **~69%** · DeepSeek-V4-Flash **76.7%*** *(0731 自报；同表引 Opus 4.8 **83.1**，与 Anthropic 卡不完全一致)* | [OpenAI GPT-5.5](https://openai.com/index/introducing-gpt-5-5/) · [DeepSeek changelog](https://api-docs.deepseek.com/updates/) |
| **AutomationBench (Public)** | Zapier 端到端业务自动化（销售/市场/运维等）；**以环境终态断言计分**。 | **Zapier 官方榜**：[zapier.com/benchmarks](https://zapier.com/benchmarks) · Opus 5 Max **26.2%** · Opus 5 XHigh **25.1%** · Gemini 3.6 Flash High **19.8%** · GPT-5.6 Sol Max **18.1%** · Fable 5 Max **17.4%** · Opus 4.8 XHigh **17.2%** · *另：Qwen3.8-Max 自报 **27.3**；DeepSeek 0731 表 Flash **25.1** / Opus 4.8 **27.2** / GLM **12.9**（厂商口径可能不同，勿与 Zapier 榜直比）· Kimi 卡另报 K3 **30.8** / Sol **29.7*** | [Zapier AutomationBench](https://zapier.com/benchmarks) |
| **Agents' Last Exam** | Berkeley RDI：长程职业工作流 Agent 考（多行业）；分 Near-Term / Full-Spectrum / Last-Exam 等档。 | **OpenAI GPT-5.6 发版表**：[openai.com/index/gpt-5-6](https://openai.com/index/gpt-5-6/) · Sol **52.7%** · Terra **50.4%** · Luna **50.3%** · GPT-5.5 **46.9%** · Opus 4.8 **45.2%** · Fable 5 **40.5%** · Gemini 3.1 Pro **32.1%** · *Qwen3.8-Max 自报 Pass **27.0%** / Score **52.4**；DeepSeek 0731 表 Flash **25.2** / Opus 4.8 **25.7** / GLM **23.8** 数值量级不同，疑为不同子集/harness，勿混排* | [agents-last-exam.org](https://agents-last-exam.org/) · [论文](https://arxiv.org/abs/2606.05405) · [GPT-5.6](https://openai.com/index/gpt-5-6/) |
| **SWE-Atlas** | 仓库级调试；Seed 标为 Debugging。 | Seed2.1 Pro **35.2** · Turbo **30.6** | 见 [Seed2.1](https://seed.bytedance.com/en/seed2_1) |
| **SWE-Marathon** | 20 个超长周期任务（重建库、编译器、语言服务器、ML 工程等，常需数小时）。 | Kimi K3 **42.0%*** · Grok 4.5 **29.0%** · GLM-5.2 **13.0%** · *K3 为 v1.1 前 H20 校准分支，勿与最终榜混排* | [swe-marathon.org](https://www.swe-marathon.org/) |
| **FrontierSWE** | 超长开放式工程；用 Dominance 等相对指标。 | Kimi K3 **81.2** Dominance · GLM-5.2 **74.4**（2026-06-16 发布口径；Kimi 7/16 重算为 **67.3**）· Qwen3.8-Max **73.5*** | [frontierswe.com](https://www.frontierswe.com/) · [GitHub](https://github.com/Proximal-Labs/frontier-swe) |
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
| Qwen3.8-Max | 2026-08-03 | https://qwen.ai/blog?id=qwen3.8 |
| Qwen3.7-Max / Plus | 2026-05 | https://qwen.ai/blog?id=qwen3.7 |
| DeepSeek-V4-Flash（正式版 / 0731，API public beta） | 2026-07-31 | https://api-docs.deepseek.com/updates/ |
| DeepSeek-V4 Preview（Pro / Flash） | 2026-04-26 | https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash |
