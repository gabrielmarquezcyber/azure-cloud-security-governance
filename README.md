# Azure Cloud Security Governance

## Project Summary

This project documents a simulated Azure cloud security governance implementation for a regulated enterprise migration scenario.

The goal is to demonstrate Azure identity governance, least-privilege access design, key protection, backup readiness, policy-based tagging, and audit-defensible risk documentation.

This repository is based on a simulated environment and cleaned implementation notes. It does not represent production administration of a live enterprise tenant.

## Scenario

A logistics organization is migrating workloads from legacy data centers into Microsoft Azure. The environment requires improved governance across departments, stronger access isolation, recoverable key-management controls, backup readiness, and compliance-oriented documentation.

The simulated business risks include:

- Overly broad cross-department access.
- Inconsistent resource ownership and tagging.
- Weak evidence of backup recoverability.
- Risk of accidental or malicious deletion of keys or secrets.
- Need for audit-defensible notes aligned to regulated cloud environments.

## Objectives

The implementation focuses on:

- Department-scoped resource organization.
- Azure RBAC assignments at appropriate scope.
- Azure Key Vault recovery protections.
- Azure Policy tag governance.
- Recovery Services backup policy configuration.
- Risk and control mapping aligned to NIST SP 800-53 control families and PCI/FISMA-oriented governance concerns.

## Technology Areas

| Area | Azure Service / Concept |
|---|---|
| Identity and Access | Azure RBAC, Entra ID identity context |
| Resource Governance | Department-scoped resource groups |
| Key Management | Azure Key Vault soft delete and purge protection |
| Backup and Recovery | Recovery Services vault, VM backup policy |
| Policy Governance | Azure Policy tag enforcement |
| Compliance Visibility | Defender for Cloud regulatory compliance concept |
| Security Operations Relevance | Audit notes, risk register, false-positive-aware review mindset |

## Repository Contents

| File | Purpose |
|---|---|
| `README.md` | Project overview and implementation summary. |
| [`docs/control-mapping.md`](docs/control-mapping.md) | Maps Azure controls to security and compliance objectives. |
| [`docs/risk-register.md`](docs/risk-register.md) | Documents key risks, impact, mitigation, and residual risk. |
| [`docs/evidence-summary.md`](docs/evidence-summary.md) | Summarizes sanitized evidence artifacts and what each proves. |

## Implementation Summary

### 1. RBAC and Least Privilege

Department-scoped resource groups were used to separate ownership and reduce unnecessary cross-department visibility.

Azure RBAC was applied at scoped resource group level so access could be limited to the minimum operational boundary required.

Security value:

- Reduces excessive access.
- Supports least-privilege review.
- Creates cleaner audit evidence for role assignments.
- Makes departmental ownership easier to validate.

### 2. Key Vault Recovery Protection

Azure Key Vault recovery features were documented to reduce the risk of accidental or malicious loss of secrets, keys, or vault objects.

The implementation emphasizes:

- Soft delete.
- Purge protection.
- Recovery-oriented governance.
- Departmental separation of key-management resources.

Security value:

- Helps prevent immediate permanent deletion.
- Supports recovery from accidental or malicious deletion events.
- Improves resilience of encryption and key-management workflows.

### 3. Backup and Recovery Governance

A Recovery Services vault and backup policy were documented to support recoverability expectations.

The scenario emphasizes:

- Daily backup cadence.
- Defined retention.
- Recovery Services governance.
- Backup evidence review.

Security value:

- Supports continuity planning.
- Reduces ransomware and data-loss impact.
- Provides audit-facing evidence of backup configuration.

### 4. Azure Policy Tag Governance

Azure Policy was used to support governance through required resource tagging.

The Department tag model helps enforce:

- Ownership.
- Cost accountability.
- Resource classification.
- Audit-friendly resource inventory.

Security value:

- Reduces unmanaged resources.
- Improves resource accountability.
- Supports scalable governance across cloud assets.

## Control Themes Demonstrated

| Theme | Evidence |
|---|---|
| Least Privilege | RBAC scoped to department resource groups. |
| Separation of Duties | Department-specific resource organization and access boundaries. |
| Key Protection | Key Vault soft delete and purge protection. |
| Recovery Readiness | Recovery Services backup policy. |
| Governance at Scale | Azure Policy tag enforcement. |
| Audit Defensibility | Evidence summary, control mapping, and risk register. |

## What This Project Proves

This project demonstrates the ability to:

- Translate business and compliance requirements into Azure governance controls.
- Document cloud security design decisions clearly.
- Think in terms of least privilege, recovery, policy enforcement, and audit evidence.
- Communicate cloud risk in a way useful to security operations, governance, and compliance teams.
- Build public-safe portfolio artifacts without exposing raw lab, tenant, or source material.

## What This Project Does Not Claim

This repository does not claim:

- Production Azure tenant administration.
- Production Microsoft Sentinel deployment.
- Production Defender XDR operations.
- Ownership of enterprise cloud compliance certification.
- Live MSSP or multi-tenant operations.
- Real customer environment access.

It is a simulated cloud security governance implementation designed to demonstrate practical Azure security reasoning and documentation discipline.

## Relevance to Security Operations

Although this project is governance-focused, it supports security operations work by showing how cloud controls become triage and audit evidence.

Examples:

- RBAC scope affects identity investigation and privilege review.
- Key Vault recovery settings affect incident recovery.
- Azure Policy tag enforcement improves resource ownership during triage.
- Backup policy evidence supports ransomware and continuity review.
- Control mapping supports audit-facing notes and remediation prioritization.

## Future Improvements

Future versions may add:

- Example KQL queries for governance-related Azure Activity Logs.
- Microsoft Sentinel analytic rule concepts.
- Defender for Cloud posture review notes in a future extension.
- Azure Activity Log evidence review.
- Additional control mapping to Microsoft Cloud Security Benchmark.

## Author

Gabriel Marquez

Cybersecurity portfolio: Azure governance, cloud security controls, detection engineering, vulnerability prioritization, and AI/Web3 security research.

