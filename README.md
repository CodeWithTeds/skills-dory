<p align="center">
  <img src="dory/dory.png" width="240" alt="DORY – Autonomous Iterative Coding System">
</p>

<h1 align="center">DORY</h1>

<p align="center">
  <strong>Deterministic Test Gates &middot; Context Degradation Elimination &middot; Self-Healing AFK Engineering</strong><br>
  <em>The Ralph Wiggum Cold-Start Pressure Cooker Architecture for Autonomous AI Coding Agents</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/loop-Ralph%20Wiggum-EB4E27?style=flat-square&logo=git&logoColor=white" alt="Ralph Wiggum Loop">
  <img src="https://img.shields.io/badge/context-0%20token%20bleed-10B981?style=flat-square" alt="0 Token Bleed">
  <img src="https://img.shields.io/badge/verification-Tri--Gate%20Exit%200-059669?style=flat-square" alt="Tri-Gate Exit 0">
  <img src="https://img.shields.io/badge/agents-20%2B%20supported-111827?style=flat-square" alt="Supported Agents">
  <img src="https://img.shields.io/badge/license-MIT-6B7280?style=flat-square" alt="MIT License">
</p>

<p align="center">
  <em>"Just keep coding, just keep coding!"</em>
</p>

---

## ⚡ Quick Install (skills.sh)

Install directly into any AI coding assistant (**Claude Code, Cursor, Codex, Antigravity, Cline, Windsurf**):

```bash
# Full URL (matching the hyperframes model)
npx skills add https://github.com/CodeWithTeds/dory --skill dory

# Or shorthand
npx skills add CodeWithTeds/dory --skill dory
```

> [!TIP]
> **Test locally without installing:**
> ```bash
> npx skills use CodeWithTeds/dory@dory
> ```

---

## 🎯 Executive Overview & System KPIs

DORY eliminates the **Conversational Chat Trap** where agents suffer exponential token bleed (0k $\rightarrow$ 80k+ tokens), hallucinate fixes, and apologize on broken builds. Instead, DORY enforces the **Ralph Cold-Start Pressure Cooker**: discrete mutation cycles with **Tabula Rasa isolation**, non-negotiable **Tri-Gate verification**, and senior loopback diagnostics.

| Domain | Architectural Guarantee | Enforcement Mechanism | Target Metric |
| :--- | :--- | :--- | :--- |
| **Context Retention** | 100% Cold Starts | Tabula Rasa subshell isolation; state stored on disk, not chat history | **0 Token Bleed** |
| **Evaluation** | Deterministic Binary Gates | Non-negotiable Tri-Gate (Pint/ESLint, PHPStan/TypeScript strict, Pest/Jest) | **Exit Code 0 or 1** |
| **Human Workload** | AFK Autonomous Engineering | Automated diagnostic loopback, True TDD, and senior triage heuristics | **Zero Babysitting** |
| **Safety Bounds** | Blast Radius Containment | Disposable git branches (`agent/*`), locked sandboxes, circuit breakers | **Zero Blast Leak** |

---

## 🔁 The D-O-R-Y Loop Architecture

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

1. **D – DO:** Establish task contract (`task-spec.json`), whitelist files, pre-write failing tests (**True TDD**), and apply targeted minimal edits.
2. **O – OBSERVE:** Run the **Tri-Gate Gateway** (Style $\rightarrow$ Static Typing $\rightarrow$ Runtime Tests). Capture binary exit codes and machine-readable error telemetry.
3. **R – RECOGNIZE:** Perform **Senior Diagnostic Triage**: eliminate Ping-Pong thrashing via multi-attempt diff tracking, freeze flaky test clocks, and isolate root causes.
4. **Y – YIELD:** Progress clean working tree on disk, commit upon **Exit Code 0**, or trip the circuit breaker cleanly when bounds are reached.

---

## 🏛️ The 4-Layer Citadel Architecture

```mermaid
flowchart TB
    subgraph Citadel["The 4 Core Subsystems of the Citadel"]
        direction TB

        subgraph Block01["BLOCK 01 · SPECIFICATION (Contract Engine)"]
            B1A["• task-spec.json contract"]
            B1B["• Whitelist target file paths"]
            B1C["• Explicit error status codes & schemas"]
            B1D["• Zero conversational noise"]
            B1E["Boundary: Input Validation"]
        end

        subgraph Block02["BLOCK 02 · ORCHESTRATION (Cold-Start Worker)"]
            B2A["• Isolated OS subshell"]
            B2B["• 180s hard execution timer"]
            B2C["• Process termination after mutation"]
            B2D["• 0 token memory leakage"]
            B2E["Boundary: Process Isolation"]
        end

        subgraph Block03["BLOCK 03 · VERIFICATION (Tri-Gate Gatekeepers)"]
            B3A["• Gate A: Lint & Style (Pint / ESLint)"]
            B3B["• Gate B: Strict Types (PHPStan L8 / tsc)"]
            B3C["• Gate C: Feature Tests (Pest / Jest)"]
            B3D["• Objective binary exit codes"]
            B3E["Boundary: Compilation & Tests"]
        end

        subgraph Block04["BLOCK 04 · CITADEL (Blast Radius Sentinel)"]
            B4A["• Disposable agent/* git branch"]
            B4B["• Air-gapped network socket"]
            B4C["• Read-only secret vault (.env)"]
            B4D["• $1.50 financial / loop killswitch"]
            B4E["Boundary: Safety Containment"]
        end

        Block01 --> Block02 --> Block03 --> Block04
    end
```

---

## ⚔️ Conversational Chat Trap vs. Cold-Start Pressure Cooker

```mermaid
flowchart TD
    subgraph ChatTrap["✕ Conversational Chat Trap (Linear Degradation)"]
        direction TB
        P1["Step 1: Vague Chat Prompt<br/>(~2.5k tokens)"] --> E1["Step 2: Unverified Edit & SQL Error<br/>5k error trace dumped to chat (~12k tokens)"]
        E1 --> W1["Step 3: Sycophantic Whack-a-Mole<br/>Apologizes, patches query, breaks DB schema (~38k tokens)"]
        W1 --> C1["Final Result: Context Collapse<br/>Agent claims complete, build broken (80k+ tokens lost)"]
    end

    subgraph PressureCooker["✓ Ralph Cold-Start Pressure Cooker (Verified Cycles)"]
        direction TB
        C01["Cycle 01: task-spec.json Contract<br/>180s timer, subshell terminated after edit (0 Chat Tokens)"] --> T1["Tri-Gate Gatekeeper: Binary Verification<br/>Pint + PHPStan + Artisan (Exit 1 saved to disk XML)"]
        T1 --> C02["Cycle 02: Fresh Cold-Start Agent<br/>Reads disk diff + JUnit XML, patches root cause cleanly"]
        C02 --> T2["Tri-Gate Gatekeeper: Binary Verification<br/>Pint + PHPStan + Artisan (100% Green, Exit 0)"]
        T2 --> Green["Final Result: Deterministic Commit<br/>All 3 gates exit 0, git commit & push (0 Token Bleed)"]
    end
```

---

## 🛡️ Tri-Gate Verification Gateway

```mermaid
flowchart TD
    subgraph TriGate["The Tri-Gate Convergence Barrier"]
        direction TB
        GateA["Gate A: Code Style (Pint / PSR-12 / ESLint)<br/>• Enforce code style & formatting<br/>• Line length standardization<br/>• Unused import cleanup"]
        GateB["Gate B: Static Typing (PHPStan Level 8 / tsc)<br/>• Strict static type assertions<br/>• Non-null guarantees<br/>• Verified parameter & method contracts"]
        GateC["Gate C: Runtime Tests (Pest / Artisan / Jest)<br/>• Real database state verification<br/>• 100% green feature & unit assertions<br/>• Zero regression baseline"]

        GateA --> Convergence{"Binary Tri-Gate Convergence"}
        GateB --> Convergence
        GateC --> Convergence

        Convergence -- "Any Gate Fails (Exit != 0)" --> Reject["ABORT & LOG<br/>Capture exact stdout/stderr to disk; loopback with cold start"]
        Convergence -- "All Gates Pass (Exit == 0)" --> Certified["CENTRAL INTERSECTION<br/>Zero Hallucination · Production Verified · Exit 0"]
    end
```

---

## 🔬 Simulation Replay · Pressure Cooker in Action

<details open>
<summary><strong>Attempt 01 · RUNTIME FAILURE (Exit Code: 1)</strong></summary>

```console
$ [INFO] Attempt 1/10 initiated with prompt spec: auth-task.json
$ [AGENT] Generated: app/Http/Controllers/Api/CustomerAuthController.php
$ [TEST] Running: php artisan test --filter=CustomerAuthTest

• Tests\Feature\CustomerAuthTest > customer_can_authenticate ................. FAIL (0.12s)
  ---
  Failed asserting that 500 matches expected 200.
  Exception: Illuminate\Database\QueryException
  SQLSTATE[23000]: Integrity constraint violation: Column 'email' cannot be null
  ---
• Tests\Feature\CustomerAuthTest > customer_receives_sanctum_token .......... FAIL (0.04s)

$ [STATIC-ANALYSIS] vendor/bin/phpstan analyse
  Line 18: Method CustomerAuthController::login() has parameter $request with no typehint specified.
  Line 24: Access to undefined property $request->email.

[RESULT] 2 FAILED, 0 PASSED (Exit code: 1). Working tree dirty. Iteration aborted.
```

> **Diagnosis:** Context Poisoning avoided. No human intervened. The failure was caught immediately by the deterministic test suite and compiler. The dirty code remains on disk for the next fresh agent to inspect.  
> **Automated Next Action:** Create dedicated FormRequest (`LoginCustomerRequest`) and typehint dependencies.
</details>

<details>
<summary><strong>Attempt 02 · PROGRESS WARNING (Exit Code: 1)</strong></summary>

```console
$ [INFO] Attempt 2/10 initiated (Tabula Rasa Cold-Start)
$ [AGENT] Generated: app/Http/Requests/LoginCustomerRequest.php
$ [AGENT] Patched: app/Http/Controllers/Api/CustomerAuthController.php
$ [STATIC-ANALYSIS] vendor/bin/phpstan analyse
  [OK] No errors found. (PHPStan Level 8)

$ [TEST] Running: php artisan test --filter=CustomerAuthTest
• Tests\Feature\CustomerAuthTest > customer_can_authenticate ................. PASS (0.08s)
• Tests\Feature\CustomerAuthTest > customer_receives_sanctum_token .......... WARN (0.05s)
  ---
  Call to undefined method App\Models\Customer::createToken()
  ---

[RESULT] 1 PASSED, 1 WARNING (Exit code: 1). Sanctum HasApiTokens trait missing on Customer model.
```

> **Diagnosis:** Static typing passed. The SQL constraint was resolved cleanly via FormRequest. Second feature test caught missing API token trait on model.  
> **Automated Next Action:** Import and use `Laravel\Sanctum\HasApiTokens` in `Customer` model.
</details>

<details open>
<summary><strong>Attempt 03 · 100% GREEN CONVERGENCE (Exit Code: 0)</strong></summary>

```console
$ [INFO] Attempt 3/10 initiated (Tabula Rasa Cold-Start)
$ [AGENT] Added HasApiTokens to app/Models/Customer.php
$ [LINT] vendor/bin/pint --test
  PASS   12 files linted, 0 issues found. (PSR-12 Certified)

$ [STATIC-ANALYSIS] vendor/bin/phpstan analyse --level=8
  [OK] No errors found. Non-null guarantees verified.

$ [TEST] Running: php artisan test --filter=CustomerAuthTest
• Tests\Feature\CustomerAuthTest > customer_can_authenticate ................. PASS (0.06s)
• Tests\Feature\CustomerAuthTest > customer_receives_sanctum_token .......... PASS (0.04s)
• Tests\Feature\CustomerAuthTest > invalid_credentials_returns_422 ......... PASS (0.03s)

[RESULT] 3 PASSED, 0 FAILED (Exit code: 0). 100% Green Convergence! All 3 gates passed.
$ git commit -m "feat: complete customer authentication with FormRequest and Sanctum tokens"
```

> **Diagnosis:** All three binary gates (Pint, PHPStan Level 8, Pest feature test suite) passed with Exit Code 0.  
> **Outcome:** Production verified. Zero hallucination. Git commit pushed cleanly with 0 conversational token bleed.
</details>

---

## 🌲 Senior Loop Triage Heuristics & Antipatterns

| Antipattern | System Failure Mode | Root Cause | Senior Heuristic Resolution (The Fix) |
| :--- | :--- | :--- | :--- |
| **01 · Ping-Pong Thrash** | Agent alternates cyclically between Approach A and Approach B, breaking tests alternately. | Agent lacks memory of recent failures and assumes the alternative approach will succeed. | **Inject Multi-Attempt Diffs:** Inject the unified git diff and failure outputs of the last 2 failed attempts into the prompt so the agent sees past dead-ends. |
| **02 · Flaky Test Poisoning** | Tests pass or fail intermittently across iterations without code changes. | Tests depend on `now()`, unseeded `rand()`, or unseeded database ordering. | **Enforce Determinism:** Freeze system clocks with `Carbon::setTestNow()`, seed random number generators, and isolate tests within database transactions or in-memory SQLite. |
| **03 · Specification Vacuum** | Agent writes code that passes shallow unit tests but violates client API expectations. | Vague prompt or missing integration contracts allow the agent to satisfy superficial assertions. | **True TDD Pre-Flight:** Pre-write failing Pest/Artisan tests and strict JSON schema contracts *before* launching the implementation loop. |
| **04 · Sycophantic Apology Drift** | Agent outputs verbose apologies and claims success without verification. | Chat-based conversational bias and lack of binary gate enforcement. | **Zero-Chat Subshell Rule:** Forbid chat conversational responses. Evaluate progress strictly via binary exit codes (`0` vs `1`) from compiler and test runners. |

---

## 🎮 How to Activate DORY in Your Agent

Trigger DORY at any time in your AI chat or coding prompt:
- *"Use DORY to implement customer authentication"*
- *"`/dory` fix the failing feature tests"*
- *"Just keep coding until all tests are green (AFK mode)"*
- *"Run in DORY mode with max_iterations=5"*

---

## 📂 Repository Layout

```text
dory/
├── dory/
│   ├── dory.png           # Mascot branding
│   └── SKILL.md           # Mirror entrypoint
├── skills/
│   └── dory/
│       └── SKILL.md       # Primary Agent Skills entrypoint
├── skills.sh.json         # skills.sh discovery manifest
├── plugin.json            # Open agent plugin manifest
├── package.json           # npm & package manager metadata
├── context.md             # Systems architecture & Mermaid schematics
├── skills.md              # Original master prompt specification
├── index.html             # Visual masterclass case study & terminal replay
└── README.md
```

---

## 📄 License

MIT © [CodeWithTeds](https://github.com/CodeWithTeds)
