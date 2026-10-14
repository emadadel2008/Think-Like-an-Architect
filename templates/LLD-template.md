# Low-Level Design (LLD)

> Specify enough detail for implementation, review, testing, and operations. Keep secrets and production credentials out of this document; reference the approved secret store instead.

## Document Control

| Field | Value |
|---|---|
| Project / component | [Name] |
| Document owner | [Name / role] |
| Version / status | [Version] / [Draft, In Review, Approved] |
| Created / last updated | [Date] / [Date] |
| Related HLD / requirements | [Links / IDs] |

## 1. Purpose and Scope

- **Purpose:** [Component or implementation being specified]
- **In scope:** [Detailed capabilities]
- **Out of scope:** [Explicit exclusions]
- **Dependencies:** [Other components, teams, or services]

## 2. Component Design

[Insert a component diagram. Describe each component, its interface, and responsibility.]

| Component | Responsibility | Interface | Runtime / owner |
|---|---|---|---|
| [Component] | [Purpose] | [API, event, or protocol] | [Runtime / team] |

## 3. Detailed Flows

### [Use case / operation]

1. [Trigger and validation]
2. [Processing and dependencies]
3. [Success response or resulting state]
4. [Failure paths, retry behavior, and recovery]

[Add sequence diagrams for complex interactions.]

## 4. Interfaces and API Contracts

| Operation | Method / protocol | Path / topic | Authentication | Description |
|---|---|---|---|---|
| [Name] | [Method] | [Path] | [Mechanism] | [Purpose] |

### Request / Message

```json
{
  "field": "[type and meaning]"
}
```

### Response / Event

```json
{
  "field": "[type and meaning]"
}
```

- **Validation rules:** [Required fields, bounds, formats]
- **Error behavior:** [Status / error codes and safe client messages]
- **Versioning / compatibility:** [Contract evolution policy]
- **Timeouts, retries, and idempotency:** [Rules]

## 5. Data Design

### Entities / Schema

| Entity / field | Type | Required | Constraints | Classification / notes |
|---|---|---|---|---|
| [Name] | [Type] | [Yes / No] | [Rules] | [Notes] |

- **Relationships and keys:** [Describe]
- **Indexes / query patterns:** [Describe]
- **Retention, archival, and deletion:** [Describe]
- **Migration / compatibility:** [Describe]

## 6. Infrastructure and Configuration

| Resource / setting | Purpose | Non-secret configuration | Environment differences |
|---|---|---|---|
| [Resource / key] | [Purpose] | [Value or reference] | [Differences] |

- **Network / DNS / ports:** [Required paths and boundaries]
- **Capacity / scaling:** [Limits, triggers, and sizing assumptions]
- **Secrets:** [Secret-store references and rotation expectations only]

## 7. Security Controls

- **Identity and authorization:** [Principals, roles, least-privilege rules]
- **Input and output handling:** [Validation, encoding, file / payload constraints]
- **Encryption and key handling:** [In transit / at rest, key ownership]
- **Audit events:** [Events, fields, retention, and access]
- **Threats and mitigations:** [Link to threat model / review]

## 8. Failure Handling and Resilience

| Failure mode | Detection | Handling / retry | Recovery / alert |
|---|---|---|---|
| [Failure] | [Signal] | [Behavior] | [Action / owner] |

## 9. Deployment and Operations

- **Build / deployment dependencies:** [Pipeline, artifacts, prerequisites]
- **Release, rollback, and migration steps:** [Procedure or linked runbook]
- **Health checks:** [Readiness / liveness and expected behavior]
- **Logs, metrics, and traces:** [Signals, dashboards, alert links]
- **Operational owner and support tier:** [Team / contact path]

## 10. Testing and Acceptance

| Test level | Scenarios / criteria | Evidence location |
|---|---|---|
| Unit | [Cases] | [Link] |
| Integration | [Cases] | [Link] |
| Security / performance | [Cases and thresholds] | [Link] |

## 11. Open Items, References, and Change History

| Open item | Owner | Due date / status |
|---|---|---|
| [Decision or action] | [Name] | [Date / status] |

- [HLD, ADRs, API specification, data model, runbooks]

| Version | Date | Author | Summary of change |
|---|---|---|---|
| 0.1 | [Date] | [Name] | Initial draft |
