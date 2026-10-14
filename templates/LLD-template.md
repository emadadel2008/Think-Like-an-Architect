# Low-Level Design (LLD)

> **Purpose:** Provide an implementable, reviewable specification for a bounded component, service, interface, or change. Detail behavior, contracts, data, configuration, security, failure handling, deployment, and verification. Keep the cross-system architecture in the HLD.
>
> **How to use:** Scope this document to a component or coherent change; link the approved HLD, requirements, and ADRs. Use stable IDs and versioned contracts. Include only implementation details needed to build, test, secure, and operate the design. Never record credentials or secret values.

## Document Control

| Field | Value |
|---|---|
| System / component / change | [Name and tracking link] |
| Component owner / engineering lead | [Team / name] |
| Author / reviewers | [Names / roles] |
| Version / status | [Version] / [Draft, In Review, Approved, Superseded] |
| Created / last updated | [YYYY-MM-DD] / [YYYY-MM-DD] |
| Classification | [Organizational label] |
| Parent HLD / BRD / ADRs | [Links and IDs] |

### Review and Approval

| Reviewer | Perspective | Decision / conditions | Date |
|---|---|---|---|
| [Name] | [Engineering / architecture / security / data / operations / test] | [Pending / Approved / Rejected] | [YYYY-MM-DD] |

## 1. Purpose, Scope, and Design Summary

- **Component responsibility:** [Single bounded responsibility.]
- **In scope / out of scope:** [Explicitly state both.]
- **Requirements addressed:** [BR- / QA- / security-control IDs.]
- **Dependencies and owners:** [Services, libraries, platforms, teams.]
- **Design summary:** [Implementation approach and important decisions.]

## 2. Component Structure and Behavior

### 2.1 Component Diagram

[Insert a focused component diagram showing dependencies, boundaries, and interfaces.]

### 2.2 Responsibilities and Dependencies

| ID | Module / dependency | Responsibility | Interface / version | Owner / criticality |
|---|---|---|---|---|
| CMP-001 | [Name] | [Responsibility] | [Interface / version] | [Owner / criticality] |

### 2.3 Main Flows and State Transitions

[Describe preconditions, normal path, alternate paths, invariants, and state transitions. Add a sequence diagram for complex or security-sensitive flows.]

| Step | Actor / component | Input / action | Result / persisted state | Failure / compensation |
|---|---|---|---|---|
| 1 | [Actor] | [Action and validation] | [Result] | [Failure behavior] |

## 3. Interface and Contract Specifications

For each API, event, message, file exchange, or scheduled interface, define the contract and the ownership boundary.

| Interface ID | Operation | Protocol / method | Endpoint / topic | Contract version / owner |
|---|---|---|---|---|
| API-001 | [Operation] | [HTTPS / REST / event / etc.] | [Path / topic] | [Version / owner] |

### Request / Event Schema

```json
{
  "requestId": "[string, required; correlation identifier]",
  "exampleField": "[type, required/optional; constraints and meaning]"
}
```

### Response / Event Schema

```json
{
  "requestId": "[string; correlation identifier]",
  "result": "[type and meaning]"
}
```

- **Validation and limits:** [Required fields, formats, size limits, allow-lists, boundary checks.]
- **Authentication and authorization:** [Principal, scopes / roles, resource-level decisions.]
- **Error contract:** [Stable error codes, safe messages, retryable vs. terminal classification.]
- **Compatibility and versioning:** [Additive / breaking change policy and consumer migration.]
- **Timeout, retry, and idempotency:** [Budgets, backoff, deduplication key, replay behavior.]
- **Rate limiting / quotas:** [Limits, enforcement point, client behavior.]
- **Example:** [Sanitized request / response / message or contract link.]

## 4. Data Model and Persistence

### 4.1 Entities and Schema

| Entity / field | Type / format | Required | Key / constraint | Classification / notes |
|---|---|---|---|---|
| [Name] | [Type] | [Yes / No] | [PK / FK / unique / validation] | [Sensitivity / purpose] |

### 4.2 Data Behavior

- **Relationships and ownership:** [Source of truth, cardinality, write authority.]
- **Transactions and consistency:** [Atomicity boundaries, isolation, consistency model.]
- **Queries and indexes:** [Primary query patterns, indexes, expected cardinality.]
- **Retention and deletion:** [TTL, archival, legal hold, deletion propagation.]
- **Schema evolution / migration:** [Forward / backward compatibility, migration order, rollback.]
- **Data protection:** [Encryption, keys, masking, backup, residency.]

## 5. Security and Privacy Controls

| Control | Implementation detail | Verification / evidence |
|---|---|---|
| Identity and least privilege | [Principals, roles, permissions, workload identity] | [Test / review] |
| Input / output safety | [Validation, encoding, file / payload restrictions] | [Test] |
| Secrets and keys | [Secret-store reference, access boundary, rotation] | [Review / alert] |
| Sensitive data | [Classification, minimization, redaction, retention] | [Test / review] |
| Audit | [Events, actor, outcome, correlation, retention, access] | [Test / evidence] |

- **Threat model / abuse cases:** [Link and applicable threats / mitigations.]
- **Security dependencies / vulnerabilities:** [Approved versions, scanning, patch expectations.]
- **Security exceptions:** [Approver, rationale, expiry, tracking link; N/A if none.]

## 6. Runtime, Infrastructure, and Configuration

| Resource / setting | Purpose | Safe value / secret reference | Environment / scaling behavior |
|---|---|---|---|
| [Name] | [Purpose] | [Non-secret value or secret-store reference; never the secret] | [Difference / limit] |

- **Runtime / platform:** [Language / runtime versions, OS or managed service assumptions.]
- **Network / DNS / ports:** [Ingress, egress, protocol, allowed destinations, trust boundary.]
- **Capacity and limits:** [Sizing assumptions, concurrency, connection pools, payload / storage limits.]
- **Configuration validation:** [Required settings, startup checks, safe failure behavior.]
- **Infrastructure as code:** [Module / repository / environment configuration link.]

## 7. Resilience and Failure Handling

| Failure / degraded dependency | Detection | Component behavior | Retry / timeout / fallback | Alert / recovery owner |
|---|---|---|---|---|
| [Failure mode] | [Signal] | [Fail safe / degrade] | [Bounded policy] | [Owner / action] |

- **Idempotency / duplicate delivery:** [Behavior and retention of deduplication state.]
- **Concurrency / ordering:** [Required guarantees and enforcement.]
- **Circuit breaking / back-pressure:** [Thresholds, queue limits, load shedding.]
- **Recovery / data reconciliation:** [Procedure and runbook link.]

## 8. Observability and Operations

- **Logs:** [Structured fields, correlation IDs, sensitive-data exclusions, retention.]
- **Metrics:** [Service and business metrics, units, dimensions, thresholds.]
- **Traces:** [Propagation and sampling.]
- **Health checks:** [Liveness / readiness semantics and dependency treatment.]
- **Dashboards and alerts:** [Links, SLO mapping, routing, actionable response.]
- **Runbooks / ownership:** [Procedure links, escalation path, support tier.]

## 9. Build, Deployment, and Rollback

- **Build artifacts and provenance:** [Pipeline, artifact source, signing / scanning.]
- **Deployment sequence:** [Prerequisites, dependencies, data / schema order.]
- **Progressive rollout:** [Canary / feature flag / staged release and guard conditions.]
- **Configuration and secret rollout:** [Safe update and rotation sequence.]
- **Rollback / roll-forward:** [Decision criteria, steps, compatibility limits.]
- **Post-deployment checks:** [Signals, smoke tests, observation window.]

## 10. Test and Verification Plan

| Test level / quality | Scenario and acceptance threshold | Automation / owner | Evidence |
|---|---|---|---|
| Unit / contract | [Behavior and measurable result] | [Pipeline / owner] | [Link] |
| Integration / end-to-end | [Dependencies and scenario] | [Pipeline / owner] | [Link] |
| Security / privacy | [Abuse case / control] | [Tool / reviewer] | [Link] |
| Performance / resilience | [Load / failure and target] | [Test / owner] | [Link] |
| Operational acceptance | [Alert, recovery, rollback verification] | [Exercise / owner] | [Link] |

## 11. Requirement Traceability and Open Items

| Requirement / ADR / HLD reference | Design section | Verification / evidence | Status |
|---|---|---|---|
| [ID / link] | [Section] | [Test / review] | [Planned / Verified] |

| Open decision / risk | Owner | Needed by | Status / implementation impact |
|---|---|---|---|
| [Item] | [Role] | [Date] | [Status / impact] |

## 12. References and Change History

- [API schemas, data model, sequence diagrams, threat model, IaC, pipeline, runbooks.]

| Version | Date | Author | Change | Review / approval reference |
|---|---|---|---|---|
| 0.1 | [YYYY-MM-DD] | [Name] | Initial draft | [Link / pending] |

### Guidance

- [arc42: Architecture documentation overview](https://arc42.org/overview)
- [C4 model: Diagram types and levels of detail](https://c4model.com/diagrams)
