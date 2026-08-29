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

The Official Build Attempt 3 execution cycle remains open. No Official Build Attempt 3 reservation, launch marker, BuildRoot, evidence, log, artifact, or freeze-candidate output exists.

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
- Control Tower operations documentation is stored here.
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

A previously approved Windows wrapper invocation returned:
- `DUONIX_R3_CHILD_EXITCODE=0`

That output is **not accepted as evidence of R3 execution** because later read-only evidence recovery proved all mandatory R3 top-level side effects absent:
- Attempt-3 reservation marker: ABSENT
- Attempt-3 launched marker: ABSENT
- Attempt-3 BuildRoot: ABSENT
- Attempt-3 evidence/log/artifact directories: ABSENT
- status JSON: ABSENT
- provenance JSON: ABSENT
- freeze candidate: ABSENT

Therefore:
- Official Build Attempt 3: **NOT EXECUTED / NOT CONSUMED**
- Official Build lifetime invocation count: **2**
- Attempt-3 reservation: **NOT CREATED**
- Attempt-3 launch marker: **NOT CREATED**
- Galaxy Validation: **NOT EXECUTED**

Do not manually create markers or BuildRoot.

## 6. Windows Invocation Transport Diagnostics

Confirmed:
- exact R3 SHA/bytes/lines match authority,
- Windows PowerShell parser error count for R3 = `0`,
- R3 main `try` AST exists,
- child PowerShell `-Command` probe executes and propagates exact exit `23`,
- disposable local child `-File` probe executes, emits sentinel, and propagates exact exit `37`,
- therefore generic Windows PowerShell child `-File` transport is working.

Exact child execution-policy scopes when launched with `-ExecutionPolicy Bypass`:
- MachinePolicy = Undefined
- UserPolicy = Undefined
- Process = Bypass
- CurrentUser = Undefined
- LocalMachine = Undefined
- Effective = Bypass

Exact R3 NTFS streams:
- `:$DATA` length `138535`
- `RVContext` length `60`
- `Zone.Identifier` length `328`

Exact `Zone.Identifier` content confirms Internet-zone transport metadata:
- `[ZoneTransfer]`
- `ZoneId=3`
- ReferrerUrl = ChatGPT conversation URL
- HostUrl = ChatGPT file-download URL

Authenticode:
- status = `NotSigned`
- PowerShell status message states the downloaded script is not digitally signed and cannot execute under the current system context.

Microsoft documentation confirms that Internet-downloaded scripts may carry `Zone.Identifier`, and `Unblock-File` removes that alternate data stream without changing the script's execution policy. The exact R3 main data-stream SHA/bytes/lines remain the artifact authority.

## 7. Current Blocker

`LC-01-A3-WIN-INVOCATION-TRANSPORT-01`

Refined classification:
- `WINDOWS DOWNLOADED-SCRIPT / MARK-OF-THE-WEB EXECUTION CONTEXT`
- NOT Candidate defect
- NOT Toolchain D defect
- NOT R3 parser defect
- NOT generic child `-File` transport defect
- NOT Official Build failure because Official Build never launched

Strongest current hypothesis:
- the downloaded R3's `Zone.Identifier (ZoneId=3)` / downloaded-script trust context is the differentiator between R3 and the successful disposable local `-File` probe.

Root cause status:
- **strongly indicated but not yet proven by an execution after transport normalization**.

## 8. Control Tower Disposition

- Exact R3 remains the independently validated runner authority.
- Attempt 3 remains available because no reservation or launch marker exists.
- Do not modify the R3 main data stream.
- Do not create Attempt-3 markers or BuildRoot manually.
- Do not execute R3 until Control Tower authorizes transport-metadata normalization.
- Galaxy Validation / Official Frozen Dist promotion / LC01-MOB-06+ / LC-02 remain unauthorized.

## 9. Next Single Action

**Normalize only the exact R3 local Windows transport metadata by removing `Zone.Identifier` with `Unblock-File`, then immediately verify that the R3 default-stream SHA-256 / bytes / lines are unchanged and `Zone.Identifier` is absent. Do not execute R3 in the same step. Return the verification output to Control Tower.**
