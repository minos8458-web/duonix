# DUONIX Control Tower Session State

Session: `No.4 [DUONIX] 00 Control Tower`  
Status: ACTIVE

## 1. Major Work Unit Count

Current count: **4**

Completed major work units:

1. No.3 state recovery and reconstructed baseline disposition.
2. Attempt-3 runner provenance and exact artifact recovery disposition.
3. Attempt-3 initial Pre-Execution Runner Artifact Validation disposition — FAIL/HOLD with four runner-level blockers.
4. Attempt-3 runner remediation loop — R2 reduced blockers to one; R3 independently validated `FINAL PASS / blockers 0`; Control Tower closed the remediation loop.

Rotation band: **CONTINUE**

The Official Build Attempt 3 execution cycle remains open and is not counted as another completed major work unit until generated build evidence/artifacts are independently validated and Control Tower disposes the result.

## 2. Baseline

Legacy reference:
- `duonix-play-3.html`

Current canonical source artifact:
- filename: `duonix-app-lc-01-cpu-speed-slider-direction-fix-handoff.zip`
- SHA-256: `41f4dea1c532afe38b53dbd2684fa5222f98a838bd9e5e06f8112866d0fd75e9`
- bytes: `1,504,018`
- files: `416`
- directories: `62`
- required `scripts.build`: `node scripts/build.mjs`

Toolchain D:
- filename: `duonix-app-lc-01-toolchain-win-x64-node24.18.0-npm11.16.0.zip`
- SHA-256: `9e13ed3129cae04692143d4b07419cc98c1f2fc2561d72895c8135eb2abd86ec`
- internal manifest SHA-256: `3064ed4fa2e7a90fe2f5422055a3ea9d7abaf14fe9a0d2e460bd9eaf0097cbaa`

GitHub operations repository:
- `minos8458-web/duonix`
- current LC-01 application source has **not yet been migrated into this repository**.

Git base branch / commit for current LC-01 application source artifact: `미확인`.  
Working branch / latest application-source commit: `미확인`.

## 3. Active Milestone

Milestone: `LC-01`  
Status: `ACTIVE / NOT COMPLETE`

Current gates:
- `LC01-MOB-06+ = HOLD`
- `LC-02 = NOT ACTIVE`

## 4. Exact R3 Runner Authority

- filename: `DUONIX-LC01-OFFICIAL-BUILD-FREEZE-A3-WINDOWS-R3.ps1`
- SHA-256: `8f6d67ce4af29a2812c2a181bb712edf57940e450dd8a70c30a9a1d6a8dfda07`
- bytes: `138535`
- lines: `2709`
- independent pre-execution Validation: `FINAL PASS / blockers 0`

Historical R1 and R2 runners remain non-authoritative for execution.

## 5. Corrected Attempt-3 Execution State

A previous Windows wrapper returned `DUONIX_R3_CHILD_EXITCODE=0`, but direct evidence recovery proved all mandatory R3 side effects absent. That wrapper result is therefore not accepted as evidence that R3 executed.

Current authoritative state:
- Official Build Attempt 3: **NOT EXECUTED / NOT CONSUMED**
- Official Build lifetime invocation count: **2**
- Attempt-3 reservation marker: **ABSENT**
- Attempt-3 launched marker: **ABSENT**
- Attempt-3 BuildRoot: **ABSENT**
- Attempt-3 evidence/log/artifact directories: **ABSENT**
- Attempt-3 freeze candidate: **ABSENT**
- Galaxy Validation: **NOT EXECUTED**

## 6. Windows Invocation / Transport Findings

Confirmed:
- exact R3 identity matches authority,
- Windows PowerShell parser errors = `0`,
- R3 main `try` AST exists,
- child PowerShell `-Command` transport works and propagates exit codes,
- disposable child `-File` transport works and propagates exit codes,
- child process launched with `-ExecutionPolicy Bypass` has effective policy `Bypass` and no MachinePolicy/UserPolicy override.

Downloaded R3 originally carried:
- `Zone.Identifier`, length `328`, `ZoneId=3`,
- `RVContext`, length `60`,
- Authenticode status `NotSigned`.

Transport normalization executed with `Unblock-File` only.

Post-normalization direct verification:
- R3 SHA-256 = `8f6d67ce4af29a2812c2a181bb712edf57940e450dd8a70c30a9a1d6a8dfda07`
- bytes = `138535`
- lines = `2709`
- `IDENTITY_UNCHANGED=True`
- `Zone.Identifier` = **ABSENT**
- `RVContext` = **PRESENT**
- `R3_EXECUTION=0`

Therefore the approved R3 default data stream was not modified. Only the Internet-zone transport metadata was removed.

Causal attribution:
- `Zone.Identifier` / downloaded-script context remains the strongest differential from the successful local probe,
- but because the child process effective policy was already `Bypass`, Control Tower does **not** claim that MOTW was proven as the sole cause of the first no-side-effect invocation.

## 7. Transport Blocker Disposition

`LC-01-A3-WIN-INVOCATION-TRANSPORT-01`

Status: **SUFFICIENTLY MITIGATED FOR A CONTROLLED ONE-TIME EXECUTION**.

Rationale:
- exact R3 parser is clean,
- exact R3 identity is unchanged,
- generic child `-Command` transport is directly proven,
- Internet-zone ADS has been removed without modifying R3 `$DATA`,
- Attempt 3 remains unconsumed and all execution guards are clean.

This does not retroactively prove the root cause of the earlier wrapper anomaly.

## 8. Control Tower Authorization

Control Tower authorizes **exactly one** Official Build Attempt 3 execution of the exact R3 identity above, using a corrected Windows PowerShell child `-Command` transport only.

Mandatory preconditions immediately before launch:
- exact R3 SHA/bytes/lines still match,
- `Zone.Identifier` remains absent,
- Attempt-3 reservation marker absent,
- Attempt-3 launched marker absent,
- exact Attempt-3 BuildRoot absent.

After this authorized launch command is issued, **do not execute R3 again regardless of exit code or visible output** until persistent markers/evidence are inspected.

Still unauthorized:
- R1/R2 execution,
- previous failed/no-side-effect wrapper reuse,
- manual marker creation,
- manual BuildRoot creation,
- any automatic retry,
- Galaxy Validation,
- Official Frozen Dist promotion,
- LC01-MOB-06+ progression,
- LC-02 activation,
- source modification.

## 9. Next Single Action

**Execute the exact R3 once through the newly authorized child `-Command` transport after the mandatory identity/guard checks, then return the complete terminal output. Do not rerun R3 under any outcome.**
