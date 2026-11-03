# Deterministic Test Gates, Context Degradation Elimination, and Self-Healing AFK Engineering

> **VISUAL BLUEPRINT & SYSTEMS ARCHITECTURE SPECIFICATION**  
> High-density systems architecture schematics and operational execution directives for autonomous, cold-start coding loops. Pure engineering topology with zero conversational drift.

---

## System Key Performance Indicators (KPIs)

| Domain | Architectural Guarantee | Mechanism | Target Metric |
| :--- | :--- | :--- | :--- |
| **Context Retention** | 100% Cold Starts | Tabula Rasa subshell isolation; state stored on disk, not chat history | **0 Token Bleed** |
| **Evaluation** | Deterministic Binary Gates | Non-negotiable Tri-Gate (Pint PSR-12, PHPStan Level 8, Pest/Artisan) | **Exit Code 0 or 1** |
| **Human Workload** | AFK Autonomous Engineering | Automated diagnostic loopback and senior triage heuristics | **Zero Babysitting** |
| **Safety Bounds** | Blast Radius Containment | Disposable git branches (`agent/*`), locked sandboxes, circuit breakers | **Zero Blast Leak** |

---

## 1. Visual Schematics & Architectural Topology

### Schematic 01 · Flowchart: Context Collapse vs. Ralph Cold-Start Pressure Cooker

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

### Schematic 02 · UML Sequence Diagram: Cold-Start Process Lifecycle & Gatekeeper

```mermaid
sequenceDiagram
    autonumber
    participant Orch as Loop Orchestrator
    participant Spec as task-spec.json
    participant Worker as Cold-Start Worker (Subshell)
    participant Disk as Workspace Disk
    participant Gate as Tri-Gate Barrier
    participant Git as Git Version Control

    Orch->>Spec: Ingest task contract & whitelisted file paths
    Note over Orch,Worker: Cycle 01 (Tabula Rasa - 0 In-Memory Tokens)
    Orch->>Worker: Spawn isolated worker (Hard timeout: 180s)
    Worker->>Disk: Apply targeted mutations strictly to whitelisted files
    Orch->>Worker: Terminate worker process immediately after edit
    Orch->>Gate: Execute Gate A (Pint PSR-12 Lint)
    Orch->>Gate: Execute Gate B (PHPStan Level 8 Static Analysis)
    Orch->>Gate: Execute Gate C (Pest Feature & Runtime Tests)
    
    alt Tri-Gate Returns Exit Code 1
        Gate-->>Disk: Stream JUnit XML & compiler telemetry to disk
        Note over Orch,Worker: Cycle 02 (Fresh Process, 0 Token Bleed)
        Orch->>Worker: Spawn fresh agent; inject disk diff + JUnit telemetry
        Worker->>Disk: Apply root-cause patch based on telemetry
        Orch->>Worker: Terminate worker process
        Orch->>Gate: Re-run Tri-Gate Verification
    end

    Gate-->>Orch: All gates return Exit Code 0 (100% Green)
    Orch->>Git: git commit -m "feat: verified implementation" && git push
```

---

### Schematic 03 · Tri-Gate Convergence Architecture

```mermaid
flowchart TD
    subgraph TriGate["The Tri-Gate Convergence Barrier"]
        direction TB
        GateA["Gate A: Code Style (Pint / PSR-12)<br/>• Enforce PSR-12 code style<br/>• Line length & format standardization<br/>• Unused import cleanup"]
        GateB["Gate B: Static Typing (PHPStan Level 8)<br/>• Strict static type assertions<br/>• Non-null guarantees<br/>• Verified parameter & method contracts"]
        GateC["Gate C: Runtime Tests (Pest / Artisan)<br/>• Real database state verification<br/>• 100% green feature & unit assertions<br/>• Zero regression baseline"]

        GateA --> Convergence{"Binary Tri-Gate Convergence"}
        GateB --> Convergence
        GateC --> Convergence

        Convergence -- "Any Gate Fails (Exit != 0)" --> Reject["ABORT & LOG<br/>Capture exact stdout/stderr to disk; loopback with cold start"]
        Convergence -- "All Gates Pass (Exit == 0)" --> Certified["CENTRAL INTERSECTION<br/>Zero Hallucination · Production Verified · Exit 0"]
    end
```

---

### Schematic 04 · Data Flow Diagram (DFD Level 1): Artifact Transforms

```mermaid
flowchart LR
    Spec[("task-spec.json<br/>Contract Specification")] -->|1. Ingest Whitelist & Rules| Worker["Cold-Start Worker<br/>(Isolated OS Subshell)"]
    Worker -->|2. Targeted Code Mutation| Disk[("Workspace Disk<br/>(Git Working Tree)")]
    Disk -->|3. Trigger Verification| Gates["Tri-Gate Engine<br/>(Pint / PHPStan / Pest)"]
    Gates -->|4a. Exit != 0 Telemetry| Telemetry[("Disk Telemetry<br/>junit.xml / errors.log")]
    Telemetry -->|5. Diff & Error Injection| Worker
    Gates -->|4b. Exit == 0 Verified| Commit["Git Production Commit<br/>(Clean Tree)"]
```

---

### Schematic 05 · Block Diagram: The 4-Layer Citadel Architecture

```mermaid
flowchart TB
    subgraph Citadel["The 4 Core Subsystems of the Citadel"]
        direction TB

        subgraph Block01["BLOCK 01 · SPECIFICATION (Contract Engine)"]
            B1A["• task-spec.json contract"]
            B1B["• Whitelist file paths only"]
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
            B3A["• Pint style checker"]
            B3B["• PHPStan Level 8 static types"]
            B3C["• Pest feature test suite"]
            B3D["• Objective binary exit codes"]
            B3E["Boundary: Compilation & Tests"]
        end

        subgraph Block04["BLOCK 04 · CITADEL (Blast Radius Sentinel)"]
            B4A["• Disposable agent/* git branch"]
            B4B["• Air-gapped network socket"]
            B4C["• Read-only secret vault"]
            B4D["• $1.50 financial / loop killswitch"]
            B4E["Boundary: Safety Containment"]
        end

        Block01 --> Block02 --> Block03 --> Block04
    end
```

---

### Schematic 06 · Spider Mind Map: Ralph Wiggum Autonomous Topology

```mermaid
flowchart TD
    Root["Ralph Wiggum Autonomous Loop"]

    Root --> M1["Context Retention"]
    M1 --> M1A["Tabula Rasa Isolation"]
    M1 --> M1B["0 Token Bleed"]
    M1 --> M1C["Disk as Single Source of Truth"]

    Root --> M2["Verification Gateway"]
    M2 --> M2A["Gate A: Pint / PSR-12 Style"]
    M2 --> M2B["Gate B: PHPStan Level 8 Types"]
    M2 --> M2C["Gate C: Pest / Artisan Tests"]

    Root --> M3["Citadel Sentinel"]
    M3 --> M3A["Disposable agent/* Branches"]
    M3 --> M3B["180s Hard Execution Boundaries"]
    M3 --> M3C["Circuit Breakers ($1.50 / Max Iterations)"]

    Root --> M4["Senior Triage"]
    M4 --> M4A["Anti-Ping-Pong Multi-Diff Memory"]
    M4 --> M4B["Frozen Time & Seeded DB Isolation"]
    M4 --> M4C["True TDD Pre-Flight Contracts"]
```

---

## 2. Simulation Replay · Live Pressure Cooker Trace

### Interactive Attempt Trace

```text
[Attempt 01]  FAIL (SQL Null constraint violation & PHPStan parameter missing)
[Attempt 02]  WARN (Missing Trait & missing FormRequest injection)
[Attempt 03]  PASS (100% Green across all 3 gates · Exit 0)
```

### Terminal Session · Iteration 01 Trace (Runtime Failure)

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

#### Diagnostic Evaluation:
> [!NOTE] Context Poisoning Avoided
> No human intervened. The failure was caught immediately by the deterministic test suite and compiler. The dirty code remains on disk for the next fresh agent to inspect.

#### Automated Next Action:
1. Create dedicated `FormRequest` (`LoginCustomerRequest`) with strict validation rules.
2. Typehint dependency injection in `CustomerAuthController::login(LoginCustomerRequest $request): JsonResponse`.
3. Re-run Gate B (PHPStan) and Gate C (Pest).

---

## 3. Senior Loop Triage Heuristics & Antipattern Tree

| Antipattern | System Failure Mode | Root Cause | Senior Heuristic Resolution (The Fix) |
| :--- | :--- | :--- | :--- |
| **01 · Ping-Pong Thrash** | Agent alternates cyclically between Approach A and Approach B, breaking tests alternately. | Agent lacks memory of recent failures and assumes the alternative approach will succeed. | **Inject Multi-Attempt Diffs:** Inject the unified git diff and failure outputs of the last 2 failed attempts into the prompt so the agent sees past dead-ends. |
| **02 · Flaky Test Poisoning** | Tests pass or fail intermittently across iterations without code changes. | Tests depend on `now()`, unseeded `rand()`, or unseeded database ordering. | **Enforce Determinism:** Freeze system clocks with `Carbon::setTestNow()`, seed random number generators, and isolate tests within database transactions or in-memory SQLite. |
| **03 · Specification Vacuum** | Agent writes code that passes shallow unit tests but violates client API expectations. | Vague prompt or missing integration contracts allow the agent to satisfy superficial assertions. | **True TDD Pre-Flight:** Pre-write failing Pest/Artisan tests and strict JSON schema contracts *before* launching the implementation loop. |
| **04 · Sycophantic Apology Drift** | Agent outputs verbose apologies and claims success without verification. | Chat-based conversational bias and lack of binary gate enforcement. | **Zero-Chat Subshell Rule:** Forbid chat conversational responses. Evaluate progress strictly via binary exit codes (`0` vs `1`) from compiler and test runners. |

---

## 4. Master Prompt Directives for Autonomous Agents

When operating under this architecture, the agent must adhere to the following non-negotiable execution laws:

```text
================================================================================
AUTONOMOUS EXECUTION DIRECTIVE: RALPH WIGGUM COLD-START PRESSURE COOKER
================================================================================

1. ZERO CONVERSATIONAL DRIFT:
   - Do not apologize, explain intentions, or generate conversational filler.
   - Your state is defined entirely by the git working tree, task-spec.json, and terminal output.

2. SPECIFICATION FIRST (BLOCK 01):
   - Never touch application logic without an explicit acceptance contract and a whitelisted list of target files.
   - If tests do not exist, write failing behavioral tests first (True TDD).

3. TRI-GATE CONVERGENCE MANDATE (BLOCK 03):
   - You are prohibited from claiming task completion until ALL THREE gates return Exit Code 0:
     * Gate A (Style): Linting / PSR-12 clean with zero unused imports.
     * Gate B (Types): Static analysis at highest strictness level (e.g., PHPStan Level 8).
     * Gate C (Runtime): 100% passing unit & feature test suite.

4. COLD-START ISOLATION (BLOCK 02):
   - On each failed attempt, persist failure logs (stdout/stderr/JUnit) to disk.
   - Treat each repair attempt as a cold start: inspect git diff, analyze failure telemetry, apply minimal root-cause patch.

5. SENIOR HEURISTIC TRIAGE:
   - Check against Ping-Pong thrashing: Never re-apply an approach attempted in the prior 2 cycles.
   - Isolate test determinism: Freeze time and database seeds.
   - Never disable, comment out, or weaken existing tests to simulate a pass.

6. CITADEL BOUNDARIES (BLOCK 04):
   - Abort and trip the circuit breaker if the maximum iteration limit (default 10) or financial threshold is reached.
   - Provide a factual, binary-verified delivery report upon reaching Exit Code 0 across all gates.
================================================================================
```
