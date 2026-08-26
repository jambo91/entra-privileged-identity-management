# Microsoft Entra Privileged Identity Management

![Microsoft Entra ID](https://img.shields.io/badge/Microsoft-Entra_ID-0078D4)
![PIM](https://img.shields.io/badge/Security-Privileged_Identity_Management-742774)
![Identity Governance](https://img.shields.io/badge/IAM-Identity_Governance-008272)
![Project Status](https://img.shields.io/badge/Project-Completed-success)
![Environment](https://img.shields.io/badge/Environment-Home_Lab-orange)

## Project Status

✅ Completed — eligible assignment, approval workflow, time-limited activation, privileged task validation, auditing, deactivation and access review were successfully tested.

## Executive Summary

This home-lab project demonstrates an enterprise-style privileged-access workflow using Microsoft Entra Privileged Identity Management (PIM).

The solution replaces standing administrative access with eligible, just-in-time access. A fictional administrator must complete MFA, provide a business justification and change-control reference, and receive independent approval before temporarily activating the User Administrator role.

The project also demonstrates privileged-task auditing, manual role deactivation and periodic certification through a Microsoft Entra access review.

## Business Problem

Permanent administrative access increases the risk of:

* Account compromise
* Excessive privilege
* Unauthorised administrative changes
* Privilege misuse
* Stale role assignments
* Limited accountability

The organisation requires a controlled process that grants administrative access only when needed and preserves evidence of every important action.

## Solution

Microsoft Entra PIM was configured to provide:

* Eligible rather than permanently active role assignment
* Just-in-time activation
* MFA during activation
* Business justification
* Change-control information
* Independent approval
* Maximum one-hour activation
* Audit logging
* Manual deactivation after use
* Periodic access review

## Fictional Lab Identities

| Identity                  | Responsibility                                                      |
| ------------------------- | ------------------------------------------------------------------- |
| PIM Test Administrator 01 | Requests and uses temporary User Administrator access               |
| PIM Role Approver 01      | Independently approves activation and reviews continued eligibility |
| PIM Validation User 01    | Test account created to validate the activated permissions          |

All identities are fictional and were created only for this home lab.

## Privileged-Access Workflow

1. Assign the User Administrator role as eligible.
2. Require MFA, justification, ticket information and approval.
3. Submit a time-limited activation request.
4. Review the request using a separate approver identity.
5. Activate the role for a maximum of one hour.
6. Perform an authorised privileged task.
7. Confirm the action in Microsoft Entra audit logs.
8. Manually deactivate the role.
9. Verify that no active privileged role remains.
10. Review continued eligibility through a PIM access review.

## PIM Security Controls

| Control                      | Configuration        |
| ---------------------------- | -------------------- |
| Role                         | User Administrator   |
| Assignment                   | Eligible             |
| Eligible assignment duration | 30 days              |
| Maximum activation duration  | 1 hour               |
| MFA required                 | Yes                  |
| Justification required       | Yes                  |
| Ticket information required  | Yes                  |
| Approval required            | Yes                  |
| Independent approver         | PIM Role Approver 01 |
| Notifications                | Enabled              |
| Manual deactivation tested   | Yes                  |
| Access review completed      | Yes                  |

## Why User Administrator Was Selected

The User Administrator role provided sufficient permissions to perform a meaningful privileged task without assigning the more powerful Global Administrator role.

This follows least-privilege principles by selecting the lowest role appropriate for the validation activity.

## Validation Results

| Test                                       | Result |
| ------------------------------------------ | ------ |
| Eligible role assignment created           | Passed |
| Activation required MFA                    | Passed |
| Business justification captured            | Passed |
| Change-control reference captured          | Passed |
| Independent approval required              | Passed |
| Temporary role activated                   | Passed |
| Authorised user-creation task completed    | Passed |
| Privileged action recorded in audit logs   | Passed |
| Role manually deactivated                  | Passed |
| No active privileged role remained         | Passed |
| Eligible assignment independently reviewed | Passed |
| Access review completed                    | Passed |

## Key Evidence

### Eligible Assignment and Activation

* [User Administrator eligible assignment](screenshots/01-user-administrator-eligible-assignment.jpg)
* [Activation request pending approval](screenshots/02-activation-request-pending-approval.jpg)
* [Approver reviewing the request](screenshots/03-approver-pending-request.jpg)
* [Activation request approved](screenshots/04-activation-request-approved.jpg)
* [Temporary User Administrator activation](screenshots/05-user-administrator-active-assignment.jpg)

### Privileged Task and Auditing

* [Successful privileged user-creation audit activity](screenshots/06a-privileged-user-creation-audit-activity.jpg)
* [Privileged user-creation audit target](screenshots/06b-created-user-audit-target.jpg)
* [No active role after deactivation](screenshots/07-no-active-privileged-role.jpg)
* [PIM activation audit record](screenshots/08a-pim-role-activation-audit.jpg)
* [PIM deactivation audit record](screenshots/08b-pim-role-deactivation-audit.jpg)

### Access Review

* [Access-review overview](screenshots/09a-pim-access-review-overview.jpg)
* [Independent reviewer configuration](screenshots/09b-pim-access-review-reviewer.jpg)
* [Approved review summary](screenshots/10a-pim-access-review-approved-summary.jpg)
* [Approved review result](screenshots/10b-pim-access-review-approved-result.jpg)
* [Completed access review](screenshots/11-pim-access-review-completed.jpg)

## Documentation

* [Project overview and business scenario](documentation/01-project-overview.md)
* [PIM role design and security controls](documentation/02-pim-role-design.md)
* [Activation, approval and testing](documentation/03-activation-approval-and-testing.md)
* [Access review and governance](documentation/04-access-review-and-governance.md)
* [Troubleshooting and lessons learned](documentation/05-troubleshooting-and-lessons-learned.md)

## Repository Structure

```text
entra-privileged-identity-management/
├── documentation/
│   ├── 01-project-overview.md
│   ├── 02-pim-role-design.md
│   ├── 03-activation-approval-and-testing.md
│   ├── 04-access-review-and-governance.md
│   ├── 05-troubleshooting-and-lessons-learned.md
│   └── README.md
├── screenshots/
│   ├── PIM implementation evidence
│   └── README.md
└── README.md
```

## Skills Demonstrated

* Microsoft Entra Privileged Identity Management
* Privileged-role configuration
* Just-in-time access
* Least-privilege design
* MFA enforcement
* Approval workflows
* Separation of duties
* Time-bound role activation
* Microsoft Entra audit-log analysis
* Privileged-access deactivation
* Access reviews
* Identity governance
* Security documentation
* GitHub portfolio management

## Lessons Learned

The project confirmed that eligible assignment duration and activation duration control different parts of the privileged-access lifecycle.

It also demonstrated that role activation must be verified under Active assignments, PIM role reviews are performed through the PIM Review access page, and change-control values must be checked carefully before submission because they become part of the audit record.

Detailed findings are available in [Troubleshooting and lessons learned](documentation/05-troubleshooting-and-lessons-learned.md).

## Security and Privacy

This repository contains no passwords, access tokens, authentication secrets or real production identities.

Screenshots were sanitised before publication. Tenant names, domains, email addresses, Object IDs, Tenant IDs, correlation IDs and other unnecessary identifying information were removed or redacted.

## Project Outcome

The project successfully demonstrated a complete privileged-access lifecycle:

**Eligible → Request → MFA → Approval → Activate → Perform task → Audit → Deactivate → Review**

The final design provides temporary, controlled and auditable administrative access without leaving the test administrator with standing active privileges.


