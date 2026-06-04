# Evidence Summary

## Purpose

This document summarizes the published evidence for the Azure Cloud Security Governance project.

The evidence supports four control areas: RBAC scope, Key Vault recovery protection, Azure Policy tag governance, and Recovery Services backup policy configuration.

The screenshots are cropped to the relevant Azure configuration panes and support public review of the simulated Azure governance implementation.

## Evidence Index

| Evidence | Control Area | What It Proves |
|---|---|---|
| [RBAC resource group scope evidence](../images/rbac-resource-group-scope.png) | RBAC / Least Privilege | Role assignment is scoped to the selected resource group. |
| [Key Vault recovery protection evidence](../images/key-vault-soft-delete-purge-protection.png) | Key Management | Key Vault recovery protections are configured. |
| [Azure Policy Department tag evidence](../images/azure-policy-department-tag.png) | Policy Governance | Azure Policy is used to require a Department tag and value. |
| [Recovery Services backup policy evidence](../images/recovery-services-backup-policy.png) | Backup and Recovery | Backup policy schedule and retention settings are documented. |

## Evidence 1: RBAC Resource Group Scope

![RBAC resource group scope evidence](../images/rbac-resource-group-scope.png)

*Azure RBAC role assignment showing Virtual Machine Contributor access scoped to the selected resource group.*

### Control Area

Access control and least privilege.

### What It Proves

This evidence shows Azure RBAC scoped to a selected resource group rather than broad tenant-wide access.

### Security Interpretation

Resource group scoped RBAC supports least-privilege access design and reduces unnecessary cross-department visibility.

### Limitation

This screenshot supports scoped RBAC evidence in a simulated lab environment. It does not claim production identity governance ownership.

## Evidence 2: Key Vault Soft Delete and Purge Protection

![Key Vault recovery protection evidence](../images/key-vault-soft-delete-purge-protection.png)

*Azure Key Vault recovery settings showing soft delete enabled and purge protection configured.*

### Control Area

Key management and recovery protection.

### What It Proves

This evidence shows Key Vault recovery protections, including soft delete and purge protection.

### Security Interpretation

Key Vault recovery protections reduce the risk of immediate permanent loss of key-management assets after accidental or malicious deletion.

### Limitation

This screenshot supports recovery-protection configuration evidence. It does not claim production key-management administration.

## Evidence 3: Azure Policy Department Tag

![Azure Policy Department tag evidence](../images/azure-policy-department-tag.png)

*Azure Policy assignment requiring the Department tag and a department-specific value.*

### Control Area

Governance and resource ownership.

### What It Proves

This evidence shows Azure Policy being used to support Department tag governance.

### Security Interpretation

Tag governance helps security and operations teams identify ownership, cost responsibility, and triage accountability for cloud resources.

### Limitation

This screenshot supports policy-governance evidence in a simulated environment. It does not claim production compliance enforcement.

## Evidence 4: Recovery Services Backup Policy

![Recovery Services backup policy evidence](../images/recovery-services-backup-policy.png)

*Recovery Services backup policy showing daily backup schedule, instant restore retention, and daily retention configuration.*

### Control Area

Backup and recovery readiness.

### What It Proves

This evidence shows backup policy configuration, including schedule and retention settings.

### Security Interpretation

Backup policy evidence supports continuity planning, ransomware recovery planning, and audit review.

### Limitation

This screenshot proves backup policy configuration. It does not prove restore testing or production recovery validation.

## Public Evidence Standard

The published screenshots are limited to the configuration panes needed to support the stated control claims.

The evidence supports review of the simulated Azure governance implementation without unnecessary environment context.

## Project Limitations

- Evidence is from a simulated environment.
- No production tenant evidence is included.
- No formal compliance certification is claimed.
- No restore-test completion is claimed.
- No production Microsoft Sentinel, Defender XDR, or Defender for Cloud operation is claimed.

## Potential Extensions

Future extensions may add:

- Defender for Cloud posture-review documentation.
- Azure Activity Log review examples.
- Example KQL queries for governance-related activity.
- Backup job health or restore-test evidence.
- Additional mapping to Microsoft Cloud Security Benchmark.
