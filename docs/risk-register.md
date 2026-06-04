# Risk Register

## Purpose

This document summarizes cloud governance and compliance risks identified in the simulated Azure migration scenario.

The register demonstrates structured risk reasoning for Azure governance controls, residual risk, and audit-defensible documentation.

This is a public portfolio artifact for a simulated regulated cloud environment. It does not represent production risk ownership.

## Risk Summary

| ID | Risk | Impact | Likelihood | Severity | Mitigation | Residual Risk |
|---|---|---:|---:|---:|---|---|
| R-001 | Overly broad Azure access | High | Medium | High | Department-scoped resource groups and Azure RBAC assignments | Medium |
| R-002 | Cross-department resource visibility | Medium | Medium | Medium | Separate resource groups and ownership tagging | Low-Medium |
| R-003 | Permanent deletion of keys or secrets | High | Low-Medium | High | Key Vault soft delete and purge protection | Low-Medium |
| R-004 | Unverified backup recoverability | High | Medium | High | Recovery Services vault and documented backup policy | Medium |
| R-005 | Unowned or poorly classified resources | Medium | High | Medium | Azure Policy Department tag enforcement | Low-Medium |
| R-006 | Weak audit evidence | Medium | Medium | Medium | Evidence summary, control mapping, and published screenshots | Low |
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

- [RBAC evidence summary](evidence-summary.md#evidence-1-rbac-resource-group-scope).
- Resource group scope notes.
- Control mapping entry.

### Residual Risk

Medium. Access reviews and identity governance remain recurring operational requirements.

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

- [RBAC evidence summary](evidence-summary.md#evidence-1-rbac-resource-group-scope).
- [Azure Policy Department tag evidence summary](evidence-summary.md#evidence-3-azure-policy-department-tag).
- Control mapping entry.

### Residual Risk

Low-Medium. Scoped access and ownership tagging reduce exposure, but resource drift still requires review.

## R-003: Permanent Deletion of Keys or Secrets

### Description

A user with sufficient access could accidentally or maliciously delete important key-management resources.

### Impact

Loss of keys or secrets could disrupt applications, recovery processes, encryption workflows, or data access.

### Mitigation

- Enable Key Vault soft delete.
- Enable purge protection.
- Keep recovery settings documented.
- Restrict Key Vault administrative access.

### Evidence

- [Key Vault recovery protection evidence summary](evidence-summary.md#evidence-2-key-vault-soft-delete-and-purge-protection).
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
- Treat restore testing as a separate validation requirement.

### Evidence

- [Recovery Services backup policy evidence summary](evidence-summary.md#evidence-4-recovery-services-backup-policy).
- Evidence summary.
- Control mapping entry.

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

- [Azure Policy Department tag evidence summary](evidence-summary.md#evidence-3-azure-policy-department-tag).
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
- Keep public evidence focused on the control claim being demonstrated.

### Evidence

- Repository documentation.
- Published evidence screenshots linked from `docs/evidence-summary.md`.

### Residual Risk

Low. Evidence quality depends on keeping documentation current and limiting claims to supported configurations.

## R-007: Compliance Control Gaps During Migration

### Description

Cloud migration may introduce gaps between legacy security expectations and new Azure implementation patterns.

### Impact

Compliance gaps can affect regulated operations, audit readiness, security posture, and remediation prioritization.

### Mitigation

- Align implementation themes to NIST SP 800-53 control families.
- Document PCI/FISMA-oriented governance concerns without claiming certification or authorization.
- Maintain risk-based remediation notes.
- Treat formal compliance validation as a separate organization-specific process.

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

It demonstrates structured analyst reasoning for a simulated cloud governance scenario.

## Operational Use

This risk register supports security operations and governance review by helping answer:

- Which risks affect identity and access?
- Which risks affect recovery and resilience?
- Which risks affect audit evidence?
- Which risks require future validation?
- Which risks can be reduced through Azure governance controls?

## Limitations

- Simulated environment.
- Public documentation only.
- No production risk ownership.
- No formal compliance certification.
- No formal authorization package.
- No production Microsoft Sentinel, Defender XDR, or Defender for Cloud operation is claimed.
- Risk ratings are qualitative and scenario-based.

## Potential Extensions

Future extensions may add:

- Additional Azure evidence for each risk area.
- Defender for Cloud posture-review documentation.
- Azure Activity Log review notes.
- Example KQL queries for governance or identity review.
- Restore-test evidence or backup job health evidence.
- More detailed mapping to Microsoft Cloud Security Benchmark.
