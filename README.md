
# Access Control and Offboarding Policy Framework
### Role-Based Access Control (RBAC) and Least Privilege

<!--
Author: Shuruq
Domain: Information Security, Identity and Access Management, IT Governance
Reference: NCA Essential Cybersecurity Controls (ECC-2:2024)
Related Controls: ECC 1-8, ECC 1-9, ECC 2-2, ECC 2-12
-->

## 1. Project Overview

Managing user access is an ongoing responsibility, particularly when employees change roles or leave an organization. Accounts that remain active after an employee's departure, as well as permissions that exceed job requirements, can expose business systems and sensitive information to unauthorized access.

This project presents a practical approach to managing these risks through role-based access control (RBAC), periodic access reviews, and a documented employee offboarding process.

The framework defines access permissions for common organizational roles and outlines the steps required to remove access when employment ends. It also identifies the responsibilities of IT, HR, and cybersecurity personnel so that access changes can be tracked and independently reviewed.

The design is mapped to relevant controls in the National Cybersecurity Authority's Essential Cybersecurity Controls, ECC-2:2024. The mapping provides a basis for assessment; actual compliance depends on implementation, supporting evidence, and the organization's applicable requirements.

## 2. Objectives

The project aims to:

- Limit access to information and systems according to each user's assigned duties and business needs.
- Separate administrative responsibilities from security monitoring and independent audit activities.
- Establish a consistent process for changing or revoking access when employment or job responsibilities change.
- Maintain records of access approvals, modifications, reviews, and account deactivation.
- Define measurable operational targets for offboarding and access verification.
- Support periodic reviews of identity and access management controls.

## 3. ECC-2:2024 Control Mapping

The following controls provide the main reference points for this framework.

| ECC Control | Relevance to the Project |
|---|---|
| ECC 1-3-1 to 1-3-4 | Documenting, implementing, and periodically reviewing cybersecurity policies and procedures. |
| ECC 1-4-1 to 1-4-2 | Defining cybersecurity roles and responsibilities and reviewing them periodically. |
| ECC 1-8-1 to 1-8-3 | Reviewing cybersecurity controls and supporting independent audit and documented corrective actions. |
| ECC 1-9-1 to 1-9-6 | Managing personnel-related cybersecurity requirements, including revoking access upon termination. |
| ECC 2-2-1 to 2-2-4 | Identity and access management, least privilege, segregation of duties, privileged access management, and periodic access reviews. |
| ECC 2-6-3.3 | Removing organizational data from mobile devices and BYOD arrangements when employment ends or a device is lost. |
| ECC 2-12-1 to 2-12-4 | Managing cybersecurity event logs, monitoring privileged accounts, and reviewing implementation periodically. |

These references identify the controls relevant to the proposed design. They do not, by themselves, demonstrate that an organization has achieved compliance.

## 4. Role-Based Access Control (RBAC)

Access permissions should be assigned according to approved job responsibilities rather than individual preference. Each role should receive only the permissions necessary to perform its assigned tasks.

### 4.1 Permission Definitions

| Permission | Description |
|---|---|
| **F — Full Administrative Access** | Administrative control over the assigned system, subject to approved restrictions and logging requirements. |
| **R/W — Read and Write** | Ability to view, create, or modify authorized operational information. |
| **R — Read Only** | Ability to view information without changing system settings or records. |
| **N — No Access** | No standard access is granted to the resource. |

Full administrative access does not automatically authorize the alteration or deletion of protected security logs. Sensitive administrative actions must remain subject to appropriate safeguards and monitoring.

### 4.2 Access Control Matrix

The following matrix is a proposed baseline for a typical organization. Actual permissions should be adjusted to the organization's systems, job duties, and approved access requirements.

| Resource / System | IT System Administrator | Cybersecurity Officer | HR Department | Finance Department | General Employee |
|---|:---:|:---:|:---:|:---:|:---:|
| Active Directory / Identity Infrastructure | F | R | N | N | N |
| SIEM and Security Event Logs | R* | F* | N | N | N |
| Human Resources Information System (HRIS) | R** | R** | F | N | N |
| Financial / ERP Systems | N*** | R** | N | F | N |
| Department Shared Drives | R/W*** | R** | R/W (HR) | R/W (Finance) | R/W (Authorized Areas) |
| Identity and Access Management (IAM) | F | R / Oversight | R / Request Initiation | N | N |

**Matrix notes:**

- `*` Administrative access to SIEM and security logs must be restricted according to approved duties. Log deletion, alteration, and retention settings require additional protection and monitoring.
- `**` Read access is subject to business need, information classification, and formal authorization. Access to sensitive employee or financial information must not be assumed by default.
- `***` IT administrators should not receive unrestricted access to financial data or departmental files solely because they administer the underlying infrastructure. Any necessary exceptional access must be authorized and recorded.
- HR initiates or confirms personnel changes but does not independently administer technical identities.
- The cybersecurity function monitors access controls and investigates suspicious activity. Independent audit activities should be performed by appropriately independent personnel.

### 4.3 Access Approval and Changes

Access requests should identify the user, requested resource, business justification, required permission level, and approving authority.

The standard process is:

1. The user's manager confirms the business need.
2. The relevant system owner or delegated authority approves access to the resource.
3. IT provisions the approved permissions.
4. Privileged access is granted only where required and is subject to enhanced safeguards.
5. The request and resulting changes are recorded for subsequent review.

Changes to job responsibilities should trigger a review of existing permissions. Access that is no longer required should be removed rather than retained alongside the user's new permissions.

## 5. Security Controls and Audit Requirements

### 5.1 Least Privilege and Need-to-Know

Access must be limited to the information, systems, and functions necessary for the user's assigned responsibilities.

The implementation should consider both the need-to-know and need-to-use principles, alongside least privilege and segregation of duties.

**ECC reference:** 2-2-3.3.

### 5.2 Segregation of Duties

System administration, security monitoring, and independent audit responsibilities should be separated where necessary to reduce conflicts of interest.

For example, administrators responsible for operating infrastructure should not have unrestricted authority to remove evidence of their own activities from security logs. Security monitoring and independent reviews should provide appropriate oversight.

**ECC references:** 2-2-3.3 and 1-8-2.

### 5.3 Privileged Account Management

Privileged accounts should be identified and managed separately from ordinary user accounts where appropriate.

The organization should define approval requirements, permitted uses, monitoring arrangements, and periodic reviews for privileged access. Authentication requirements should reflect the applicable ECC requirements and the assessed risks, including the requirements for privileged accounts and remote access.

**ECC references:** 2-2-3.2 and 2-2-3.4.

### 5.4 Periodic Access Reviews

User identities and access rights should be reviewed at planned intervals. This project proposes a review every 90 days as an operational target.

The review should identify:

- Accounts belonging to former employees.
- Permissions that are no longer required.
- Dormant or unnecessary accounts.
- Excessive privileges and conflicting responsibilities.
- Exceptions that require renewal, modification, or removal.

Review results, decisions, and corrective actions should be recorded.

**ECC references:** 2-2-3.5 and 2-2-4.

### 5.5 Security Logging and Monitoring

Security event logging should cover critical information assets and privileged accounts, including relevant remote access events. Logs should be monitored continuously and protected against unauthorized alteration or deletion.

The ECC-2:2024 requirement under control 2-12-3.5 specifies a minimum retention period of 12 months for cybersecurity event logs.

Offboarding events should be recorded so that the organization can verify when access was revoked and investigate any subsequent suspicious activity.

**ECC references:** 2-12-1 to 2-12-4.

## 6. Employee Offboarding Process

The offboarding process begins when HR confirms that an employee's employment is ending. Access removal should be coordinated with the confirmed departure time and the organization's approved procedures.

### 6.1 Workflow

```text
[HR Notification]
        |
        v
[Validate Departure Details]
        |
        v
[Disable Identity and Revoke Sessions]
        |
        v
[Remove Remote and Application Access]
        |
        v
[Recover Assets and Handle Organizational Data]
        |
        v
[Verify Access Removal and Record Evidence]
        |
        v
[Review and Close Offboarding Ticket]
```

### 6.2 Process Steps

**Step 1 — HR Notification**

HR submits an offboarding request containing the employee identifier, department, manager, effective departure date, and exact departure time where applicable.

The request should be available to the authorized teams and retained as evidence of the initiation of the process.

**Step 2 — Identity Deactivation**

IT disables the employee's primary account at the approved departure time, or earlier when required by an authorized security decision.

Accounts should generally be disabled rather than immediately deleted when retention is necessary for investigations, records management, or business continuity.

The process should also cover relevant cloud identities, email access, application accounts, and other linked identities.

**Step 3 — Session and Remote Access Revocation**

The responsible teams revoke active sessions and tokens where supported by the relevant services. They also remove unnecessary VPN access, remote access permissions, SSH keys, authentication tokens, and other credentials associated with the departing employee.

The team should verify that disabling the primary identity has not left independent application accounts or alternate authentication methods active.

**Step 4 — Application and Privilege Review**

IT and relevant system owners identify and remove the employee's access to business applications, privileged groups, shared resources, and third-party services.

Where necessary, ownership of files, service responsibilities, and business resources is transferred to an authorized employee before the account is archived.

**Step 5 — Asset Recovery and Data Handling**

HR and IT coordinate the return of organizational devices, access badges, and other assigned assets.

For personally owned devices enrolled in a BYOD arrangement, the organization should remove its organizational data using approved device-management procedures, without assuming that a full-device wipe is always appropriate.

**Step 6 — Verification and Closure**

The responsible teams verify that the required access has been removed and record the outcome in the offboarding ticket.

The record should include the completion time, systems checked, outstanding exceptions, responsible personnel, and evidence of verification.

The ticket should remain open until required actions are complete or documented exceptions have been formally accepted by an authorized owner.

**ECC references:** 1-9-2, 1-9-5, 2-2-2, and 2-6-3.3.

## 7. Offboarding Checklist and Proposed Service Levels

The following targets are proposed operational service levels for this project. They are not presented as time limits explicitly mandated by ECC-2:2024.

| Action | Responsible Team | Proposed Target | Evidence |
|---|---|---|---|
| Confirm departure details and initiate the request | HR | Before the effective departure time, where practicable | HR request / ticket |
| Disable primary identity and email access | IT | Within 30 minutes of the approved effective time | Identity logs and ticket timestamp |
| Revoke active sessions and remote access | IT / Cybersecurity | Immediately as part of the offboarding response | Session and access records |
| Remove application accounts and privileged permissions | IT / System Owners | As part of the offboarding process, with completion tracked | Access review results |
| Recover assigned assets and manage organizational data | HR / IT Support | By the end of the last working day, where practicable | Asset return record |
| Transfer ownership of business resources | Manager / IT | Within 24 hours, where required | Ownership transfer record |
| Verify deactivation and close the ticket | IT / Authorized Reviewer | After all required actions are verified | Completed checklist and audit trail |
| Review account retention or deletion | IT / Records Owner | According to approved retention requirements | Retention or deletion record |

### Verification Status

The checklist should use actual execution states, for example:

- `Pending` — The action has not been completed.
- `In Progress` — The action is being performed.
- `Verified` — Completion has been checked and evidence recorded.
- `Exception` — The action could not be completed and requires documented handling.

A task should not be marked `Verified` merely because it appears in the procedure. The status must reflect the actual implementation.

## 8. Audit Evidence and Success Measures

To assess whether the framework works in practice, the organization can retain the following evidence:

- Approved access requests and role assignments.
- Periodic access review records and remediation decisions.
- Lists of privileged accounts and their assigned owners.
- HR offboarding requests and corresponding completion timestamps.
- Identity, session revocation, and application deactivation records.
- Security event logs and evidence of their protection and retention.
- Records of independent audit findings and corrective actions.

Suggested performance indicators include:

| Measure | Purpose |
|---|---|
| Percentage of offboarding requests completed within the approved SLA | Measures the timeliness of access removal. |
| Number of former employees with active accounts | Identifies potential offboarding failures. |
| Percentage of access reviews completed on schedule | Measures review execution. |
| Number of unresolved excessive-privilege findings | Tracks access-control weaknesses. |
| Percentage of sampled offboarding cases with complete evidence | Measures auditability and process consistency. |

Results should be reviewed periodically, and identified weaknesses should be assigned corrective actions with responsible owners and target completion dates.

## 9. Assumptions and Implementation Scope

This framework is a proposed baseline for an organization using centralized identity management, business applications, remote access, and shared resources.

Before operational adoption, the organization should:

1. Identify the systems and personnel within scope.
2. Define system owners and approval authorities.
3. Confirm the applicable cybersecurity and records-retention requirements.
4. Approve the access matrix and offboarding procedures.
5. Configure and test the required technical controls.
6. Validate the process through access reviews and sample offboarding tests.

The 90-day access review interval and the offboarding service levels are project design choices. They should be approved according to the organization's risk assessment and internal requirements.

## 10. Future Improvements

Potential improvements include automating account deactivation through identity management integrations, generating offboarding tickets from approved HR events, and creating reports for overdue access revocations.

Further enhancements may include automated detection of inactive accounts, privileged-access review workflows, and dashboards that track access-review completion and offboarding exceptions.

Any automation should be tested before production use and should maintain an auditable record of the actions performed.

## 11. References

- National Cybersecurity Authority (NCA), *Essential Cybersecurity Controls (ECC-2:2024)*.
- ECC controls 1-3, 1-4, 1-8, 1-9, 2-2, 2-6, and 2-12, as applicable to the activities described in this framework.

Official NCA website: https://nca.gov.sa/

---

## Project Status

This repository documents a proposed access-control and offboarding framework. Its control mappings are intended to support implementation and assessment against relevant ECC-2:2024 requirements; they are not a declaration of verified organizational compliance.
