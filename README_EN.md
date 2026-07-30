# Awesome Code Agent Benchmarks (EN)

[English](./README_EN.md) | [中文](./README_ZH.md)

Window: **2026-05-01 → 2026-07-31** · Code-agent benches still scored in vendor posts / model cards  
Format: `name | intro | models + scores | bench link` · Model pages at the bottom  
Notes: mostly vendor-reported; **different harness / multi-agent ≠ comparable**. Excludes single-problem codegen (HumanEval, LiveCodeBench, …).

---

## Benchmarks

| Name | Intro | Models + scores | Bench link |
|------|--------|-----------------|------------|
| **Terminal-Bench 2.1** | Hard multi-step tasks in a sandboxed terminal (code, setup, debug, data, ML, security). Broadest vendor coverage. | GPT-5.6 Sol **88.8%** (Sol Ultra multi-agent **91.9%**, Codex) · Kimi K3 **88.3%** (Kimi Code) · Grok 4.5 **83.3%** · GLM-5.2 **81.0%** (Terminus-2) / **82.7%** (Claude Code) · Gemini 3.6 Flash **78.0%** · Gemini 3.5 Flash **76.2%** · Seed2.1 Pro **71.0%** / Turbo **67.6%** · MiniMax M3 **66.0%** · Opus 4.8 reported, no absolute score on page | [tbench.ai/2.1](https://www.tbench.ai/news/terminal-bench-2-1) |
| **DeepSWE v1.1** | 113 original long-horizon SWE tasks (91 repos / 5 langs); human verifiers; low public-PR contamination. Fastest-rising new bench. | GPT-5.6 Sol **72.7%** · Kimi K3 **67.5%** (Kimi Code; mini-SWE-agent **67.3%**) · Grok 4.5 **53%** · Gemini 3.6 Flash **49%** · GLM-5.2 **46.2%** | [Leaderboard](https://deepswe.datacurve.ai/) · [paper](https://arxiv.org/abs/2607.07946) |
| **SWE-Bench Pro** | 1,865 tasks / 41 pro repos; multi-file, long-horizon. Still widely reported; OpenAI audit estimates ~**30%** broken/unreliable — not sole evidence. | Grok 4.5 **64.7%** · GPT-5.6 Sol **64.6%** · GLM-5.2 **62.1%** · Qwen3.7-Max **60.6%** · MiniMax M3 **59.0%** · Gemini 3.6 Flash **58.7%** / 3.5 Flash **55.1%** · *(OpenAI cite)* Fable 5 **80.0%** · Opus 4.8 **69.2%** | [Scale LB](https://labs.scale.com/leaderboard/swe_bench_pro_public) · [OpenAI audit](https://openai.com/index/separating-signal-from-noise-coding-evaluations/) |
| **AA Coding Agent Index v1.1** | Third-party composite: pass rate + tokens + latency + cost. **Model × harness** score. | GPT-5.6 Sol **80.0** / Terra **77.4** / Luna **74.6** · *(OpenAI cite)* Fable 5 **77.2** · Opus 4.8 **72.5** · Opus 5 highlights index, no absolute on page | [method](https://artificialanalysis.ai/methodology/coding-agents-benchmarking) · [ranking](https://artificialanalysis.ai/agents/coding-agents) |
| **ProgramBench** | Build a full program from NL (no scaffold / fine hints). | Kimi K3 **77.8** · GLM-5.2 **63.7** · Seed2.1 Pro `0/1/50.3` · Turbo `0/0/49.4` (official 3-field; not reinterpreted) | [programbench.com](https://programbench.com/) |
| **NL2Repo** | High-level NL → end-to-end repo (arch / multi-file / ship). Heavier use by CN labs. | GLM-5.2 **48.9** · Seed2.1 Pro **47.0** / Turbo **43.7** · *(GLM cite)* Qwen3.7-Max **47.2** | See model pages (no single public site) |
| **SWE-Atlas** | Repo-level debugging (Seed labels Debugging). | Seed2.1 Pro **35.2** · Turbo **30.6** | [Seed2.1](https://seed.bytedance.com/en/seed2_1) |
| **SWE-Marathon** | 20 ultra-long tasks (rebuild libs, compilers, LSPs, ML eng; often multi-hour). | Kimi K3 **42.0%*** · Grok 4.5 **29.0%** · GLM-5.2 **13.0%** · *K3 = pre-v1.1 H20 calibration branch* | [swe-marathon.org](https://www.swe-marathon.org/) |
| **FrontierSWE** | Ultra-long open-ended eng; Dominance-style relative metrics. | Kimi K3 **81.2** Dominance · GLM-5.2 **74.4** (2026-06-16 post; Kimi 7/16 recompute **67.3**) | [frontierswe.com](https://www.frontierswe.com/) · [GitHub](https://github.com/Proximal-Labs/frontier-swe) |
| **Frontier-Bench v0.1** | Scale/Harbor hard general-agent env (TB3-era). ≠ Cognition FrontierCode. | Claude Opus 5: claims >2× Opus 4.8 / new SOTA; **no absolute** on launch page | [Scale](https://labs.scale.com/blog/frontier-bench-harder-tasks-for-better-agents) · [Harbor](https://hub.harborframework.com/datasets/frontier-bench/frontier-bench/latest) |
| **CursorBench 3.2** | Cursor’s official IDE-agent eval: ambiguous multi-file tasks from real sessions; reports score / cost / tokens / steps. **Best effort** per model. | Fable 5 Max **70.5%** · Opus 5 Max **70.0%** · GPT-5.6 Sol Max **67.2%** · Grok 4.5 High **66.7%*** · GPT-5.6 Terra Max **64.9%** · Opus 4.8 Max **62.3%** · Sonnet 5 Max **61.5%** · GPT-5.6 Luna Max **61.1%** · Kimi K3 Max **60.8%** · Composer 2.5 **56.1%** · GLM 5.2 Max **55.0%** · Gemini 3.6 Flash High **53.5%** · Kimi K2.7 Code **49.7%** · Gemini 3.5 Flash **48.8%** · *Grok: earlier Cursor codebase snapshot in training; score impact unclear* | [CursorBench](https://cursor.com/cn/cursorbench) · [method](https://cursor.com/blog/cursorbench) |
| **FrontierCode 1.1** | Cognition: correctness + mergeability / style / regressions. | Fable 5: claimed top · Opus 5: near-Fable, ~½ cost · Sonnet 5: added in 1.1 | [LB](https://cognition.com/frontiercode) · [1.1](https://cognition.com/blog/frontier-code-1.1) |

### Outside window (DeepSeek, 2026-04-26)

| Name | Intro | Models + scores | Link |
|------|--------|-----------------|------|
| Terminal-Bench **2.0** / SWE Verified / Pro / Multilingual | Still on classic TB2.0 + SWE stack; not yet DeepSWE / ProgramBench | V4-Pro Max: TB2.0 **67.9** · Verified **80.6** · Pro **55.4** · Multilingual **76.2** | [HF V4-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash) |

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
| DeepSeek-V4 (outside window) | 2026-04-26 | https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash |
