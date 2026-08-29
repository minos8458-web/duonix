# DUONIX Control Tower Session State

Session: `No.4 [DUONIX] 00 Control Tower`  
Status: ACTIVE

## 1. Major Work Unit Count

Current count: **6**

Completed major work units:

1. No.3 state recovery and reconstructed baseline disposition.
2. Attempt-3 runner provenance and exact artifact recovery disposition.
3. Attempt-3 initial Pre-Execution Runner Artifact Validation disposition — FAIL/HOLD with four runner-level blockers.
4. Attempt-3 runner remediation loop — R2 reduced blockers to one; R3 independently validated `FINAL PASS / blockers 0`; Control Tower closed the remediation loop.
5. Attempt-3 Official Build / post-build evidence cycle — Official Build executed and consumed successfully; initial independent post-build Validation returned `FINAL FAIL / blocker 1`, and Control Tower held promotion for executing-runner provenance remediation only.
6. Attempt-3 executing-runner provenance remediation — read-only Windows event recovery plus independent focused 70 revalidation closed the sole blocker and revised post-build Validation to `FINAL PASS / blockers 0`.

Rotation band: **CONTINUE**

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
- historical R1/R2 remain non-authoritative for execution.

Known metadata-only defect for this historical run:
- exact R3 source contains `$RunnerRevision = 'OBR-A3-CPU-SPEED-SLIDER-DIRECTION-FIX-R2'`.
- focused independent revalidation determined this stale label no longer creates execution-authority ambiguity because OS ScriptBlock logging independently binds the executed code to the R3-only correction.

## 5. Official Build Attempt 3

Persistent authorities and independently validated post-build package establish:
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

## 6. Freeze Candidate

Exact freeze candidate independently validated:
- filename: `duonix-app-lc-01-cpu-speed-slider-direction-fix-a3-dist-freeze-candidate.zip`
- SHA-256: `829b43ca4dd58c23de4ddc64b3297c87d8c3be940b690d63850a95bf15dd89cc`
- bytes: `79,435`
- file count: `2`
- raw-dist manifest consistency: PASS
- direct semantic-network validation: PASS
- external runtime dependency: `0`
- unclassified fetch: `0`
- missing local runtime asset: `0`
- build-workspace leak: `0`
- `official_frozen_dist = false`

This remains a **freeze candidate**, not yet an Official Frozen Dist.

## 7. Focused Runner-Provenance Revalidation

Previous sole blocker:
`LC-01-A3-POST-IV-EXECUTING-RUNNER-IDENTITY-BINDING-01`

Independent focused `[DUONIX] 70 Validation / Integration` result:
- `FOCUSED RUNNER-PROVENANCE REVALIDATION = FINAL PASS`
- blocker = **CLOSED**
- blocker count = `0`

Accepted evidence includes:
- Windows PowerShell engine start/stop bound to exact R3 `HostApplication`,
- execution ProcessID `23964`, common HostId and RunspaceId,
- Operational Event ID `4104` ScriptBlock fragments `1/8` through `8/8`,
- common ScriptBlockId `d0b24578-9197-407c-9abf-ba84aae5ef49`,
- exact R3 path on the captured ScriptBlock authority,
- executed ScriptBlock text includes the R3-only fail-closed correction rejecting leading `./`,
- PSReadLine history corroborates exact approved R3 SHA guard and child `-Command` invocation,
- OS execution interval contains the independently validated Attempt-3 reservation and launch timestamps.

Recovery report authority recorded by the recovery tool:
- SHA-256: `60815da5917438592e6fbd4cdc326cb7208f3e1f3c8becf2cbcd03ac74880845`
- bytes: `449,575`
- recovery execution of R3: `0`
- recovery execution of Official Build: `0`

Security 4688 matching evidence was unavailable and Sysmon Operational was unavailable; focused Validation determined positive Windows PowerShell / ScriptBlock provenance was sufficient.

## 8. Revised Independent Post-Build Validation

The initial post-build Validation had exactly one blocker. That blocker is now independently CLOSED.

Current authoritative result:
- `POST-BUILD EVIDENCE / ARTIFACT VALIDATION = FINAL PASS`
- `BLOCKER COUNT = 0`
- freeze candidate content PASS: unchanged
- exact executing R3 binding: sufficiently established
- rebuild / rerun required: NO

Galaxy Validation: **NOT EXECUTED**.
Official Frozen Dist: **NOT DECLARED**.

## 9. Control Tower Disposition

Control Tower accepts the focused revalidation and closes `LC-01-A3-POST-IV-EXECUTING-RUNNER-IDENTITY-BINDING-01`.

Current release disposition:
- Official Build Attempt 3 post-build evidence/artifact gate: **PASS / CLOSED**.
- freeze candidate is **ELIGIBLE FOR A SEPARATELY CONTROLLED OFFICIAL FROZEN DIST PROMOTION STEP**.
- `official_frozen_dist` remains `false` until that promotion step is independently evidenced.
- Galaxy Validation remains **NOT EXECUTED / NOT YET AUTHORIZED**.
- `LC01-MOB-06+` remains HOLD.
- `LC-02` remains inactive.
- R3 / Official Build rerun remains prohibited.
- no marker replacement, retrospective evidence rewriting, or application-source modification is authorized.

Major work unit count is **6**; rotation remains **CONTINUE**.

## 10. Next Single Action

**Hand the exact independently validated freeze candidate SHA-256 `829b43ca4dd58c23de4ddc64b3297c87d8c3be940b690d63850a95bf15dd89cc` to `[DUONIX] 80 Build / Release` for a promotion-only disposition: verify the candidate identity, preserve payload bytes unchanged, create explicit promotion/receipt evidence that distinguishes candidate from Official Frozen Dist, and return the result to Control Tower. Do not rebuild, rerun R3, run Galaxy Validation, deploy, or advance LC01-MOB-06+ in the same step.**
