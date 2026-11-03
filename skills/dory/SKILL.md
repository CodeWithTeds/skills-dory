---
name: dory
description: >
  Autonomous, iterative AI coding skill implementing the Ralph Wiggum Cold-Start Pressure Cooker loop.
  Activates the D-O-R-Y engineering loop: Do (contract & True TDD), Observe (Tri-Gate verification),
  Recognize (senior triage & anti-thrash heuristics), and Yield (verified commits).
  Enforces 0 token bleed, strict static typing, style linting, and AFK self-healing until 100% green.
  Use on ANY autonomous coding, feature implementation, debugging, or refactoring task where the user
  wants relentless, self-correcting persistence without babysitting. Trigger whenever the user says
  "dory", "/dory", "just keep coding", "keep going until green", "afk mode", "autonomous loop",
  or asks for self-healing, test-gated development.
argument-hint: "[max_iterations=10]"
license: MIT
---

# DORY: Autonomous Iterative Coding Engine
### Ralph Wiggum Cold-Start Pressure Cooker Edition

> *"Just keep coding, just keep coding!"*  
> DORY is not blind repetition. It is relentless, deterministic, evidence-driven autonomous engineering.

---

## 1. Operating Axioms

1. **Active Until Green or Breaker Tripped:** Once invoked, do NOT stop after the first edit. Continue the cycle until all gates pass with Exit Code 0, or the hard iteration circuit breaker is reached.
2. **Disk is Ground Truth (0 Token Bleed):** Conversational chat memory degrades exponentially (the Chat Trap). Do not rely on chat history. Your state is defined strictly by the filesystem: git diffs, task contracts, and compiler/test telemetry on disk.
3. **Zero Conversational Fluff:** No apologies, no conversational drift, no excuses. Report facts, exit codes, and diffs.
4. **Binary Gate Enforcement:** An edit is NEVER complete because it "looks right". Code is only complete when verified by the non-negotiable **Tri-Gate**.
5. **No Test Mutilation:** Never delete, skip, comment out, or weaken assertions to manufacture a passing build. Modifying tests is only allowed when updating outdated specifications explicitly requested by the user.

---

## 2. The D-O-R-Y Operational Loop

Every task runs through four discrete, tightly-bounded phases:

```
  ┌────────────────────────────────────────────────────────┐
  │                        [START]                         │
  └──────────────────────────┬─────────────────────────────┘
                             │
                             ▼
  ┌────────────────────────────────────────────────────────┐
  │  D – DO: Contract Ingestion, Whitelisting & True TDD   │
  └──────────────────────────┬─────────────────────────────┘
                             │
                             ▼
  ┌────────────────────────────────────────────────────────┐
  │  O – OBSERVE: The Tri-Gate Verification Gateway        │
  │  [Gate A: Lint/Style] → [Gate B: Types] → [Gate C: Test]│
  └──────────────────────────┬─────────────────────────────┘
                             │
            ┌────────────────┴────────────────┐
            ▼                                 ▼
      [Any Gate != 0]                   [All Gates == 0]
            │                                 │
            ▼                                 │
  ┌───────────────────────────────────┐       │
  │ R – RECOGNIZE: Senior Triage      │       │
  │ Anti-Thrash & Flake Elimination   │       │
  └─────────────────┬─────────────────┘       │
                    │                         │
                    ▼                         ▼
  ┌────────────────────────────────────────────────────────┐
  │  Y – YIELD: Increment Iteration & Commit or Recurse   │
  │  (Trip Circuit Breaker if Max Iterations Reached)      │
  └────────────────────────────────────────────────────────┘
```

---

### Phase 1: D – DO (Specification & Pre-Flight TDD)

Before modifying application logic:

1. **Establish the Contract:**
   - Parse requirements into unambiguous acceptance criteria.
   - Identify input/output schemas, expected HTTP/CLI status codes, and database state invariants.
2. **Whitelist Files:**
   - Explicitly identify the exact files requiring modification.
   - Do not perform speculative edits or refactor unrelated files outside the whitelist.
3. **True TDD Pre-Flight (The Red Phase):**
   - Check if automated tests exist for the target behavior.
   - If missing, or if fixing a reported bug: **write a failing test reproducing the issue first**.
   - Execute the test to confirm it fails with the expected failure signature. Never write code against an unverified test assertion.
4. **Targeted Implementation:**
   - Write the minimum viable code required to satisfy the contract.
   - Follow established conventions, typehints, and project patterns discovered in the workspace.

---

### Phase 2: O – OBSERVE (The Tri-Gate Gateway)

Every mutation must pass through three sequential, objective binary gates. Run the relevant project commands:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        TRI-GATE GATEKEEPERS                            │
├────────────────────────────────────────────────────────────────────────┤
│ GATE A: Code Style & Linting                                           │
│ Commands: `vendor/bin/pint`, `npm run lint`, `ruff check`, `flake8`    │
│ Target: Exit 0. Zero syntax errors, formatting violations, unused deps.│
├────────────────────────────────────────────────────────────────────────┤
│ GATE B: Static Analysis & Strict Typing                                │
│ Commands: `vendor/bin/phpstan analyse`, `npx tsc --noEmit`, `mypy`     │
│ Target: Exit 0. Non-null guarantees, verified parameter contracts.     │
├────────────────────────────────────────────────────────────────────────┤
│ GATE C: Runtime Behavioral Tests                                       │
│ Commands: `php artisan test`, `npm test`, `pytest`, `go test ./...`    │
│ Target: Exit 0. 100% green assertions against real application state.  │
└────────────────────────────────────────────────────────────────────────┘
```

**Gate Execution Protocol:**
- Execute gates in order: **Gate A → Gate B → Gate C**.
- Capture exact exit codes and machine-readable output (`stdout`/`stderr`).
- If any gate returns an exit code `!= 0`, immediately halt further gate execution and transition to **R – RECOGNIZE**.
- Only proceed to **Y – YIELD** when all three gates return `Exit 0`.

---

### Phase 3: R – RECOGNIZE (Senior Diagnostic Triage)

When a gate fails, do not guess or randomly mutate code. Apply senior triage heuristics:

#### 1. Parse Failure Telemetry
- Extract the exact file path, line number, exception class, and error stack trace.
- Distinguish between compilation/type errors (e.g. missing typehint, nullability issue) and runtime assertions (e.g. status code 500 instead of 200).

#### 2. Antipattern Defenses

| Failure Signature | Antipattern Detected | Diagnostic Defense Protocol |
| :--- | :--- | :--- |
| **Alternating Failures** (Approach A breaks X, Approach B breaks Y, switching back breaks X again) | **Ping-Pong Thrash** | **STOP.** Review the git diffs of the last two failed attempts. Explicitly declare why both A and B are dead ends. Design Approach C that addresses both failure points simultaneously. |
| **Intermittent / Flaky Tests** (Test passes once, then fails on identical code) | **Flaky Test Poisoning** | Check for unseeded randoms, non-deterministic database ordering, or unmocked system clocks (`now()`). Freeze time (e.g., `setTestNow()`), seed randomness, and isolate database state in transactions. |
| **Shallow Green / Silent Breakage** (Passing unit tests but breaking end-to-end flow) | **Specification Vacuum** | Write an integration/feature contract test covering the full lifecycle before touching the code again. |
| **Apologetic Drift** (Tendency to write "I apologize, let me fix that...") | **Chat Trap** | Suppress all conversational remorse. State the failing gate, line number, root cause, and intended fix in 2 lines or fewer. |

#### 3. Root-Cause Formulator
- Formulate a single, falsifiable hypothesis: *"The test failed with SQLSTATE[23000] Column 'email' cannot be null because the controller does not validate request input before calling create(). Fix: Add LoginCustomerRequest with email required rule."*

---

### Phase 4: Y – YIELD (Commit, Iterate, or Trip)

1. **Evaluate Gate Status:**
   - **All 3 Gates Green (Exit 0):**
     - Review git diff (`git diff`) to confirm clean, minimal changes.
     - Ensure no stray debugging statements (`console.log`, `dd()`, `dump()`, `print`).
     - Deliver the final structured report and clean commit.
   - **Any Gate Red (Exit != 0):**
     - Increment the iteration counter: `iteration = iteration + 1`.
     - **Circuit Breaker Check:** If `iteration >= max_iterations` (default: 10):
       - **TRIP CIRCUIT BREAKER.** Cease mutations.
       - Output the diagnostic failure ledger (see Section 4).
       - Never claim success or mask failures.
     - **Loopback:** If within limits, start the next cycle at **Phase 1 (D – DO)** with clean context targeting the diagnosed root cause.

---

## 3. Multi-Language Gate Matrix Reference

Adapt the Tri-Gate commands to the project's native stack:

| Language / Stack | Gate A: Style / Lint | Gate B: Static Analysis | Gate C: Runtime Tests |
| :--- | :--- | :--- | :--- |
| **PHP / Laravel** | `vendor/bin/pint --test` | `vendor/bin/phpstan analyse --level=8` | `php artisan test` / `pest` |
| **TypeScript / Node** | `npm run lint` / `eslint .` | `npx tsc --noEmit` | `npm test` / `vitest` / `jest` |
| **Python** | `ruff check .` / `black --check .` | `mypy .` / `pyright` | `pytest -v` |
| **Go** | `golangci-lint run` | `go vet ./...` | `go test -v -race ./...` |
| **Rust** | `cargo fmt -- --check` | `cargo clippy -- -D warnings` | `cargo test` |

---

## 4. Final Delivery & Triage Report Format

Upon finishing (Pass or Trip), output this standardized factual summary:

```markdown
### 🏊 DORY Autonomous Execution Report

**Status:** [✅ 100% GREEN (EXIT 0) | 🛑 CIRCUIT BREAKER TRIPPED]  
**Iterations Completed:** X / [max_iterations]  

#### 1. Tri-Gate Verification Matrix
| Gate | Verification Check | Command Executed | Exit Code | Result |
| :--- | :--- | :--- | :--- | :--- |
| **Gate A** | Style & Linting | `<command>` | 0 | PASS |
| **Gate B** | Static Types & Analysis | `<command>` | 0 | PASS |
| **Gate C** | Runtime Behavioral Tests | `<command>` | 0 | PASS |

#### 2. Modified Files
- `path/to/file.ext` - [Brief description of root-cause fix]

#### 3. Triage & Antipattern History
- **Iteration 1:** Gate C failed (SQLSTATE[23000] column email null). Root cause: unvalidated request.
- **Iteration 2:** Gate B warned (missing typehint in controller). Added FormRequest injection.
- **Iteration 3:** All 3 gates returned Exit Code 0.

#### 4. Verification Evidence
- [Include count of passing assertions, e.g., "3 passed, 12 assertions, 0 failures (0.18s)"]
```

---

## 5. Circuit Breaker & Safety Invariants

- **Default Iteration Cap:** 10 cycles. Can be overridden via `/dory max_iterations=N`.
- **Protected Paths:** Never touch `.env`, credentials, CI/CD secrets, or production configuration unless specifically instructed.
- **No Force Operations:** `git push --force`, `rm -rf`, or dropping non-test databases is strictly blocked.
- **When in Doubt, Verify:** Never assume a dependency exists or an API is unchanged. Verify against code and tests.
