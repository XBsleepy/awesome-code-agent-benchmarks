# Awesome Code Agent Benchmarks (EN)

[English](./README_EN.md) | [中文](./README_ZH.md)

Window: **2026-05-01 → 2026-07-31** · Code-agent benches still scored in vendor posts / model cards  
Format: `name | intro | models + scores | bench link` · Model pages at the bottom  
Notes: mostly vendor-reported; **different harness / multi-agent ≠ comparable**. Excludes single-problem codegen (HumanEval, LiveCodeBench, …).

---

## Benchmarks

| Name | Intro | Models + scores | Bench link |
|------|--------|-----------------|------------|
| **Terminal-Bench 2.1** | Hard multi-step tasks in a sandboxed terminal (code, setup, debug, data, ML, security). Broadest vendor coverage. | GPT-5.6 Sol **88.8%** (Sol Ultra multi-agent **91.9%**, Codex) · Kimi K3 **88.3%** (Kimi Code) · Opus 4.8 **85.0%*** · Grok 4.5 **83.3%** · DeepSeek-V4-Flash **82.7%*** · GLM-5.2 **81.0%** · Gemini 3.6 Flash **78.0%** · Gemini 3.5 Flash **76.2%** · Seed2.1 Pro **71.0%** / Turbo **67.6%** · MiniMax M3 **66.0%** · Flash Preview **63.3** · Pro Preview **67.9** · *Flash/Opus from DeepSeek 0731 table; Flash = DeepSeek Harness minimal / max effort* | [tbench.ai/2.1](https://www.tbench.ai/news/terminal-bench-2-1) |
| **DeepSWE v1.1** | 113 original long-horizon SWE tasks (91 repos / 5 langs); human verifiers; low public-PR contamination. Fastest-rising new bench. | GPT-5.6 Sol **72.7%** · Kimi K3 **67.5%** · Opus 4.8 **59.0%*** · DeepSeek-V4-Flash **54.4%*** · Grok 4.5 **53%** · Gemini 3.6 Flash **49%** · GLM-5.2 **46.2%** · Flash Preview **7.3** · Pro Preview **9.8** · *0731 table labels “DeepSWE” (not v1.1)* | [Leaderboard](https://deepswe.datacurve.ai/) · [paper](https://arxiv.org/abs/2607.07946) |
| **SWE-Bench Pro** | 1,865 tasks / 41 pro repos; multi-file, long-horizon. Still widely reported; OpenAI audit estimates ~**30%** broken/unreliable — not sole evidence. | Grok 4.5 **64.7%** · GPT-5.6 Sol **64.6%** · GLM-5.2 **62.1%** · Qwen3.7-Max **60.6%** · MiniMax M3 **59.0%** · Gemini 3.6 Flash **58.7%** / 3.5 Flash **55.1%** · *(OpenAI cite)* Fable 5 **80.0%** · Opus 4.8 **69.2%** | [Scale LB](https://labs.scale.com/leaderboard/swe_bench_pro_public) · [OpenAI audit](https://openai.com/index/separating-signal-from-noise-coding-evaluations/) |
| **AA Coding Agent Index v1.1** | Third-party composite: pass rate + tokens + latency + cost. **Model × harness** score. | GPT-5.6 Sol **80.0** / Terra **77.4** / Luna **74.6** · *(OpenAI cite)* Fable 5 **77.2** · Opus 4.8 **72.5** · Opus 5 highlights index, no absolute on page | [method](https://artificialanalysis.ai/methodology/coding-agents-benchmarking) · [ranking](https://artificialanalysis.ai/agents/coding-agents) |
| **ProgramBench** | Build a full program from NL (no scaffold / fine hints). | Kimi K3 **77.8** · GLM-5.2 **63.7** · Seed2.1 Pro `0/1/50.3` · Turbo `0/0/49.4` (official 3-field; not reinterpreted) | [programbench.com](https://programbench.com/) |
| **NL2Repo** | High-level NL → end-to-end repo (arch / multi-file / ship). Heavier use by CN labs. | Opus 4.8 **69.7*** · DeepSeek-V4-Flash **54.2*** · GLM-5.2 **48.9** · Seed2.1 Pro **47.0** / Turbo **43.7** · Qwen3.7-Max **47.2** *(GLM cite)* · Flash/Pro Preview **35.5** · *Opus/Flash from 0731 table* | See model pages (no single public site) |
| **Toolathlon-Verified** | Multi-tool / MCP agents (108 tasks). **Verified series since 2026-06-30 — not comparable to pre-Verified Toolathlon.** | **Official independent Pass@1** ([LB](https://toolathlon.xyz/docs/leaderboard)): Kimi K3 max **76.5** · Opus 4.8 max **76.2** · Muse Spark 1.1 **75.6** · GPT-5.5 xhigh **73.5** · Sonnet 5 max **71.6** · Gemini 3.5 Flash **67.3** · Gemini 3.1 Pro **61.1** · GLM-5.2 max **59.9** · V4-Pro max **55.9** · V4-Flash max **50.9** · *Also: DeepSeek 0731 self-report Flash **70.3** (own harness ≠ official Default) · Kimi card cites Fable 5 **77.9** / GPT-5.6 Sol **74.9*** | [toolathlon.xyz LB](https://toolathlon.xyz/docs/leaderboard) |
| **Cybergym** | Cybersecurity vuln reproduction / exploit-style agent eval. | GPT-5.6 Sol **~84.5%** *(aggregator)* · Mythos 5/Preview **~83–84%** · GPT-5.5 **81.8%** *[OpenAI](https://openai.com/index/introducing-gpt-5-5/)* · Opus 4.8 **~78%** *(Anthropic System Card)* · Opus 4.7 **73.1%** · Seed2.1 Pro **~70%** · GLM-5.1 **~69%** · DeepSeek-V4-Flash **76.7%*** *(0731 self-report; same table cites Opus 4.8 **83.1**, may disagree with Anthropic card)* | [OpenAI GPT-5.5](https://openai.com/index/introducing-gpt-5-5/) · [DeepSeek changelog](https://api-docs.deepseek.com/updates/) |
| **AutomationBench (Public)** | Zapier end-to-end business automation; **final world-state assertions**. | **Zapier official** ([LB](https://zapier.com/benchmarks)): Opus 5 Max **26.2%** · Opus 5 XHigh **25.1%** · Gemini 3.6 Flash High **19.8%** · GPT-5.6 Sol Max **18.1%** · Fable 5 Max **17.4%** · Opus 4.8 XHigh **17.2%** · *Also: DeepSeek 0731 Flash **25.1** / Opus 4.8 **27.2** / GLM **12.9** (likely different protocol — don’t mix) · Kimi card cites K3 **30.8** / Sol **29.7*** | [Zapier AutomationBench](https://zapier.com/benchmarks) |
| **Agents' Last Exam** | Berkeley RDI long-horizon professional workflows (multi-industry); tiers Near-Term / Full-Spectrum / Last-Exam. | **OpenAI GPT-5.6 table** ([post](https://openai.com/index/gpt-5-6/)): Sol **52.7%** · Terra **50.4%** · Luna **50.3%** · GPT-5.5 **46.9%** · Opus 4.8 **45.2%** · Fable 5 **40.5%** · Gemini 3.1 Pro **32.1%** · *DeepSeek 0731 Flash **25.2** / Opus 4.8 **25.7** / GLM **23.8** look like a different split/harness — do not merge ranks* | [agents-last-exam.org](https://agents-last-exam.org/) · [paper](https://arxiv.org/abs/2606.05405) · [GPT-5.6](https://openai.com/index/gpt-5-6/) |
| **DSBench-FullStack / Hard** | DeepSeek **internal** full-stack / hard coding-agent sets; no independent multi-vendor public LB found. | 0731 comparison only: FullStack Flash **68.7** / Opus 4.8 **71.6** / GLM **61.8** · Hard Flash **59.6** / Opus 4.8 **71.7** / GLM **54.5** | [DeepSeek changelog](https://api-docs.deepseek.com/updates/) (internal) |
| **SWE-Atlas** | Repo-level debugging (Seed labels Debugging). | Seed2.1 Pro **35.2** · Turbo **30.6** | [Seed2.1](https://seed.bytedance.com/en/seed2_1) |
| **SWE-Marathon** | 20 ultra-long tasks (rebuild libs, compilers, LSPs, ML eng; often multi-hour). | Kimi K3 **42.0%*** · Grok 4.5 **29.0%** · GLM-5.2 **13.0%** · *K3 = pre-v1.1 H20 calibration branch* | [swe-marathon.org](https://www.swe-marathon.org/) |
| **FrontierSWE** | Ultra-long open-ended eng; Dominance-style relative metrics. | Kimi K3 **81.2** Dominance · GLM-5.2 **74.4** (2026-06-16 post; Kimi 7/16 recompute **67.3**) | [frontierswe.com](https://www.frontierswe.com/) · [GitHub](https://github.com/Proximal-Labs/frontier-swe) |
| **Frontier-Bench v0.1** | Scale/Harbor hard general-agent env (TB3-era). ≠ Cognition FrontierCode. | Claude Opus 5: claims >2× Opus 4.8 / new SOTA; **no absolute** on launch page | [Scale](https://labs.scale.com/blog/frontier-bench-harder-tasks-for-better-agents) · [Harbor](https://hub.harborframework.com/datasets/frontier-bench/frontier-bench/latest) |
| **CursorBench 3.2** | Cursor’s official IDE-agent eval: ambiguous multi-file tasks from real sessions; reports score / cost / tokens / steps. **Best effort** per model. | Fable 5 Max **70.5%** · Opus 5 Max **70.0%** · GPT-5.6 Sol Max **67.2%** · Grok 4.5 High **66.7%*** · GPT-5.6 Terra Max **64.9%** · Opus 4.8 Max **62.3%** · Sonnet 5 Max **61.5%** · GPT-5.6 Luna Max **61.1%** · Kimi K3 Max **60.8%** · Composer 2.5 **56.1%** · GLM 5.2 Max **55.0%** · Gemini 3.6 Flash High **53.5%** · Kimi K2.7 Code **49.7%** · Gemini 3.5 Flash **48.8%** · *Grok: earlier Cursor codebase snapshot in training; score impact unclear* | [CursorBench](https://cursor.com/cn/cursorbench) · [method](https://cursor.com/blog/cursorbench) |
| **FrontierCode 1.1** | Cognition: correctness + mergeability / style / regressions. | Fable 5: claimed top · Opus 5: near-Fable, ~½ cost · Sonnet 5: added in 1.1 | [LB](https://cognition.com/frontiercode) · [1.1](https://cognition.com/blog/frontier-code-1.1) |

### Preview baseline (DeepSeek-V4, 2026-04-26)

| Name | Intro | Models + scores | Link |
|------|--------|-----------------|------|
| Terminal-Bench **2.0** / SWE Verified / Pro / Multilingual | Preview used classic TB2.0 + SWE stack; Flash GA (0731) reports TB2.1 / DeepSWE / NL2Repo instead | V4-Pro Max: TB2.0 **67.9** · Verified **80.6** · Pro **55.4** · Multilingual **76.2** · V4-Flash Max: Verified **79.0** · Pro **52.6** · TB2.0 **56.9** | [HF V4-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash) |

---

## Model pages

| Model | Date | Page |
|-------|------|------|
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
| ByteDance Seed2.1 / Doubao | 2026-06-23 | https://seed.bytedance.com/en/seed2_1 · [blog](https://seed.bytedance.com/en/blog/seed2-1-officially-released-advancing-ai-productivity) |
| MiniMax M3 | 2026-06-01 | https://www.minimax.io/blog/minimax-m3 |
| Qwen3.7-Max / Plus | 2026-05 | https://qwen.ai/blog?id=qwen3.7 |
| DeepSeek-V4-Flash (GA / 0731, API public beta) | 2026-07-31 | https://api-docs.deepseek.com/updates/ |
| DeepSeek-V4 Preview (Pro / Flash) | 2026-04-26 | https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash |
