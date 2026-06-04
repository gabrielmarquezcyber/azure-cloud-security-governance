# Control Mapping

## Purpose

This document maps the Azure cloud security governance implementation to security objectives and compliance-oriented control themes.

This is not a certification claim. It is a public-safe control-mapping artifact for a simulated regulated cloud environment.

## Control Mapping Summary

| Security Objective | Azure Implementation | Control Theme | Evidence |
|---|---|---|---|
| Limit access by department | Department-scoped resource groups with Azure RBAC assignments | Least privilege, access control, separation of duties | RBAC screenshot or implementation notes |
| Protect keys and secrets from permanent deletion | Azure Key Vault soft delete and purge protection | Key management, recovery protection, resilience | Key Vault properties screenshot or implementation notes |
| Improve recovery readiness | Recovery Services vault and backup policy | Contingency planning, backup, recovery readiness | Backup policy screenshot or implementation notes |
| Improve resource ownership visibility | Azure Policy requiring Department tag | Governance, inventory, audit readiness | Azure Policy screenshot or implementation notes |
| Support audit-defensible documentation | Control mapping, risk register, evidence summary | Auditability, accountability, control validation | Repository documentation |

## Azure RBAC and Resource Scope

Azure role-based access control supports assigning roles at different scopes, including management group, subscription, resource group, and resource scope.

This simulated implementation emphasizes resource group scope to reduce unnecessary cross-department access.

### Implemented Control Intent

- Assign access only where required.
- Avoid broad subscription-level access unless operationally justified.
- Keep departmental assets separated by resource group.
- Support cleaner access reviews.

### Security Value

Department-scoped access reduces the chance that a user can view, modify, or administer resources outside their business function.

### Evidence

Suggested evidence file:

```text
images/rbac-resource-group-scope.png
```

Suggested caption:

```text
Department-scoped RBAC assignment showing least-privilege access boundary.
```

## Azure Key Vault Recovery Protection

Azure Key Vault soft delete and purge protection support recovery of deleted vaults or objects and reduce the risk of immediate permanent destruction.

### Implemented Control Intent

- Enable soft delete.
- Enable purge protection.
- Use department-specific vaults or department-aware access boundaries where appropriate.
- Reduce exposure to accidental or malicious deletion.

### Security Value

Key and secret recovery controls help protect availability and recoverability of cryptographic assets.

### Evidence

Suggested evidence file:

```text
images/key-vault-soft-delete-purge-protection.png
```

Suggested caption:

```text
Azure Key Vault recovery settings showing soft delete and purge protection enabled.
```

## Azure Policy Tag Governance

Azure Policy can support tag governance by enforcing or modifying tag requirements.

This project uses a Department tag governance model to improve resource accountability.

### Implemented Control Intent

- Require department ownership metadata.
- Improve resource inventory.
- Support audit and cost-allocation review.
- Reduce unmanaged or unidentified cloud resources.

### Security Value

Tag governance helps analysts and administrators identify resource ownership during incident review, access review, cost review, and compliance checks.

### Evidence

Suggested evidence file:

```text
images/azure-policy-department-tag.png
```

Suggested caption:

```text
Azure Policy assignment enforcing department tag governance.
```

## Recovery Services Backup Governance

Recovery Services vault configuration and backup policy documentation support recoverability objectives.

### Implemented Control Intent

- Define backup cadence.
- Document retention expectations.
- Support recovery readiness review.
- Preserve evidence of backup configuration.

### Security Value

Backup governance supports continuity planning, ransomware recovery, and audit review.

### Evidence

Suggested evidence file:

```text
images/recovery-services-backup-policy.png
```

Suggested caption:

```text
Recovery Services backup policy showing configured backup schedule and retention.
```

## NIST SP 800-53 Control Family Alignment

This section maps project themes to NIST SP 800-53 control families at a high level.

This is control-family alignment only. It is not a formal assessment, authorization, certification, or compliance claim.

| NIST Control Family | Project Relevance | Azure Evidence |
|---|---|---|
| AC - Access Control | RBAC assignments and least-privilege scope | Resource group scoped role assignments |
| AU - Audit and Accountability | Evidence summary and audit-defensible notes | Documentation and screenshot captions |
| CP - Contingency Planning | Backup policy and recovery readiness | Recovery Services vault evidence |
| IA - Identification and Authentication | Entra ID identity context for RBAC | Role assignment identity context |
| SC - System and Communications Protection | Key Vault recovery and protection controls | Key Vault configuration |
| CM - Configuration Management | Azure Policy tag enforcement | Policy assignment evidence |

## PCI / FISMA-Oriented Governance Notes

This project does not claim PCI DSS certification, FISMA authorization, FedRAMP authorization, or formal compliance status.

It demonstrates cloud governance controls relevant to regulated environments:

- Least-privilege access.
- Resource ownership tracking.
- Key recovery protection.
- Backup and recovery planning.
- Audit-defensible evidence.
- Risk-based recommendations.

## Security Operations Relevance

This control map supports security operations by connecting Azure configuration to investigation and triage questions:

- Who had access to the affected resource?
- Which department owns the resource?
- Are key-management resources recoverable?
- Is backup evidence available?
- Is the resource covered by policy governance?
- Is the control gap documented in a risk register?

## Limitations

- Simulated environment.
- Public-safe documentation only.
- No production tenant details.
- No customer data.
- No formal compliance certification.
- No claim of production Sentinel, Defender XDR, or Defender for Cloud operation.
- Screenshot evidence should be sanitized before upload.

## Validation Notes

This document should be reviewed against available screenshots before final image upload.

Claims that refer to a specific role assignment, Key Vault setting, policy assignment, or backup configuration should only remain if the corresponding evidence exists or the claim is clearly framed as simulated design rationale.
