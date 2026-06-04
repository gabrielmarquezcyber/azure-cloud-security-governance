# Risk Register

## Purpose

This document summarizes cloud governance and compliance risks identified in the simulated Azure migration scenario.

The register is designed to show audit-defensible risk reasoning, not production risk ownership.

This is a public-safe portfolio artifact for a simulated regulated cloud environment.

## Risk Summary

| ID | Risk | Impact | Likelihood | Severity | Mitigation | Residual Risk |
|---|---|---:|---:|---:|---|---|
| R-001 | Overly broad Azure access | High | Medium | High | Department-scoped resource groups and Azure RBAC assignments | Medium |
| R-002 | Cross-department resource visibility | Medium | Medium | Medium | Separate resource groups and ownership tagging | Low-Medium |
| R-003 | Permanent deletion of keys or secrets | High | Low-Medium | High | Key Vault soft delete and purge protection | Low-Medium |
| R-004 | Unverified backup recoverability | High | Medium | High | Recovery Services vault and documented backup policy | Medium |
| R-005 | Unowned or poorly classified resources | Medium | High | Medium | Azure Policy Department tag enforcement | Low-Medium |
| R-006 | Weak audit evidence | Medium | Medium | Medium | Evidence summary, control mapping, and documented screenshots | Low |
| R-007 | Compliance control gaps during migration | High | Medium | High | NIST/FISMA/PCI-oriented control mapping and recommendations | Medium |

## R-001: Overly Broad Azure Access

### Description

Users or groups may have access beyond their required department scope.

### Impact

Excessive access increases the risk of unauthorized modification, accidental changes, data exposure, and difficult incident scoping.

### Mitigation

- Use department-scoped resource groups.
- Assign Azure RBAC roles at the narrowest practical scope.
- Avoid broad subscription-level access unless operationally justified.
- Document role assignments for audit review.

### Evidence

- RBAC assignment screenshot, if sanitized and available.
- Resource group scope notes.
- Control mapping entry.

### Residual Risk

Medium. Access reviews and identity governance should be repeated over time.

## R-002: Cross-Department Resource Visibility

### Description

Departments may view or interact with resources outside their operational responsibility.

### Impact

Cross-department visibility can violate least privilege and complicate audit boundaries.

### Mitigation

- Separate departmental workloads by resource group.
- Use role assignments aligned to department ownership.
- Use Department tags for ownership clarity.

### Evidence

- Resource group organization notes.
- Department tag policy evidence, if sanitized and available.
- RBAC notes.

### Residual Risk

Low-Medium. The risk decreases with scoped access and tagging, but resource drift requires ongoing review.

## R-003: Permanent Deletion of Keys or Secrets

### Description

A user with sufficient access could accidentally or maliciously delete important key-management resources.

### Impact

Loss of keys or secrets could disrupt applications, recovery processes, encryption workflows, or data access.

### Mitigation

- Enable Key Vault soft delete.
- Enable purge protection where appropriate.
- Keep recovery settings documented.
- Restrict Key Vault administrative access.

### Evidence

- Key Vault properties screenshot, if sanitized and available.
- Control mapping entry.

### Residual Risk

Low-Medium. Recovery protections reduce deletion risk, but administrative access still requires governance and monitoring.

## R-004: Unverified Backup Recoverability

### Description

Backups may exist without clear evidence of schedule, retention, or recovery alignment.

### Impact

Unclear backup posture increases business impact from ransomware, accidental deletion, system failure, or migration rollback needs.

### Mitigation

- Configure or document a Recovery Services vault.
- Document backup policy schedule and retention.
- Align backup design to recovery objectives.
- Add restore-test evidence in a future version if available.

### Evidence

- Recovery Services vault screenshot, if sanitized and available.
- Backup policy screenshot, if sanitized and available.
- Evidence summary.

### Residual Risk

Medium. Backup configuration evidence is useful, but restore validation would be needed to reduce this risk further.

## R-005: Unowned or Poorly Classified Resources

### Description

Resources without ownership tags are harder to triage, audit, or assign cost and risk responsibility.

### Impact

Unowned resources create operational confusion and can delay incident response, remediation ownership, and audit review.

### Mitigation

- Use Azure Policy to enforce Department tags.
- Define accepted department values.
- Review noncompliant resources.
- Use tagging to support inventory, ownership, and triage.

### Evidence

- Azure Policy tag governance screenshot, if sanitized and available.
- Control mapping entry.

### Residual Risk

Low-Medium. Tag enforcement improves governance, but exceptions and drift still require review.

## R-006: Weak Audit Evidence

### Description

Controls may exist but lack documentation explaining what was configured, why it matters, and what evidence supports the claim.

### Impact

Weak evidence makes audit review, incident review, handoffs, and control validation less reliable.

### Mitigation

- Maintain control mapping.
- Maintain risk register.
- Maintain evidence summary.
- Use professional screenshot captions.
- Remove tenant, subscription, user, and raw source identifiers before publishing evidence.

### Evidence

- Repository documentation.
- Sanitized screenshots when added.

### Residual Risk

Low. Evidence quality depends on keeping documentation current and only publishing sanitized artifacts.

## R-007: Compliance Control Gaps During Migration

### Description

Cloud migration may introduce gaps between legacy security expectations and new Azure implementation patterns.

### Impact

Compliance gaps can affect regulated operations, audit readiness, security posture, and remediation prioritization.

### Mitigation

- Align implementation themes to NIST SP 800-53 control families.
- Document PCI/FISMA-oriented governance concerns without claiming certification or authorization.
- Maintain risk-based remediation notes.
- Add Defender for Cloud regulatory compliance evidence in a future version if available and sanitized.

### Evidence

- Control mapping.
- Evidence summary.
- Risk recommendations.

### Residual Risk

Medium. Formal compliance validation would require organization-specific scope, control testing, evidence, and authorization processes.

## Severity Model

Severity is estimated using a simple qualitative model:

```text
Severity = business impact + likelihood + control maturity
```

This is not a formal quantitative risk model.

It is intended to demonstrate structured analyst reasoning for a simulated cloud governance scenario.

## Operational Use

This risk register supports security operations and governance review by helping answer:

- Which risks affect identity and access?
- Which risks affect recovery and resilience?
- Which risks affect audit evidence?
- Which risks require future validation?
- Which risks can be reduced through Azure governance controls?

## Limitations

- Simulated environment.
- Public-safe documentation only.
- No customer data.
- No production risk ownership.
- No formal compliance certification.
- No formal authorization package.
- No claim of production Microsoft Sentinel, Defender XDR, or Defender for Cloud operation.
- Risk ratings are qualitative and scenario-based.

## Future Improvements

Future versions may add:

- Sanitized Azure screenshots for each risk area.
- Defender for Cloud regulatory compliance evidence, if available.
- Azure Activity Log review notes.
- Example KQL queries for governance or identity review.
- Restore-test evidence or backup job health evidence.
- More detailed mapping to Microsoft Cloud Security Benchmark.
