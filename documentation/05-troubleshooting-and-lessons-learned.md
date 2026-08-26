# Troubleshooting and Lessons Learned

## Overview

This document records the issues identified during the PIM implementation and the lessons learned from resolving them.

Documenting troubleshooting demonstrates that the project included validation and problem-solving rather than only following configuration steps.

## 1. Assignment Expiration and Activation Duration

### Observation

The active-assignment expiration options started at 15 days, while the project required temporary access for only one hour.

### Explanation

These settings control different stages:

* Assignment expiration controls how long a role assignment exists.
* Eligible assignment expiration controls how long a user remains eligible.
* Activation duration controls how long temporary permissions remain active after an eligible user activates the role.

### Resolution

The eligible assignment was configured for 30 days, while individual activations were limited to one hour.

### Lesson Learned

Time-bound eligibility does not mean that privileges remain continuously active. The activation duration is the important control for just-in-time access.

## 2. Approved Request Not Displayed Under My Requests

### Observation

After approval, the activation request no longer appeared under My requests.

### Resolution

The role was verified under:

`Privileged Identity Management > My roles > Microsoft Entra roles > Active assignments`

The User Administrator role showed the Activated state and a defined end time.

### Lesson Learned

The Active assignments page is the correct location for verifying effective temporary privilege after approval.

## 3. PIM Access Review Not Visible in My Access

### Observation

The reviewer could not find the Microsoft Entra role review in the My Access portal. That page displayed only group, application and access-package review categories.

### Resolution

The reviewer used:

`Microsoft Entra admin center > ID Governance > Privileged Identity Management > Review access`

The active User Administrator eligibility review appeared in this location.

### Lesson Learned

Microsoft Entra role access reviews created through PIM are completed from the PIM Review access page.

## 4. Access Review Initially Showed Not Started

### Observation

Immediately after creation, the access review status displayed Not started.

### Resolution

After allowing time for processing and refreshing the page, the status changed to Active.

### Lesson Learned

Some Microsoft Entra governance operations require a short processing period before their final state appears.

## 5. Ticket Fields Entered in Reverse Order

### Observation

The activation audit record showed:

* Ticket system: `IAM-CHG-2026-001`
* Ticket number: `Home Lab Change Control`

These values were entered in the opposite fields.

### Impact

The activation remained valid because approval, MFA, justification and time limitation were still enforced. However, the audit information was not labelled as intended.

### Correct Format for Future Requests

* Ticket system: `Home Lab Change Control`
* Ticket number: `IAM-CHG-2026-001`

### Lesson Learned

Change-control information should be checked before submitting an activation request because it becomes part of the permanent audit record.

## 6. Screenshot Sanitisation

### Observation

Microsoft Entra screenshots can expose tenant names, email domains, user principal names, Object IDs, Tenant IDs and correlation IDs.

### Resolution

Screenshots were reviewed and sanitised before being uploaded to the public GitHub repository.

### Lesson Learned

Evidence should demonstrate the technical result while protecting unnecessary tenant and identity information.

## 7. Deactivation Verification

### Observation

Successful privileged task completion does not automatically prove that temporary access was removed.

### Resolution

The role was manually deactivated, the Active assignments page was refreshed and the PIM audit history was checked.

### Lesson Learned

A secure privileged-access workflow must verify both privilege elevation and privilege removal.

## Final Lessons

This project demonstrated that successful PIM implementation requires more than assigning a role. A complete process includes:

* Eligible assignment
* Strong activation controls
* Independent approval
* Limited activation duration
* Authorised task validation
* Audit-log verification
* Privilege deactivation
* Access certification
* Accurate documentation
