# DUONIX Control Tower Operations Documentation Layout

Status: REPOSITORY LAYOUT GUIDANCE  
Owner: `[DUONIX] 00 Control Tower`

## Recommended Repository Location

Do not place Control Tower policy/state documents inside runtime source directories such as `src/`.

Recommended layout:

```text
docs/
└─ operations/
   └─ control-tower/
      ├─ DUONIX_CONTROL_TOWER_SESSION_ROTATION_POLICY.md
      ├─ README.md                         # optional index
      └─ sessions/
         ├─ no-04/
         │  ├─ STATE.md
         │  └─ HANDOFF.md                  # only when rotation is prepared/finalized
         ├─ no-05/
         │  ├─ STATE.md
         │  └─ HANDOFF.md
         └─ ...
```

## Document Ownership

### Permanent policy

Path:

`docs/operations/control-tower/DUONIX_CONTROL_TOWER_SESSION_ROTATION_POLICY.md`

Purpose:

- permanent rotation rules,
- work-unit definition,
- rotation thresholds,
- hard triggers,
- required HANDOFF contents,
- multiple-attachment ZIP rule.

This document must not contain current session counters, current blockers, current SHA values, or current milestone status.

### Session state

Path pattern:

`docs/operations/control-tower/sessions/no-XX/STATE.md`

Purpose:

- current Control Tower session number,
- current major-work-unit count,
- active milestone,
- current source/build authority,
- current blockers/HOLDs,
- latest validation/build result,
- next single action.

Update this file whenever a meaningful project-state transition occurs.

### Session handoff

Path pattern:

`docs/operations/control-tower/sessions/no-XX/HANDOFF.md`

Create/update when preparing to rotate out of the current Control Tower session.

The HANDOFF belongs to the outgoing session. Example:

`docs/operations/control-tower/sessions/no-04/HANDOFF.md`

means No.4 → next Control Tower session handoff.

## Recommended Chat-Session Ownership

No separate DUONIX role needs to be created for these documents.

Recommended ownership:

- **Policy owner:** `[DUONIX] 00 Control Tower`
- **Session STATE/HANDOFF owner:** the currently active numbered `[DUONIX] 00 Control Tower` chat session
- **Architecture / Development / Validation / Build sessions:** read or return evidence, but should not own or rewrite Control Tower policy.

For the current project state, use:

- Chat session: `No.4 [DUONIX] 00 Control Tower`
- Repository state path: `docs/operations/control-tower/sessions/no-04/STATE.md`

Do not create No.5 merely to store operational documents. No.5 should be created only when the rotation policy says the current Control Tower session has reached a justified handoff boundary.
