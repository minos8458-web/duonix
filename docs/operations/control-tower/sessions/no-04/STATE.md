# DUONIX Control Tower Session State

Session: `No.4 [DUONIX] 00 Control Tower`  
Status: ACTIVE

## 1. Major Work Unit Count

Current count: **5**

Completed major work units:

1. No.3 state recovery and reconstructed baseline disposition.
2. Attempt-3 runner provenance and exact artifact recovery disposition.
3. Attempt-3 initial Pre-Execution Runner Artifact Validation disposition — FAIL/HOLD with four runner-level blockers.
4. Attempt-3 runner remediation loop — R2 reduced blockers to one; R3 independently validated `FINAL PASS / blockers 0`; Control Tower closed the remediation loop.
5. Attempt-3 Official Build / post-build evidence cycle — Official Build executed and consumed successfully; independent post-build Validation completed `FINAL FAIL / blocker 1`; Control Tower disposition = HOLD for executing-runner identity provenance remediation only.

Rotation band: **CONTINUE**

The active post-build blocker now has newly recovered read-only Windows execution provenance. Control Tower considers the new evidence materially responsive to the blocker, but the blocker is not closed until independent `[DUONIX] 70 Validation / Integration` focused revalidation.

## 2. Baseline

Legacy reference: `duonix-play-3.html`

Current canonical source artifact:
- filename: `duonix-app-lc-01-cpu-speed-slider-direction-fix-handoff.zip`
- SHA-256: `41f4dea1c532afe38b53dbd2684fa5222f98a838bd9e5e06f8112866d0fd75e9`
- bytes: `1,504,018`
- files: `416`
- directories: `62`
- required `scripts.build`: `node scripts/build.mjs`

Toolchain D authority:
- filename: `duonix-app-lc-01-toolchain-win-x64-node24.18.0-npm11.16.0.zip`
- bytes: `51,403,257`
- SHA-256: `9e13ed3129cae04692143d4b07419cc98c1f2fc2561d72895c8135eb2abd86ec`
- internal manifest SHA-256: `3064ed4fa2e7a90fe2f5422055a3ea9d7abaf14fe9a0d2e460bd9eaf0097cbaa`

GitHub operations repository: `minos8458-web/duonix`.
Current LC-01 application source has not yet been migrated into this repository.
Git base branch / commit and working branch for the current source artifact: `미확인`.

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
- `Zone.Identifier` removed before successful invocation; default-stream SHA/bytes/lines remained unchanged.

Historical R1/R2 remain non-authoritative for execution.
Known metadata discrepancy remains: exact R3 source contains `$RunnerRevision = 'OBR-A3-CPU-SPEED-SLIDER-DIRECTION-FIX-R2'`.

## 5. Official Build Attempt 3

Persistent authorities and independently inspected post-build package establish:
- Attempt-3 reservation: PRESENT
- Attempt-3 launch: PRESENT
- canonical command: `npm run build`
- package build script: `node scripts/build.mjs`
- Official Build exit code: `0`
- retry performed: `false`
- lifetime invocation count: **3**
- Attempt 3: **CONSUMED**
- R3 / Official Build rerun: **PROHIBITED**

Successful transfer package:
- `DUONIX-LC01-A3-RESULT-TRANSFER-DIAG-20260829-212230.zip`
- SHA-256: `f2d13b31e9547489329f641874df42542d75294d378f23acdc8c7bd5d3c164dd`
- bytes: `317,904`
- entries: `42`

Freeze candidate independently validated by 70 for content/manifest/semantic-network gates:
- SHA-256: `829b43ca4dd58c23de4ddc64b3297c87d8c3be940b690d63850a95bf15dd89cc`
- bytes: `79,435`
- file count: `2`
- `official_frozen_dist = false`

## 6. Independent Post-Build Validation Result

`[DUONIX] 70 Validation / Integration` result currently remains:
- `POST-BUILD EVIDENCE / ARTIFACT VALIDATION = FINAL FAIL`
- `BLOCKER COUNT = 1`

Active blocker:
`LC-01-A3-POST-IV-EXECUTING-RUNNER-IDENTITY-BINDING-01`

Original basis:
- exact transferred artifact is approved R3,
- internal `RunnerRevision` says R2,
- reservation/launch/result/provenance omit executing-runner SHA/path,
- original package alone did not independently bind the consumed launch to exact R3.

This blocker is provenance-only; product output and freeze-candidate content passed direct Validation.

## 7. Newly Recovered Windows Execution Provenance

Read-only recovery was performed for local execution window `2026-08-29 21:13:00–21:18:00`. No R3 or Build execution occurred during recovery.

Recovery tool output reports:
- report file: `DUONIX-LC01-A3-RUNNER-PROVENANCE-RECOVERY-20260829-224234.txt`
- report SHA-256: `60815da5917438592e6fbd4cdc326cb7208f3e1f3c8becf2cbcd03ac74880845`
- report bytes: `449,575`
- recovery exit code: `0`

### Windows PowerShell / Operational evidence

Recovered events directly record an execution host whose `HostApplication` is:
`powershell.exe -NoProfile -ExecutionPolicy Bypass -Command & '<$HOME>\Downloads\DUONIX-LC01-OFFICIAL-BUILD-FREEZE-A3-WINDOWS-R3.ps1'`

Key bound execution context:
- execution ProcessID: `23964`
- HostId: `841ea67e-1d1d-472f-9fef-774ebc618de4`
- RunspaceId: `3e1cbd58-dec0-4d39-b6e3-c6e307f5202f`
- exact script path: `...\DUONIX-LC01-OFFICIAL-BUILD-FREEZE-A3-WINDOWS-R3.ps1`
- engine start around local `21:14:10.996`
- engine stop around local `21:16:21.173`

`Microsoft-Windows-PowerShell/Operational` contained `29` events in the window and `22` matches to the exact R3 authority/path criteria.

PowerShell ScriptBlock logging (`Event ID 4104`) captured the executing script as **8/8 scriptblock fragments** with:
- one common ScriptBlockId: `d0b24578-9197-407c-9abf-ba84aae5ef49`
- common execution ProcessID `23964`
- exact `Path` ending in `DUONIX-LC01-OFFICIAL-BUILD-FREEZE-A3-WINDOWS-R3.ps1`
- captured source contains Attempt-3 reservation/build-launch/result/provenance logic.

Critically, captured scriptblock fragment 4/8 contains the R3-only correction:
`if ($value.StartsWith('./')) { throw "HTML runtime resource leading current-directory segment is forbidden: $Reference" }`

This differentiates the executed script content from historical R2, whose missing fail-closed handling for leading `./` was the last pre-execution blocker before R3.

### PSReadLine history corroboration

Recovered history includes the exact R3 filename, approved SHA authority, the guarded `$invoke` construction, and child invocation through:
`& $child -NoProfile -ExecutionPolicy Bypass -Command $invoke`

Relevant recovered history includes the final guarded invocation sequence around lines `32746–32808`, including:
- exact R3 runner assignment,
- approved SHA `8f6d67ce4af29a2812c2a181bb712edf57940e450dd8a70c30a9a1d6a8dfda07`,
- `$invoke = "& '" + $runner.Replace("'","''") + "'"`,
- child `-Command $invoke` execution.

Security 4688 had no matching event available; Sysmon Operational was unavailable. Those absences do not negate the positive Windows PowerShell / Operational provenance above.

## 8. Control Tower Interim Assessment

Control Tower assessment of the new evidence:
- the new Windows event data directly binds the historical execution process to the **exact R3 path**,
- ScriptBlock logging binds that same process/path to actual source text containing the **R3-only leading-`./` correction**,
- PSReadLine corroborates the approved R3 SHA guard and child invocation sequence,
- therefore the prior possibility that historical R2 executed instead of R3 is now strongly contradicted by independent OS evidence.

However, Control Tower does **not** unilaterally replace the existing independent Validation result. The blocker remains formally OPEN pending focused 70 revalidation of this newly recovered evidence.

## 9. Current Release State

- Official Frozen Dist promotion: **HOLD pending focused revalidation**.
- `official_frozen_dist`: `false`.
- Galaxy Validation: **NOT EXECUTED / unauthorized**.
- `LC01-MOB-06+`: HOLD.
- `LC-02`: inactive.
- Attempt 3: consumed; lifetime count `3`.
- R3 / Official Build rerun: prohibited.
- no marker replacement, BuildRoot modification, or retrospective evidence rewriting authorized.

Major work unit count remains **5** until focused revalidation and subsequent Control Tower disposition.

## 10. Next Single Action

**Send the newly recovered Windows provenance report together with the unchanged successful Attempt-3 transfer ZIP back to `[DUONIX] 70 Validation / Integration` for focused revalidation of blocker `LC-01-A3-POST-IV-EXECUTING-RUNNER-IDENTITY-BINDING-01` only. 70 must independently determine whether the OS event records and ScriptBlock logging bind the consumed Attempt-3 execution to exact R3 strongly enough to CLOSE the blocker. Do not rerun R3 or Official Build; do not run Galaxy Validation; do not promote Official Frozen Dist before the focused revalidation result returns.**
