# 🏊 DORY – Autonomous Iterative Coding Agent Skill
> **Ralph Wiggum Cold-Start Pressure Cooker Edition**  
> *"Just keep coding, just keep coding!"*

DORY is an autonomous, persistent, and self-healing AI coding agent skill inspired by the **Ralph Wiggum Autonomous Feedback Loop**. It replaces conversational context collapse with deterministic, cold-start engineering cycles.

---

## ⚡ Quick Install (skills.sh)

Install directly using `npx skills add` (identical to the `heygen-com/hyperframes` package model):

```bash
# Full GitHub URL
npx skills add https://github.com/<YOUR_GITHUB_USERNAME>/dory --skill dory

# Or shorthand
npx skills add <YOUR_GITHUB_USERNAME>/dory --skill dory
```

*(Once you push this repository to GitHub under your account, the command above will immediately download, validate, and wire DORY into any connected coding assistant).*

### Test Local Installation
You can test the installation locally right now on your machine without publishing:
```bash
npx skills add /Applications/dory --skill dory
```

---

## 🚀 The D-O-R-Y Loop

- **D – DO:** Contract specification, file whitelisting, and **True TDD** (writing failing contract tests before modifying production code).
- **O – OBSERVE:** Verification through the objective **Tri-Gate Gateway**:
  - **Gate A:** Code Style & Linting (`pint`, `eslint`, `ruff`)
  - **Gate B:** Static Analysis & Strict Typing (`phpstan`, `tsc --noEmit`, `mypy`)
  - **Gate C:** Runtime Behavioral Tests (`pest`, `artisan test`, `jest`, `pytest`)
- **R – RECOGNIZE:** Senior triage diagnostics (anti-Ping-Pong thrash protection, time-freezing against flaky tests, root-cause isolation).
- **Y – YIELD:** Clean working-tree progression, 0 token bleed, verified commits on **Exit 0**, or clean circuit-breaker trip at max iterations.

---

## 📂 Repository Layout

```text
dory/
├── skills/
│   └── dory/
│       └── SKILL.md       # Primary Agent Skills entrypoint
├── dory/
│   └── SKILL.md           # Mirror entrypoint for legacy resolvers
├── skills.sh.json         # skills.sh discovery manifest
├── plugin.json            # Open agent plugin manifest
├── package.json           # npm & package manager metadata
├── context.md             # Systems architecture & Mermaid schematics
├── skills.md              # Original master prompt specification
└── README.md
```

---

## 🎮 Usage & Activation

Once installed, invoke DORY by saying to any coding agent (Claude Code, Cursor, Codex, Antigravity):
- *"Use DORY to fix this bug"*
- *"`/dory` implement customer authentication"*
- *"Just keep coding until all tests pass (AFK mode)"*
- *"Run in DORY mode with max_iterations=5"*
