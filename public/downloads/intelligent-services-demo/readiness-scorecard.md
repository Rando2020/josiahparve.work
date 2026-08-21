# Synthetic Readiness Scorecard

## Demonstration notice

Fictional scenario using synthetic data only. This scorecard is an operational example and is not legal, security, privacy, clinical, or compliance approval.

## Overall result

**Readiness score: 82 / 100**

**Recommendation: NO-GO until mandatory blockers are resolved**

The aggregate score is not sufficient to authorize launch. Three mandatory gates remain open.

## Category scores

| Category | Weight | Score | Status | Evidence summary |
|---|---:|---:|---|---|
| Business objective and scope | 10 | 10 | Ready | Objective, outputs, cadence, and synthetic data scope documented |
| Stakeholders and ownership | 15 | 11 | At risk | Launch authority named, rollback owner and residual-risk acceptor not confirmed |
| Data definition and quality | 15 | 14 | Ready with action | Fields and reconciliation targets defined, final dictionary approval pending |
| Architecture and environments | 15 | 13 | Ready with action | Stack and path documented, API authentication not selected |
| Security and privacy review | 15 | 8 | Blocked | Security approval and privacy disposition missing |
| Testing and evidence | 15 | 13 | Ready with action | UAT framework drafted, transfer receipt standard incomplete |
| Operational delivery and recovery | 10 | 8 | Blocked | Recipient allowlist and rollback ownership missing |
| Launch decision and communications | 5 | 5 | Ready | Go or No-Go forum and communication audience defined |
| **Total** | **100** | **82** | **Blocked** | Mandatory gates override the aggregate score |

## Mandatory launch blockers

### B-01: Production recipient and allowlist not confirmed

- Severity: Critical
- Accountable owner: Northstar Director of Pharmacy Programs
- Required evidence: Approved recipient list, service-account ownership, destination verification, and production allowlist confirmation
- Closure condition: Security and customer owners approve the exact production recipient and destination configuration

### B-02: Security approval not complete

- Severity: High
- Accountable owner: Information Security Manager
- Required evidence: Approved API authentication model, managed-file-transfer control review, and documented access model
- Closure condition: Security review disposition is Approved or Approved with a time-bound accepted exception

### B-03: Rollback owner not assigned

- Severity: High
- Accountable owner: Portfolio Delivery Director
- Required evidence: Named rollback decision owner, recovery runbook, and communication path
- Closure condition: Owner accepts responsibility and rollback rehearsal is completed

## High-priority actions

1. Confirm the exact recipient users, service accounts, and production destination.
2. Select and review the API authentication and authorization pattern.
3. Complete security and privacy review dispositions.
4. Assign rollback authority and residual-risk acceptance authority.
5. Define delivery receipt, reconciliation, and failed-transfer incident behavior.
6. Approve the final synthetic data dictionary and UAT exit criteria.

## Decision principle

A readiness score summarizes the implementation. It does not replace mandatory controls or accountable human approval.
