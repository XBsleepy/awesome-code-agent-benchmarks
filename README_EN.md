# Awesome Code Agent Benchmarks

[English](./README_EN.md) | [中文](./README_ZH.md)

> A curated list of the most watched benchmarks for **code agents** — models and systems that plan, use tools, edit repos, and ship working patches.

Curated list of frontier / high-attention benchmarks for evaluating coding agents (repo-level repair, terminal tool-use, live algorithmic coding, etc.).

**Format:** Name → Intro → Source

### How to contribute

PRs welcome. Prefer entries that are actively cited on agent/model release notes or independent leaderboards. Keep the three-field format and add both EN + ZH blurbs when possible.

---

### Repository-level software engineering

#### SWE-bench / SWE-bench Verified

- **Intro:** The de-facto standard for real-world software engineering agents. Given a GitHub issue and a codebase, the agent must produce a patch that passes the project's tests. **SWE-bench Verified** is a 500-instance, human-validated subset widely used for fairer comparisons. Scores are highly sensitive to the agent harness (tools, prompts, retries).
- **Source:** [swebench.com](https://www.swebench.com/) · [princeton-nlp/SWE-bench](https://github.com/princeton-nlp/SWE-bench) · Paper: [arXiv:2310.06770](https://arxiv.org/abs/2310.06770)

#### SWE-bench Pro

- **Intro:** A harder, long-horizon successor aimed at enterprise-style work: multi-file patches, hours-to-days human effort, contamination-resistant splits (public / held-out / commercial). Used when Verified scores look saturated.
- **Source:** [Paper](https://arxiv.org/abs/2509.16941) · Leaderboards via vendors / aggregators (e.g. BenchLM)

#### SWE-bench-Live

- **Intro:** Continuously updated, multi-language and multi-OS SWE tasks designed to reduce contamination. Supports Python plus MultiLang (C/C++, C#, Java, JS/TS, Go, Rust) and Windows PowerShell-oriented splits.
- **Source:** [microsoft/SWE-bench-Live](https://github.com/microsoft/SWE-bench-Live) · [Leaderboard](https://swe-bench-live.github.io/)

#### Multi-SWE-bench

- **Intro:** Extends SWE-style evaluation beyond Python to Java, TypeScript, JavaScript, Go, Rust, C, and C++ with expert-curated instances — useful for multilingual coding agents.
- **Source:** [Paper / project references via Multi-SWE-bench](https://arxiv.org/abs/2504.02605) · Search: Multi-SWE-bench (ByteDance et al.)

#### SWE-Lancer

- **Intro:** Evaluates agents on real freelance-style software engineering tasks (feature work / bugfix with economic framing), complementary to classic GitHub-issue repair.
- **Source:** Paper / project: SWE-Lancer (OpenAI et al.) — check latest release notes for links

---

### Terminal & agentic tool-use

#### Terminal-Bench (tbench)

- **Intro:** Stanford + Laude Institute benchmark for hard, realistic tasks in sandboxed terminals (build, ops, ML, security, data). Current community focus is **Terminal-Bench 2.x** (e.g. 2.0 / 2.1). Heavily cited by Claude Code, Codex CLI, Cursor-style agents. Scores swing with harness choice.
- **Source:** [tbench.ai](https://www.tbench.ai/) · [harbor-framework/terminal-bench](https://github.com/laude-institute/terminal-bench) · Paper: [arXiv:2601.11868](https://arxiv.org/abs/2601.11868)

---

### Live / contamination-resistant coding

#### LiveCodeBench

- **Intro:** Competitive programming problems collected **after** model training cutoffs (Codeforces, LeetCode, AtCoder, etc.) to measure genuine algorithmic ability rather than memorization. Common companion metric alongside SWE-bench.
- **Source:** [LiveCodeBench](https://livecodebench.github.io/) · [GitHub](https://github.com/LiveCodeBench/LiveCodeBench)

#### Aider Polyglot

- **Intro:** Multi-language coding exercises run through the Aider agent harness — practical signal for “can the model + agent edit and pass tests across languages,” with the caveat that harness and benchmark share authorship.
- **Source:** [Aider polyglot leaderboard](https://aider.chat/docs/leaderboards/) · [Aider](https://github.com/Aider-AI/aider)

---

### Related / emerging

#### Commit0

- **Intro:** Agents must implement libraries from scratch from specs and tests — stresses generation + iteration rather than patching existing repos.
- **Source:** Search Commit0 benchmark / project page for current links

#### SciCode

- **Intro:** Scientific programming tasks; useful when evaluating agents for research / STEM workflows rather than app engineering.
- **Source:** SciCode project / paper (see recent coding-benchmark roundups)

---

### Reading tips

1. **Same harness or don't compare** — especially SWE-bench and Terminal-Bench.
2. Match the **split** (Verified / Lite / Pro public / Live month).
3. Prefer independent leaderboards when vendor numbers look cherry-picked.
4. Pair at least one **repo** benchmark + one **terminal/agent** + one **live coding** signal.

---

## License

CC0 / public domain dedication for list content — see [`LICENSE`](./LICENSE). Benchmarks remain under their own licenses.
