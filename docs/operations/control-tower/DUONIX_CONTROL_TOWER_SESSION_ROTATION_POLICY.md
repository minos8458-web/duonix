# DUONIX Control Tower Session Rotation Policy

Status: ACTIVE POLICY  
Owner: `[DUONIX] 00 Control Tower`  
Scope: All DUONIX Control Tower chat sessions  
Applies to source-repository operations documentation only; this file does not change game runtime behavior.

## 1. Purpose

Prevent Control Tower sessions from reaching conversation/context limits before a reliable handoff can be created, while avoiding excessively frequent session rotation.

Rotation decisions must not rely on guessed remaining context percentage or token limits.

## 2. Major Control Tower Work Unit

Count one major work unit only when Control Tower completes disposition of a coherent project-state or cross-role loop.

Examples:

1. Baseline/provenance recovery and Control Tower disposition.
2. Milestone scope freeze or activation.
3. Product + Architecture approval package completed for one milestone.
4. Development result → independent Validation → Control Tower final disposition.
5. One remediation cycle completed and independently revalidated.
6. One Official Build attempt cycle and Control Tower disposition.
7. One freeze/release-candidate validation and disposition.
8. One major blocker root-cause/recovery loop completed.
9. One milestone final closure.
10. One major program/baseline transition.

Do not count each message, file transfer, SHA check, individual blocker, HOLD update, or minor approval as a separate major work unit.

## 3. Historical-Normalized Rotation Range

Exact historical per-session arithmetic average is not currently recoverable from available No.1–No.3 records.

Therefore use the following operational calibration instead of claiming a false precise historical average:

- Normal rotation-review range: **8–12 major work units**
- Reference midpoint: **10 major work units**

This is an operational reference range, not a verified historical mean.

## 4. Rotation Decision Bands

### 0–5 major work units — CONTINUE

Do not recommend rotation solely because of work count.

### 6–7 major work units — CONTINUE + CHECKPOINT

Continue normally.

Ensure the current external Control Tower state document is up to date.

### 8–9 major work units — ROTATION REVIEW ZONE

Do not rotate automatically.

At the end of the current coherent work loop, review:

- size/risk of the next major action,
- number of cross-role HANDOFF/result cycles accumulated,
- baseline/branch/commit changes,
- whether the current state can be reconstructed from the latest checkpoint alone.

### 10–12 major work units — RECOMMENDED ROTATION ZONE

Complete the current coherent work loop.

Before starting the next major work loop:

1. update the current session state,
2. write a SESSION HANDOFF,
3. recommend moving to the next numbered Control Tower session.

### More than 12 major work units — STRONG ROTATION DEFAULT

Do not begin another major work loop unless there is a specific documented reason to remain in the current session.

Write or refresh the SESSION HANDOFF first.

## 5. Hard Rotation Triggers

Hard triggers may override the numerical range.

Recommend rotation early when one or more of the following occurs:

1. The current milestone is closed and the next milestone is materially different.
2. A major source/build baseline is frozen and the next work starts from that new baseline.
3. Multiple substantial cross-role HANDOFF/result cycles have accumulated and state reconstruction is becoming expensive.
4. Earlier project facts are becoming difficult to retrieve reliably.
5. Conflicting or duplicated state descriptions have accumulated.
6. The next major task depends on extensive rereading of old conversation rather than the latest external state documents.
7. The Control Tower cannot distinguish approved, proposed, implemented, and independently validated state without reconstructing old conversation.

A single approval, HOLD, Validation result, blocker opening/closure, or artifact receipt is not by itself a hard rotation trigger.

## 6. Rotation Procedure

When rotation is recommended:

1. Stop before starting the next major work loop.
2. Inform the user:
   `현재 세션은 인계 지점을 확보하는 것이 안전합니다. 다음 주요 작업을 시작하기 전에 새 세션으로 교체하는 것을 권고합니다.`
3. Update the current session state document.
4. Write a SESSION HANDOFF.
5. The HANDOFF must clearly separate:
   - user-approved decisions,
   - AI proposals,
   - implemented changes,
   - unverified reports,
   - independently validated results.
6. Unknown values must be written as `미확인`.
7. Do not start the next major work loop unless the user explicitly chooses to continue in the current session.

## 7. Required SESSION HANDOFF Contents

At minimum include:

- session role,
- baseline,
- active milestone,
- approved scope,
- completed work,
- incomplete work,
- confirmed decisions,
- unconfirmed/estimated items,
- base branch and commit,
- working branch and final commit,
- changed files,
- implementation scope,
- excluded scope,
- executed tests,
- pass/fail/not-run status,
- independent Validation evidence,
- Build status,
- known issues/risks,
- pending approvals,
- related documents/artifacts,
- exactly one next action for the next session.

## 8. Multiple-Attachment Packaging Rule

Applies to all DUONIX Control Tower responses.

If a response provides two or more downloadable files:

1. Individual links may be shown when useful.
2. Create one ZIP containing every file delivered in that response.
3. Verify the ZIP contents.
4. The ZIP link must be the final downloadable attachment/link in the response.
5. No other downloadable attachment may appear after the ZIP link.

If only one file is delivered, ZIP packaging is optional unless explicitly requested.

The ZIP is only a transfer container. Inner authoritative file identities such as filename, SHA-256, bytes, and line counts remain authoritative.
