# Awesome Code Agent Benchmarks

[English](./README_EN.md) | [中文](./README_ZH.md)

> 记录与追踪当前最受关注的 **Code Agent** 评测基准：名称 · 简介 · 来源。

收录当前最受关注、常被模型/Agent 发布会引用的 Code Agent 评测基准。

**条目格式：** 名称 → 简介 → 来源

### 如何贡献

欢迎 PR。优先收录仍在被广泛引用、有独立榜单或持续更新的基准。尽量保持「名称-简介-来源」结构，并附中英简介。

---

### 仓库级软件工程

#### SWE-bench / SWE-bench Verified

- **简介：** 现实软件工程 Agent 的事实标准。给定 GitHub Issue 与代码库，Agent 需提交能通过项目测试的 patch。**SWE-bench Verified** 为 500 条经人工校验的子集，是目前最常用的对比口径。分数对 Agent harness（工具、提示、重试策略）非常敏感。
- **来源：** [swebench.com](https://www.swebench.com/) · [princeton-nlp/SWE-bench](https://github.com/princeton-nlp/SWE-bench) · 论文：[arXiv:2310.06770](https://arxiv.org/abs/2310.06770)

#### SWE-bench Pro

- **简介：** 更难、更长程的后继基准，面向企业级任务：多文件改动、人类可能需数小时到数天完成；含抗污染划分（公开 / 留出 / 商业）。在 Verified 分数趋于饱和时更有区分度。
- **来源：** [论文](https://arxiv.org/abs/2509.16941) · 各厂商/聚合榜单（如 BenchLM）

#### SWE-bench-Live

- **简介：** 持续更新、多语言与多操作系统的 SWE 任务集，降低数据污染风险。覆盖 Python，以及 MultiLang（C/C++、C#、Java、JS/TS、Go、Rust）与 Windows（PowerShell）相关划分。
- **来源：** [microsoft/SWE-bench-Live](https://github.com/microsoft/SWE-bench-Live) · [排行榜](https://swe-bench-live.github.io/)

#### Multi-SWE-bench

- **简介：** 将 SWE 式评测从 Python 扩展到 Java、TypeScript、JavaScript、Go、Rust、C、C++ 等，实例经专家筛选，适合评估多语言 Coding Agent。
- **来源：** [相关论文 arXiv:2504.02605](https://arxiv.org/abs/2504.02605) · 检索：Multi-SWE-bench

#### SWE-Lancer

- **简介：** 以真实自由职业风格的软件工程任务（功能开发/修 bug，带经济视角）评测 Agent，与经典 GitHub Issue 修复形成互补。
- **来源：** SWE-Lancer 论文/项目（OpenAI 等）— 以最新发布说明中的链接为准

---

### 终端与 Agentic 工具使用

#### Terminal-Bench（tbench）

- **简介：** Stanford + Laude Institute 推出的沙箱终端硬核任务基准（构建、运维、ML、安全、数据等）。社区当前关注 **Terminal-Bench 2.x**（如 2.0 / 2.1）。常被 Claude Code、Codex CLI、Cursor 类 Agent 引用。分数同样强依赖 harness。
- **来源：** [tbench.ai](https://www.tbench.ai/) · [harbor-framework/terminal-bench](https://github.com/laude-institute/terminal-bench) · 论文：[arXiv:2601.11868](https://arxiv.org/abs/2601.11868)

---

### 实时 / 抗污染编码

#### LiveCodeBench

- **简介：** 收集模型训练截止日**之后**发布的竞赛编程题（Codeforces、LeetCode、AtCoder 等），衡量真实算法能力而非背题。常与 SWE-bench 搭配报告。
- **来源：** [LiveCodeBench](https://livecodebench.github.io/) · [GitHub](https://github.com/LiveCodeBench/LiveCodeBench)

#### Aider Polyglot

- **简介：** 在 Aider Agent harness 上跑多语言编程练习——对「模型 + Agent 能否跨语言改代码并通过测试」有实用参考价值；需注意 harness 与榜单同源。
- **来源：** [Aider polyglot 榜单](https://aider.chat/docs/leaderboards/) · [Aider](https://github.com/Aider-AI/aider)

---

### 相关 / 新兴

#### Commit0

- **简介：** 要求 Agent 从规格与测试从零实现库，侧重生成与迭代，而非在已有仓库上打补丁。
- **来源：** 检索 Commit0 benchmark / 项目页获取最新链接

#### SciCode

- **简介：** 科学计算向编程任务，适合评估研究 / STEM 场景下的 Agent，而非普通应用工程。
- **来源：** SciCode 项目 / 论文（见近期 coding benchmark 综述）

---

### 阅读建议

1. **同一 harness 才好比** —— 尤其是 SWE-bench 与 Terminal-Bench。
2. 对齐 **划分**（Verified / Lite / Pro public / Live 某月等）。
3. 厂商自报分数存疑时，优先参考独立榜单。
4. 至少组合看：**仓库修复** + **终端/Agent** + **实时编码** 三类信号。

---

## 许可证

列表内容采用 CC0，见 [`LICENSE`](./LICENSE)。各 benchmark 本身仍遵循其原有协议。
