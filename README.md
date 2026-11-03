# 🏊 DORY – Autonomous Iterative Coding Agent Skill
> **Ralph Wiggum Cold-Start Pressure Cooker Edition**  
> *"Just keep coding, just keep coding!"*

DORY is an autonomous, persistent, and self-healing AI coding agent skill inspired by the **Ralph Wiggum Autonomous Feedback Loop**. It replaces conversational context collapse with deterministic, cold-start engineering cycles.

---

## 🚀 The D-O-R-Y Loop

- **D – DO:** Contract ingestion, target file whitelisting, and **True TDD** (writing failing contract tests before modifying production code).
- **O – OBSERVE:** Verification through the objective **Tri-Gate Gateway**:
  - **Gate A:** Code Style & Linting (`pint`, `eslint`, `ruff`)
  - **Gate B:** Static Analysis & Strict Typing (`phpstan`, `tsc --noEmit`, `mypy`)
  - **Gate C:** Runtime Behavioral Tests (`pest`, `artisan test`, `jest`, `pytest`)
- **R – RECOGNIZE:** Senior triage diagnostics (anti-Ping-Pong thrash protection, time-freezing against flaky tests, root-cause isolation).
- **Y – YIELD:** Clean working-tree progression, 0 token bleed, verified commits on **Exit 0**, or clean circuit-breaker trip at max iterations.

---

## 📦 Installation

### Option 1: Via `skills.sh`
Once published to GitHub:
```bash
npx skills add <GITHUB_REPOSITORY_URL> --skill dory
```

### Option 2: Local Agent Skills / Antigravity
Clone or copy into your workspace's `.agents/skills/` directory:
```bash
mkdir -p .agents/skills/dory
cp /path/to/dory/dory/SKILL.md .agents/skills/dory/SKILL.md
```

### Option 3: Global User Plugin (Antigravity / Gemini CLI)
Install to global plugins:
```bash
mkdir -p ~/.gemini/config/plugins/dory/skills/dory
cp dory/SKILL.md ~/.gemini/config/plugins/dory/skills/dory/SKILL.md
cp plugin.json ~/.gemini/config/plugins/dory/plugin.json
```

---

## 🎮 Usage & Activation

Invoke DORY by telling any compatible coding agent:
- *"Use DORY to implement this feature"*
- `"/dory fix the failing auth tests"`
- *"Keep coding until all tests are green (AFK mode)"*

DORY will autonomously work through the Tri-Gate verification barrier until the task reaches **Exit Code 0** or trips its safety circuit breaker.
