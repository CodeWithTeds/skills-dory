# Build DORY – Autonomous Iterative Coding Agent Skill (Ralph Wiggum Pressure Cooker Edition)

Create an AI Agent Skill named **DORY**, integrating the **Ralph Wiggum Autonomous Feedback Loop**, **Cold-Start Pressure Cooker Architecture**, and **Tri-Gate Verification System**.

The skill must strictly adhere to the official Agent Skills specification and be fully compatible with `skills.sh` and modern AI coding agent harnesses.

> **CRITICAL REQUIREMENT:** This deliverable is an **Agent Skill** (`SKILL.md`), NOT a standalone CLI application, Python package, shell runner, or executable plugin. It must guide an AI coding agent to operate autonomously, iteratively, and deterministically without human babysitting (AFK engineering).

---

## 1. File Structure Requirements

Generate only the following repository structure:

```text
dory/
└── SKILL.md
```

### Constraints:
- Output **only** Markdown (`.md`) files with embedded YAML frontmatter.
- Do **not** generate JavaScript, TypeScript, Python, JSON, shell scripts, or external configuration files.
- The single source of truth and primary deliverable must be `dory/SKILL.md`.

---

## 2. Skill Metadata & Frontmatter

The `SKILL.md` file must begin with valid, parseable YAML frontmatter:

```yaml
---
name: dory
description: Autonomous iterative coding skill implementing the Ralph Wiggum Cold-Start Pressure Cooker loop. Eliminates context degradation and sycophantic drift by driving cold-start development cycles through a deterministic Tri-Gate (Style, Static Types, Runtime Tests), senior triage heuristics, and Citadel blast-radius controls until 100% green.
---
```

Ensure the metadata matches the Agent Skills specification and provides an unambiguous description that enables agents to automatically trigger DORY whenever autonomous, test-driven, self-healing, or iterative implementation tasks are requested.

---

## 3. Core Philosophy & Architectural Foundations

DORY merges the persistence of the DORY mindset (*"Just keep coding, just keep coding!"*) with the deterministic engineering rigor of the **Ralph Wiggum Cold-Start Pressure Cooker**:

### The Mnemonic:
- **D – DO:** Establish task contracts, whitelist file paths, pre-write deterministic tests (True TDD), and implement targeted mutations.
- **O – OBSERVE:** Execute the objective **Tri-Gate Verification Gateway** (Style, Types, Tests). Capture binary exit codes and machine-readable telemetry.
- **R – RECOGNIZE:** Perform **Senior Triage Diagnostics**. Eliminate Ping-Pong Thrashing, eradicate Flaky Test Poisoning, and pinpoint root causes from compiler/test output.
- **Y – YIELD:** Persist verified state to disk, update the execution ledger, advance towards 100% green convergence, or trip circuit breakers cleanly.

### Fundamental Problem: The Conversational Chat Trap
Standard conversational coding agents suffer from **Linear Horizontal Degradation**:
1. Vague prompt injected into chat window (~2.5k tokens).
2. Unverified direct mutation breaks tests; 5k token error trace dumped into chat context (~12k tokens).
3. Whack-a-mole sycophantic patching: agent apologizes, hallucinates fixes, silently corrupts schema/architecture (~38k tokens).
4. **Context Collapse:** Token bleed reaches 80k+, attention drifts, budget drains, agent falsely claims completion on a broken build.

### The Solution: Ralph Cold-Start Pressure Cooker
DORY eliminates context degradation through **Tabula Rasa State Discipline**:
- **Disk as Ground Truth:** Chat context is ephemeral; code diffs, task specs, and test output on disk are durable.
- **0 Token Bleed:** Each iteration cycle operates as a fresh, focused evaluation. State carries forward through git diffs and disk-based logs (e.g., JUnit XML, linter output), not conversational history.
- **Binary Evaluation:** Replaces subjective LLM self-assessment with deterministic exit codes (`0` = Pass, `!= 0` = Fail).

---

## 4. The 4-Layer Citadel Architecture

The instructions in `SKILL.md` must mandate that agents operate within the **Citadel Framework**:

### Block 01 · Specification Engine (Contract Engine)
- Formulate an explicit specification contract (`task-spec.json` or markdown contract) prior to code generation.
- Enforce strict target file whitelisting to prevent speculative scope creep.
- Define unambiguous error status codes, expected payload schemas, and verifiable acceptance criteria.
- Eliminate conversational ambiguity before writing application logic.

### Block 02 · Orchestrated Execution (Cold-Start Worker)
- Treat each iteration as an isolated, bounded mutation step.
- Enforce discrete execution cycles with strict operational boundaries (e.g., hard execution timeout concept, process isolation).
- Prevent memory leakage and context poisoning across multiple attempts.

### Block 03 · Tri-Gate Gatekeepers (Verification Gateway)
Every cycle must pass through three non-negotiable binary gates:
1. **Gate A · Code Style & Syntax (Linting):**
   - PSR-12, ESLint, Prettier, Pint, Ruff, or standard platform linters.
   - Zero syntax errors, formatting violations, or unused import clutter.
2. **Gate B · Static Analysis & Strict Typing:**
   - PHPStan (Level 8/max), TypeScript strict mode (`tsc --noEmit`), Mypy/Pyright, or compiler strict typing.
   - Non-null guarantees, verified method signatures, contract compliance.
3. **Gate C · Runtime Behavioral Tests:**
   - Unit, integration, and feature test suites (Pest, PHPUnit, Jest, Vitest, Pytest, Go test).
   - 100% green assertions against real database/system state.
- **Central Intersection:** *Zero Hallucination · Production Verified · Exit 0*. All three gates must return exit code 0 before code is considered complete.

### Block 04 · Citadel Blast Radius Sentinel
- Work within disposable branches or isolated workspaces (`agent/*`).
- Maintain sandbox boundaries (air-gapped network where external calls are not required).
- Protect sensitive files, credentials, and environment configurations (.env, secrets vault).
- Implement hard loop limits (maximum iterations circuit breaker) and cost bounds.

---

## 5. Senior Triage Heuristics & Antipattern Defenses

The `SKILL.md` instructions must train the agent to recognize and defeat standard loop failure modes:

| Antipattern | Mechanism of Failure | Senior Diagnostic Defense (The Fix) |
| :--- | :--- | :--- |
| **Ping-Pong Thrash** | Agent alternates between Approach A and Approach B, breaking tests cyclically. | **Multi-Attempt Diff Tracking:** Maintain a ledger/diff of the last 2 failed attempts. Force the agent to explicitly inspect prior dead-ends before proposing a patch. |
| **Flaky Test Poisoning** | Tests rely on system clock (`now()`), unseeded random ordering, or leaky database state. | **Deterministic Isolation:** Freeze time with test clocks (e.g., `Carbon::setTestNow()`, fake timers), seed random generators, and isolate database transactions. |
| **Specification Vacuum** | Vague prompts pass shallow assertions but violate actual business contracts. | **True TDD (Pre-Flight Tests):** Pre-write failing feature/unit tests and JSON schema contracts *before* modifying production code. |
| **Sycophantic Apology Loop** | Agent writes wordy apologies and claims fixes that it hasn't verified. | **Zero-Chat Rigor:** Forbid apologies and conversational filler. Evaluate strictly via terminal output and binary exit codes. |
| **Test Mutilation** | Agent deletes, comments out, or weakens assertions to force tests to pass. | **Strict Invariant:** Modifying existing tests or test thresholds to bypass failures is strictly prohibited unless explicitly instructed by the user. |

---

## 6. Comprehensive DORY Operational Workflow

`SKILL.md` must provide detailed, algorithmic instructions for each phase:

### Phase 1: D – DO (Spec & True TDD)
1. **Contract Ingestion:** Parse user requirements into an explicit acceptance contract.
2. **Codebase Reconnaissance:** Inspect existing architecture, conventions, linters, static analyzers, and test frameworks. Whitelist files to edit.
3. **Pre-Flight Test Verification (TDD):** Run existing tests to confirm current baseline. If a new feature or bug fix is needed, generate failing tests reproducing the issue before touching production code.
4. **Targeted Implementation:** Apply minimal, high-cohesion changes strictly to whitelisted files.

### Phase 2: O – OBSERVE (Tri-Gate Gateway)
1. **Sequential Gate Execution:**
   - Run Gate 1 (Lint/Style). Collect exit code + errors.
   - Run Gate 2 (Static Types/Analysis). Collect exit code + errors.
   - Run Gate 3 (Unit/Feature Tests). Collect exit code + test output.
2. **Artifact Capture:** Store failure traces on disk or structured logs. Never evaluate code validity based on conversational assumptions.

### Phase 3: R – RECOGNIZE (Senior Triage)
1. **Exit Code Evaluation:** If all gates exit `0`, transition directly to Yield.
2. **Root Cause Analysis:** Parse exact line numbers, compiler faults, and assertion failures.
3. **Thrash Check:** Compare the proposed change against the previous failed attempt. If identical to a past failure, reject approach immediately.
4. **Strategy Formulation:** Formulate a single, verified hypothesis to resolve the failure.

### Phase 4: Y – YIELD (Commit or Loop)
1. **State Persistence:** Keep working tree in a clean, inspectable state.
2. **Iteration Check:** Increment attempt counter. If `attempt >= MAX_ITERATIONS`, trip the circuit breaker and explain unresolved blocks.
3. **Loopback:** If failures remain and bounds permit, initiate the next cycle with clean context.
4. **Final Delivery:** When Tri-Gate reaches 100% green (Exit 0), produce the final summary report.

---

## 7. Safety, Boundaries & Circuit Breakers

Define rigid boundary rules:
- **Max Iteration Circuit Breaker:** Default to 5–10 maximum cycles. Hard abort with diagnostic report if unresolved.
- **Forbidden Actions:** No `git push --force`, no dropping production databases, no mutating CI/CD workflows, no deleting tests.
- **Clarification Trigger:** If the task contract is inherently contradictory or lacks credentials/dependencies, halt and request clarification rather than thrashing.

---

## 8. Final Report Specification

Upon loop completion or circuit breaker trip, DORY must present a concise, structured markdown report:
- **Status:** PASS (100% Green, Exit 0) or TRIPPED (Circuit Breaker reached).
- **Tri-Gate Summary:** Table of Gates (Style, Static Analysis, Tests) with commands executed and exit codes.
- **Files Modified:** List of touched files with rationale.
- **Triage History:** Iterations count, antipatterns resolved (e.g., fixed typehint, resolved null constraint).
- **Verification Evidence:** Key test assertion counts and green status proofs.

---

## 9. Quality & Packaging Requirements

Before writing `dory/SKILL.md`:
1. Use standard Markdown formatting with clear headings, lists, tables, and Mermaid flowcharts representing the Tri-Gate and the DORY cycle.
2. Ensure the instructions are language-agnostic (providing multi-language examples such as PHP/Laravel, TypeScript/Node, Python/FastAPI, Go).
3. Validate that the YAML frontmatter is clean and compliant.
4. Provide instructions on how to install and test the skill via `skills.sh`:
   `npx skills add <GITHUB_REPOSITORY_URL> --skill dory`
   *(Explicitly note that installation requires publishing the skill to a GitHub repository first).*

Produce the highest quality, most comprehensive, and technically rigorous `SKILL.md` possible.
