# Evidence Summary

## Purpose

This document defines the public-safe evidence model for the Azure Cloud Security Governance project.

The goal is to explain what evidence would support each control area without exposing tenant identifiers, subscription identifiers, personal accounts, raw source context, or unrelated screenshots.

This file should be used as the review checklist before adding any images to the repository.

## Evidence Handling Rules

Before any screenshot is uploaded publicly, confirm:

- The image is cropped to the relevant Azure configuration pane.
- Tenant IDs are removed or not visible.
- Subscription IDs are removed or not visible.
- User emails and personal identifiers are removed or not visible.
- Resource IDs and sensitive names are removed or not visible.
- Raw source context, instructional text, or unrelated browser content is not visible.
- Browser bookmarks, chat windows, desktop taskbar, and unrelated tabs are not visible.
- The screenshot supports a specific claim in this repository.
- The screenshot has a professional filename.
- The screenshot has a caption explaining what it proves.

## Evidence Index

| Evidence File | Control Area | What It Proves | Suggested Caption |
|---|---|---|---|
| `images/rbac-resource-group-scope.png` | RBAC / Least Privilege | Role assignment or access design is scoped to a department resource group rather than described as broad tenant-wide access. | Department-scoped RBAC evidence showing a least-privilege access boundary. |
| `images/key-vault-soft-delete-purge-protection.png` | Key Management | Key Vault recovery protections are configured or documented for deletion recovery. | Azure Key Vault recovery settings showing soft delete and purge protection. |
| `images/azure-policy-department-tag.png` | Policy Governance | Azure Policy is used to support Department tag governance. | Azure Policy assignment supporting department ownership metadata. |
| `images/recovery-services-backup-policy.png` | Backup and Recovery | Backup policy evidence exists for schedule and retention review. | Recovery Services backup policy showing backup schedule and retention configuration. |

The image filenames above are recommended names. Do not upload images until they are reviewed and sanitized.

## Evidence 1: RBAC Resource Group Scope

### Suggested File

```text
images/rbac-resource-group-scope.png
```

### Control Area

Access control and least privilege.

### What It Should Prove

This evidence should show that Azure access is scoped to a department-level resource group or similarly constrained operational boundary.

### Security Interpretation

Resource group scoped RBAC supports least-privilege access design and reduces unnecessary cross-department visibility.

### Do Not Publish If

- The screenshot exposes personal email addresses.
- The screenshot exposes tenant or subscription identifiers.
- The screenshot shows unrelated source context.
- The screenshot does not clearly show scope, role, or access boundary.

## Evidence 2: Key Vault Soft Delete and Purge Protection

### Suggested File

```text
images/key-vault-soft-delete-purge-protection.png
```

### Control Area

Key management and recovery protection.

### What It Should Prove

This evidence should show Key Vault recovery protections such as soft delete and purge protection.

### Security Interpretation

Key Vault recovery protections reduce the risk of immediate permanent loss of key-management assets after accidental or malicious deletion.

### Do Not Publish If

- The screenshot exposes sensitive vault names, tenant information, or subscription information.
- The screenshot does not show the relevant recovery settings.
- The screenshot includes raw source context or unrelated instructional material.

## Evidence 3: Azure Policy Department Tag

### Suggested File

```text
images/azure-policy-department-tag.png
```

### Control Area

Governance and resource ownership.

### What It Should Prove

This evidence should show Azure Policy being used to support resource ownership or Department tag governance.

### Security Interpretation

Tag governance helps security and operations teams identify ownership, cost responsibility, and triage accountability for cloud resources.

### Do Not Publish If

- The policy evidence does not show a clear governance purpose.
- The screenshot exposes subscription details or unrelated tenant metadata.
- The screenshot includes raw source context, instructional text, or unrelated browser content.

## Evidence 4: Recovery Services Backup Policy

### Suggested File

```text
images/recovery-services-backup-policy.png
```

### Control Area

Backup and recovery readiness.

### What It Should Prove

This evidence should show backup policy configuration, such as schedule, retention, or Recovery Services vault context.

### Security Interpretation

Backup policy evidence supports continuity planning, ransomware recovery planning, and audit review.

### Do Not Publish If

- The screenshot does not show backup configuration details.
- The screenshot exposes subscription, tenant, or personal account information.
- The screenshot implies restore validation that was not actually performed.

## Evidence Gaps

The MVP repository can remain valid without screenshots if the documentation is clearly framed as a simulated governance implementation.

Current evidence gaps that may be filled later:

- Sanitized RBAC scope screenshot.
- Sanitized Key Vault recovery protection screenshot.
- Sanitized Azure Policy Department tag screenshot.
- Sanitized Recovery Services backup policy screenshot.
- Defender for Cloud regulatory compliance evidence, if available and sanitized.
- Azure Activity Log review notes, if available and sanitized.
- Restore-test or backup job health evidence, if available and sanitized.

## Screenshot Review Checklist

Use this checklist before uploading images:

```text
[ ] No tenant IDs.
[ ] No subscription IDs.
[ ] No personal email addresses.
[ ] No customer data.
[ ] No raw source context.
[ ] No unrelated instructional text.
[ ] No full desktop or taskbar.
[ ] No unrelated browser tabs.
[ ] No sensitive resource IDs.
[ ] Screenshot is cropped to the relevant Azure pane.
[ ] Filename is professional and descriptive.
[ ] Screenshot supports a specific claim in README.md or docs/.
[ ] Caption explains what the screenshot proves.
```

## Public-Safe Evidence Standard

Evidence should support claims without creating unnecessary exposure.

If a screenshot is unclear, overly broad, or difficult to explain, do not upload it.

If a claim cannot be supported by sanitized evidence or public documentation, rewrite the claim as simulated design rationale or remove it.

## Limitations

- Evidence is from a simulated environment.
- No production tenant evidence is included.
- No customer evidence is included.
- No formal compliance certification is claimed.
- No restore-test completion is claimed unless supporting evidence is later added.
- No production Microsoft Sentinel, Defender XDR, or Defender for Cloud operation is claimed.

## Future Evidence Improvements

Future versions may add:

- Sanitized Azure screenshots.
- Defender for Cloud compliance posture screenshots.
- Azure Activity Log review examples.
- Example KQL queries for governance-related activity.
- Backup job health or restore-test evidence.
- Additional mapping to Microsoft Cloud Security Benchmark.

