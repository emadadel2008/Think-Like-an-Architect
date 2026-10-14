# Operations Runbook

> Write actionable, verifiable steps for the intended on-call audience. Replace prompts before publishing. Use approved tooling and never include passwords, tokens, private keys, or other secrets.

## Document Control

| Field | Value |
|---|---|
| Service / system | [Name] |
| Procedure | [Incident / maintenance / recovery task] |
| Owner / reviewer | [Team / names] |
| Version / last reviewed | [Version] / [Date] |
| Related service / dashboard | [Links] |

## 1. Purpose and Scope

- **Purpose:** [What this procedure enables]
- **Applies to:** [Environments / components]
- **Does not cover:** [Limitations]
- **Audience / required access:** [Role and approved access path]

## 2. Trigger and Impact

- **When to use:** [Alert, symptom, request, or scheduled event]
- **Severity / priority:** [Classification]
- **Customer / business impact:** [Known impact and affected users]
- **Expected symptoms:** [Observable indicators]

## 3. Roles and Communications

| Role | Responsibility | Contact / escalation path |
|---|---|---|
| Incident lead | [Coordination] | [On-call channel / rotation] |
| Service owner | [Technical decision] | [Contact path] |
| Communications owner | [Stakeholder updates] | [Contact path] |

## 4. Prerequisites and Safety

- [Required permissions, tools, dashboards, or change ticket]
- [Backup / snapshot / approval needed before changes]
- [Customer-data, privacy, or production-safety considerations]
- **Stop and escalate if:** [Conditions where the procedure is unsafe or insufficient]

## 5. Diagnosis

| Check | Where / how | Expected result | If unexpected |
|---|---|---|---|
| [Signal or health check] | [Approved console / command reference] | [Healthy condition] | [Next step / escalation] |

## 6. Procedure

### Step 1 — [Action]

- **Action:** [Exact safe operation; identify environment and target explicitly]
- **Expected result:** [Observable confirmation]
- **If it fails:** [Recovery or escalation]

### Step 2 — [Action]

- **Action:** [Exact operation]
- **Expected result:** [Observable confirmation]
- **If it fails:** [Recovery or escalation]

## 7. Recovery, Rollback, and Verification

- **Recovery / rollback:** [Reversible steps and decision owner]
- **Verification:** [Health signals, user-facing checks, and duration]
- **Success criteria:** [Measurable conditions]
- **Cleanup:** [Temporary resources, feature flags, or follow-up actions]

## 8. Escalation and Status Updates

- **Escalate when:** [Time limit, repeated failure, safety threshold]
- **Escalation path:** [Team / on-call / incident channel]
- **Information to provide:** [Incident ID, timestamps, scope, actions, outcomes, relevant links]
- **Update cadence / audience:** [Who is informed and how often]

## 9. Post-Incident Follow-Up

- [Record timeline, root cause, and evidence in the approved system]
- [Create follow-up actions with owners and due dates]
- [Review whether alerts or this runbook need updating]

## 10. Related Procedures and Change History

- [Dashboard, alert, architecture diagram, rollback / DR procedure]

| Version | Date | Author | Summary of change |
|---|---|---|---|
| 0.1 | [Date] | [Name] | Initial draft |
