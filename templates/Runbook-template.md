# Operations Runbook

> **Purpose:** Give the intended responder a safe, repeatable path to diagnose and handle one operational scenario. Use this for actionable procedures; keep broad incident coordination and service context in linked operational documentation.
>
> **How to use:** Make every step specific to the service and approved tools. Clearly identify environment and target; state expected results, stop conditions, and rollback. Have an operator other than the author test the procedure. Never include credentials, secret values, or unapproved commands.

## Document Control

| Field | Value |
|---|---|
| Service / component | [Name and service-catalog link] |
| Procedure title / ID | [Specific symptom or operation / ID] |
| Triggering alert / request | [Exact alert, symptom, schedule, or request link] |
| Service owner / on-call team | [Team / escalation link] |
| Author / technical reviewer | [Names / roles] |
| Version / status | [Version] / [Draft, Verified, Approved, Retired] |
| Created / last tested / next review | [YYYY-MM-DD] / [YYYY-MM-DD] / [YYYY-MM-DD] |
| Classification | [Organizational label] |

## 1. Purpose, Scope, and Impact

- **Scenario addressed:** [What failed or what operation is performed.]
- **Applies to:** [Service version, environments, regions, components.]
- **Symptoms / detection:** [Alert names, customer symptoms, dashboard links.]
- **Potential impact:** [Users, business processes, data, security, and scope.]
- **Out of scope:** [Related incidents or actions this procedure does not cover.]

## 2. Severity and Response Objectives

| Severity | Criteria / impact | Response objective | Escalation |
|---|---|---|---|
| [SEV level] | [Use the organization's incident policy; do not invent severity] | [Acknowledgement / mitigation objective] | [Team / role] |

## 3. Roles and Communications

Follow the organization's incident-management policy. For a declared incident, establish clear incident command and assign operational and communications responsibilities; one person may hold multiple roles for a small incident.

| Role | Assigned responder / channel | Responsibility |
|---|---|---|
| Incident commander | [Name / on-call path] | [Coordinates response, priorities, decisions, escalation] |
| Operations lead | [Name / on-call path] | [Leads investigation and mitigation; records actions] |
| Communications lead | [Name / on-call path] | [Provides stakeholder updates and manages inquiries] |

- **Incident channel / bridge:** [Approved link / process]
- **Stakeholders and update cadence:** [Audience, owner, and cadence per incident policy]
- **Status record:** [Incident ticket / timeline location]

## 4. Safety, Authorization, and Stop Conditions

### Before Acting

- [Confirm incident / change record and authority for the target environment.]
- [Verify operator access through the approved identity and privileged-access process.]
- [Confirm backups, snapshots, or recovery points before destructive or data-changing steps.]
- [Check for active deployments, related incidents, or concurrent operators.]
- [Preserve evidence and follow security / privacy incident procedures when applicable.]

### Stop and Escalate If

- [The target, environment, data scope, or command result is uncertain.]
- [The proposed action could cause data loss, broaden impact, or breach a security boundary.]
- [Required approval, backup, rollback, or access is unavailable.]
- [The first controlled action fails, the situation worsens, or the procedure does not match observed state.]

## 5. Triage and Decision Path

| Check | Approved source / action | Expected healthy result | Decision |
|---|---|---|---|
| Confirm symptom and scope | [Alert / dashboard / customer reports] | [Expected signal] | [If absent, stop or investigate alternate cause] |
| Check service dependencies | [Dependency health / recent changes] | [Expected signal] | [If degraded, follow linked dependency procedure] |
| Check recent changes | [Deployment / configuration / change log] | [Expected state] | [If correlated, consider approved rollback path] |

**Decision:** [Describe explicit condition to proceed with this runbook; otherwise link to the right runbook or escalation.]

## 6. Mitigation / Procedure

Record start time, actor, target, command or action, result, and decision in the incident timeline. Use placeholders only for values the responder can verify; do not use ambiguous targets such as "production" if the organization has multiple environments or regions.

### Step 1 — [Read-only check or safest first action]

- **Target / prerequisites:** [Exact environment, resource, permissions, approval.]
- **Action:** [Approved console path or command; link to source of truth.]
- **Expected result:** [Observable output or signal.]
- **If different:** [Safe next check; stop / escalate condition.]

### Step 2 — [Controlled mitigation]

- **Target / prerequisites:** [Exact resource and preconditions.]
- **Action:** [Specific, reviewed, minimal action.]
- **Expected result:** [Observable result and time window.]
- **Risk / rollback:** [Impact, approval, and exact reversal procedure.]
- **If different:** [Stop, preserve state, escalate.]

### Step 3 — [Further action, only if necessary]

- **Proceed only if:** [Evidence / decision owner.]
- **Action and expected result:** [Specific action and confirmation.]
- **If different:** [Recovery / escalation.]

## 7. Recovery, Rollback, and Verification

- **Rollback trigger:** [When to reverse the mitigation or stop rollout.]
- **Rollback / recovery procedure:** [Exact steps and linked tested procedure.]
- **Data integrity checks:** [Reconciliation, loss / duplication checks, owner.]
- **Service validation:** [Health checks and representative user journey.]
- **Success criteria:** [Measurable service and customer outcome.]
- **Observation window:** [Duration and signal thresholds before closure.]
- **Cleanup:** [Temporary access / flags / resources to remove and owner.]

## 8. Escalation

| Escalate to | Trigger / time limit | Contact path | Information to provide |
|---|---|---|---|
| [Service owner / incident commander / specialist / security / vendor] | [Condition] | [On-call / approved channel] | [Incident ID, impact, timeline, checks, actions, results, evidence links] |

**Escalate immediately for:** [Safety, suspected security / privacy incident, data integrity risk, expanding impact, or unknown destructive effects.]

## 9. Evidence and Post-Incident Follow-Up

- **Evidence to retain:** [Relevant timestamps, logs, metrics, command outputs, deployment IDs; follow retention and privacy policy.]
- **Customer / stakeholder update:** [Final status owner and required channel.]
- **Incident record:** [Timeline, mitigation, restoration time, affected scope.]
- **Follow-up:** [Post-incident review, root-cause analysis, corrective actions, owners, due dates.]
- **Runbook improvement:** [Update trigger, owner, review / test date.]

## 10. Related Resources

- [Service dashboard and alerts]
- [Architecture diagram / HLD / LLD]
- [Related dependency, deployment, security, backup, and disaster-recovery runbooks]
- [Incident policy, change policy, on-call schedule, escalation directory]

## 11. Verification and Change History

| Test date | Tester (not author, where practical) | Environment / scenario | Result / follow-up |
|---|---|---|---|
| [YYYY-MM-DD] | [Name / role] | [Environment / exercise] | [Passed / actions] |

| Version | Date | Author | Change | Review / approval reference |
|---|---|---|---|---|
| 0.1 | [YYYY-MM-DD] | [Name] | Initial draft | [Link / pending] |

### Guidance

- [Google SRE Workbook: Incident Response](https://sre.google/workbook/incident-response/)
- [Google SRE Book: Effective Troubleshooting](https://sre.google/sre-book/effective-troubleshooting/)
