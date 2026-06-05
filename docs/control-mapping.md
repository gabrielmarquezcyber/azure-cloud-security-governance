# Control Mapping

## Purpose

This document maps the Azure cloud security governance implementation to security objectives and compliance-oriented control themes.

This is not a certification claim. It is a public-safe control-mapping artifact for a simulated regulated cloud environment.

## Control Mapping Summary

| Security Objective | Azure Implementation | Control Theme | Evidence |
|---|---|---|---|
| Limit access by department | Department-scoped resource groups with Azure RBAC assignments | Least privilege, access control, separation of duties | [Published RBAC evidence](evidence-summary.md#evidence-1-rbac-resource-group-scope) |
| Protect keys and secrets from permanent deletion | Azure Key Vault soft delete and purge protection | Key management, recovery protection, resilience | [Published Key Vault recovery evidence](evidence-summary.md#evidence-2-key-vault-soft-delete-and-purge-protection) |
| Improve recovery readiness | Recovery Services vault and backup policy | Contingency planning, backup, recovery readiness | [Published Recovery Services backup policy evidence](evidence-summary.md#evidence-4-recovery-services-backup-policy) |
| Improve resource ownership visibility | Azure Policy requiring Department tag | Governance, inventory, audit readiness | [Published Azure Policy Department tag evidence](evidence-summary.md#evidence-3-azure-policy-department-tag) |
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

![RBAC resource group scope evidence](../images/rbac-resource-group-scope.png)

*Azure RBAC role assignment showing Virtual Machine Contributor access scoped to the selected resource group.*

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

![Key Vault recovery protection evidence](../images/key-vault-soft-delete-purge-protection.png)

*Azure Key Vault recovery settings showing soft delete enabled and purge protection configured.*

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

![Azure Policy Department tag evidence](../images/azure-policy-department-tag.png)

*Azure Policy assignment requiring the Department tag and a department-specific value.*

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

![Recovery Services backup policy evidence](../images/recovery-services-backup-policy.png)

*Recovery Services backup policy showing daily backup schedule, instant restore retention, and daily retention configuration.*

## NIST SP 800-53 Control Family Alignment

This section maps project themes to NIST SP 800-53 control families at a high level.

This is control-family alignment only. It is not a formal assessment, authorization, certification, or compliance claim.

| NIST Control Family | Project Relevance | Implemented Azure Control / Artifact |
|---|---|---|
| AC - Access Control | Limits excessive access and supports least privilege. | Resource-group scoped Azure RBAC assignment. |
| AU - Audit and Accountability | Supports reviewable security decisions and audit-defensible documentation. | Control mapping, risk register, and published evidence summary. |
| CP - Contingency Planning | Supports backup planning and recovery-readiness review. | Recovery Services backup policy with documented schedule and retention. |
| IA - Identification and Authentication | Connects identity context to scoped authorization decisions. | Entra ID identity context used with Azure RBAC role assignment. |
| SC - System and Communications Protection | Supports protection and recoverability of key-management assets. | Azure Key Vault soft delete and purge protection. |
| CM - Configuration Management | Supports consistent resource governance and ownership metadata. | Azure Policy assignment requiring Department tag governance. |


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
- Published screenshots are linked from `docs/evidence-summary.md`.

## Validation Notes

This document is supported by the published evidence screenshots linked from `docs/evidence-summary.md`.

Specific configuration claims are supported by the published screenshots or framed as simulated design rationale.
