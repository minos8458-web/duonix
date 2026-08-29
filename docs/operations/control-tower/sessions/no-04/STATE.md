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

Official Build Attempt 3 has executed and is consumed. Control Tower has now directly received and consistency-checked the successful post-build evidence/artifact transfer package. The Attempt-3 cycle remains open until independent `[DUONIX] 70 Validation / Integration` post-build validation and subsequent Control Tower disposition.

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
- `Zone.Identifier` was removed by `Unblock-File`; default-stream SHA/bytes/lines remained unchanged.

Historical R1/R2 remain non-authoritative for execution.

Note for independent post-build review: the exact R3 script still sets internal `$RunnerRevision = OBR-A3-CPU-SPEED-SLIDER-DIRECTION-FIX-R2`; determine independently whether this is metadata-only or a validation concern. Do not infer failure solely from the label.

## 5. Historical Pre-Launch Block

The earlier Toolchain-D-placement blocker is preserved as historical evidence. It was a pre-launch placement mismatch, not an Official Build invocation. Its blocked workspace was moved whole to a distinct archive before the final invocation. Attempt 3 remained unconsumed at that time.

Blocker `LC-01-A3-TOOLCHAIN-D-MISSING-01`: **CLOSED**.

## 6. Official Build Attempt 3 — EXECUTED / CONSUMED

Final guarded invocation passed the approved R3/source/toolchain/marker/workspace preconditions.

Persistent authorities and direct output establish:
- Attempt-3 reservation marker: PRESENT
- Attempt-3 launch marker: PRESENT
- Official Build command: `npm run build`
- canonical package build script: `node scripts/build.mjs`
- process exit code: `0`
- retry performed: `false`
- Official Build lifetime invocation count: `3`
- runner self-result: `PASS`
- automatic retry: NOT AUTHORIZED
- R3 MUST NOT be run again.

Build stdout records Vite `6.4.3`, `137 modules transformed`, and success sentinel `build: vite` exactly once.
Build stderr is empty.

## 7. Successful Post-Build Transfer Receipt

Transfer package directly received and inspected by Control Tower:
- filename: `DUONIX-LC01-A3-RESULT-TRANSFER-DIAG-20260829-212230.zip`
- SHA-256: `f2d13b31e9547489329f641874df42542d75294d378f23acdc8c7bd5d3c164dd`
- bytes: `317,904`
- ZIP entries: `42`

Key exact evidence identities:
- status JSON SHA-256: `25b087a54bdd7aee3057ccf30c9ed7920bf29636141b8c1c5fd8289aebbe7076`
- status: `PASS`
- stage: `COMPLETE`
- official build exit code: `0`
- official build lifetime invocation count: `3`
- provenance SHA-256: `91739e56c86d44cc22fb19eb72c8ef006eb219d214a8f0065932a8b2e12e007f`
- raw-dist manifest artifact SHA-256: `9628d23ded84675d7aa5991baec2663c870dba9f0c7f60876c490f763a6092c7`
- semantic-network-audit artifact SHA-256: `147c077909867187558857a380a35574597d7121072ded5c9bbd2e4edb82686b`
- Attempt-3 result SHA-256: `f2205f72e783dfd646987d37144d2ef920bf002d626a3c505bcc2ca7af501515`
- reservation marker SHA-256: `ddfc1196bc7d517980321d3140d19d26a7c675a45090362f36e9ecff0e6c1d58`
- launch marker SHA-256: `bf963249960bc42c5b643de36af6c588084ab1079519a21953a8ffc3dc884643`

Control Tower consistency check found the status/result/provenance/markers mutually consistent with Attempt 3 launch, exit `0`, lifetime count `3`, no retry, and Toolchain-D-only binding.

## 8. Raw Dist / Freeze Candidate Receipt

Runner-produced raw dist manifest:
- file count: `2`
- manifest SHA-256: `c594618614d15ccdbcc62c7429dcc5312a75bdbc70b91849fec1e0c278dbe87e`
- `assets/index-BZqr2gkq.js`: bytes `320,557`, SHA-256 `334d4027ba5c6680d6fd1972e665c5fc7ad717ce79e0b3ab43a293232f6ec73c`
- `index.html`: bytes `19,608`, SHA-256 `98e5820154ab65ae05eafb5b6f6ee15d4a2f82afb84cfabd9248922e0c93d930`

Freeze candidate:
- filename: `duonix-app-lc-01-cpu-speed-slider-direction-fix-a3-dist-freeze-candidate.zip`
- SHA-256: `829b43ca4dd58c23de4ddc64b3297c87d8c3be940b690d63850a95bf15dd89cc`
- bytes: `79,435`
- file count: `2`
- `official_frozen_dist`: `false`

Control Tower directly extracted the candidate from the transfer ZIP and independently recomputed both contained file SHA-256 values; they exactly match the raw-dist manifest. Both ZIP entries carry normalized `1980-01-01 00:00:00` timestamps.

This is a **freeze candidate only**. It has not been promoted to Official Frozen Dist.

## 9. Semantic / Immutability Self-Evidence Receipt

Runner-produced semantic network audit reports `PASS` with:
- external absolute URL count: `0`
- protocol-relative external resource count: `0`
- explicit runtime network API count: `0`
- runtime fetch occurrences: `1`
- classified Vite modulepreload polyfill fetch count: `1`
- unclassified runtime fetch count: `0`
- external runtime network dependency count: `0`
- missing local runtime asset count: `0`
- build-workspace path leak count: `0`
- findings: empty.

Post-build comparison evidence reports source and Toolchain D file/directory equality PASS. Build-shadow transient cleanup reports only `.vite-temp`, safely removed. Prohibited-action counters in provenance are all zero, including dependency install/CI, lock regeneration, direct Vite production build, automatic retry, LAN server, Galaxy Validation, and deploy.

These are runner-generated/self-evidence and must be independently recomputed or checked by 70 Validation before final acceptance.

## 10. Current Validation / Release State

Control Tower direct receipt / cross-consistency check: **PASS — no contradiction found**.

Independent `[DUONIX] 70 Validation / Integration` post-build evidence/artifact validation: **NOT YET EXECUTED**.

Galaxy Validation: **NOT EXECUTED**.
Official Frozen Dist: **NOT PROMOTED / NOT DECLARED**.
`LC01-MOB-06+`: **HOLD**.
`LC-02`: **NOT ACTIVE**.

Major work unit count remains **4** until independent post-build validation and Control Tower disposition close this Attempt-3 cycle.

## 11. Control Tower Disposition

- R3 MUST NOT be run again.
- Attempt 3 is consumed; lifetime count is `3`.
- No retry or marker replacement is authorized.
- Do not modify or delete the successful live Attempt-3 BuildRoot or historical blocked archive.
- Do not promote the freeze candidate yet.
- Do not claim `official_frozen_dist=true`.
- Galaxy Validation remains unauthorized pending independent post-build validation.
- No application-source modification is authorized.

## 12. Next Single Action

**Send `DUONIX-LC01-A3-RESULT-TRANSFER-DIAG-20260829-212230.zip` unchanged to `[DUONIX] 70 Validation / Integration` for independent post-build evidence/artifact validation. Validation must independently inspect/recompute the package, candidate, raw-dist identities, semantic-network assertions, source/toolchain immutability evidence, marker/build chronology, prohibited-action evidence, and the internal R3 revision-label discrepancy. Return a single FINAL PASS/FAIL disposition with blocker count and evidence. Do not run R3, do not run Galaxy Validation, and do not promote Official Frozen Dist.**
