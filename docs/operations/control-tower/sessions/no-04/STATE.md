# DUONIX Control Tower Session State

Session: `No.4 [DUONIX] 00 Control Tower`  
Status: ACTIVE

## 1. Major Work Unit Count

Current count: **7**

Completed major work units:

1. No.3 state recovery and reconstructed baseline disposition.
2. Attempt-3 runner provenance and exact artifact recovery disposition.
3. Attempt-3 initial Pre-Execution Runner Artifact Validation disposition — FAIL/HOLD with four runner-level blockers.
4. Attempt-3 runner remediation loop — R2 reduced blockers to one; R3 independently validated `FINAL PASS / blockers 0`; Control Tower closed the remediation loop.
5. Attempt-3 Official Build / post-build evidence cycle — Official Build executed and consumed successfully; initial independent post-build Validation returned `FINAL FAIL / blocker 1`, and Control Tower held promotion for executing-runner provenance remediation only.
6. Attempt-3 executing-runner provenance remediation — read-only Windows event recovery plus independent focused 70 revalidation closed the sole blocker and revised post-build Validation to `FINAL PASS / blockers 0`.
7. Official Frozen Dist promotion — Build/Release promotion-only step promoted the already validated immutable candidate by authority-status change only; receipt independently received and identity-checked by Control Tower.

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
- Official Build Attempt 3 post-build gate: **FINAL PASS / CLOSED**
- Official Frozen Dist: **PROMOTED / AUTHORITY ACTIVE**
- Galaxy Validation: **NOT EXECUTED**
- `LC01-MOB-06+ = HOLD`
- `LC-02 = NOT ACTIVE`

## 4. Exact R3 / Attempt-3 Authority

Exact R3 runner:
- filename: `DUONIX-LC01-OFFICIAL-BUILD-FREEZE-A3-WINDOWS-R3.ps1`
- SHA-256: `8f6d67ce4af29a2812c2a181bb712edf57940e450dd8a70c30a9a1d6a8dfda07`
- bytes: `138535`
- lines: `2709`
- independent pre-execution Validation: `FINAL PASS / blockers 0`

Attempt 3:
- reservation: PRESENT
- launch: PRESENT
- canonical command: `npm run build`
- package build script: `node scripts/build.mjs`
- Official Build exit code: `0`
- retry performed: `false`
- lifetime invocation count: **3**
- Attempt 3: **CONSUMED**
- R3 / Official Build rerun: **PROHIBITED**

Known historical metadata-only defect:
- exact R3 source contains stale `$RunnerRevision = 'OBR-A3-CPU-SPEED-SLIDER-DIRECTION-FIX-R2'`.
- focused independent revalidation established exact R3 execution through Windows PowerShell / ScriptBlock provenance containing the R3-only leading-`./` rejection correction.

## 5. Independent Post-Build Validation

Current authoritative result:
- `POST-BUILD EVIDENCE / ARTIFACT VALIDATION = FINAL PASS`
- `BLOCKER COUNT = 0`

Closed blocker:
- `LC-01-A3-POST-IV-EXECUTING-RUNNER-IDENTITY-BINDING-01 = CLOSED`

Successful Attempt-3 transfer package:
- filename: `DUONIX-LC01-A3-RESULT-TRANSFER-DIAG-20260829-212230.zip`
- SHA-256: `f2d13b31e9547489329f641874df42542d75294d378f23acdc8c7bd5d3c164dd`
- bytes: `317,904`
- entries: `42`

## 6. Official Frozen Dist Authority

Promoted immutable binary:
- filename: `duonix-app-lc-01-cpu-speed-slider-direction-fix-a3-dist-freeze-candidate.zip`
- SHA-256: `829b43ca4dd58c23de4ddc64b3297c87d8c3be940b690d63850a95bf15dd89cc`
- bytes: `79,435`
- file count: `2`
- authority status: **OFFICIAL FROZEN DIST**
- `official_frozen_dist = true`

Promotion mode:
- `IMMUTABLE_IDENTITY_AUTHORITY_PROMOTION`
- rename: `0`
- copy/repackage/regeneration: `0`
- runtime payload modification: `0`
- rebuild: `0`
- R3 rerun: `0`
- Official Build invocation during promotion: `0`
- deploy: `0`

The historical filename still contains `freeze-candidate`; authority status is defined by the promotion receipt, not by renaming the immutable binary.

Payload authority:
- `assets/index-BZqr2gkq.js` — bytes `320,557`, SHA-256 `334d4027ba5c6680d6fd1972e665c5fc7ad717ce79e0b3ab43a293232f6ec73c`
- `index.html` — bytes `19,608`, SHA-256 `98e5820154ab65ae05eafb5b6f6ee15d4a2f82afb84cfabd9248922e0c93d930`
- raw-dist manifest SHA-256: `c594618614d15ccdbcc62c7429dcc5312a75bdbc70b91849fec1e0c278dbe87e`
- candidate payload vs raw-dist manifest: exact match
- semantic-network validation: PASS
- external runtime network dependency count: `0`

## 7. Promotion Receipt

Receipt:
- filename: `DUONIX-LC01-A3-OFFICIAL-FROZEN-DIST-PROMOTION-RECEIPT.json`
- SHA-256: `6da5388bba276685fec5bde10044507c90ded3d57efa34eaac5089d1f70c5704`
- bytes: `3,910`
- schema: `duonix-lc01-official-frozen-dist-promotion-receipt-v1`
- promotion result: `PASS`
- promotion mode: `IMMUTABLE_IDENTITY_AUTHORITY_PROMOTION`

Control Tower directly rehashed and parsed the received receipt and confirmed its SHA/bytes and key fields match the Build/Release report.

Receipt records:
- promoted binary SHA/bytes/file count equal the validated freeze candidate,
- `payload_byte_identical_to_validated_freeze_candidate = true`,
- `official_frozen_dist = true`,
- Galaxy Validation = `NOT_EXECUTED`,
- deploy = `0`,
- rebuild / R3 rerun / candidate regeneration / repackaging / rename = `0`.

## 8. Control Tower Disposition

Control Tower accepts the Build/Release promotion result and receipt.

Current authoritative release state:
- Official Frozen Dist promotion: **PASS / CLOSED**.
- Official Frozen Dist authority SHA-256: `829b43ca4dd58c23de4ddc64b3297c87d8c3be940b690d63850a95bf15dd89cc`.
- `official_frozen_dist = true`.
- Galaxy Validation: **NOT EXECUTED**.
- `LC01-MOB-06+`: **HOLD** pending separate Validation disposition.
- `LC-02`: inactive.
- R3 / Official Build rerun remains prohibited.
- no marker replacement, retrospective evidence rewrite, source modification, rebuild, repackage, or deploy is authorized.

Major work unit count is **7**; rotation remains **CONTINUE**.

## 9. Next Single Action

**Send the exact Official Frozen Dist authority SHA-256 `829b43ca4dd58c23de4ddc64b3297c87d8c3be940b690d63850a95bf15dd89cc` together with promotion receipt SHA-256 `6da5388bba276685fec5bde10044507c90ded3d57efa34eaac5089d1f70c5704` to `[DUONIX] 70 Validation / Integration` for the separately authorized Galaxy Validation gate only. Validation must test the promoted frozen binary without rebuild/repackage/source modification and return explicit PASS/FAIL/BLOCKED evidence. If the approved Galaxy Validation procedure or required device/environment is unavailable, return BLOCKED rather than substituting another platform. Do not advance LC01-MOB-06+, activate LC-02, or deploy in the same step.**
