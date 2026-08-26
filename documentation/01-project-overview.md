# Project Overview

## Project Title

Microsoft Entra Privileged Identity Management

## Project Summary

This home-lab project demonstrates an enterprise-style privileged-access workflow using Microsoft Entra Privileged Identity Management (PIM).

The project replaces standing administrative access with eligible, time-limited access. A fictional administrator must request activation, complete multifactor authentication, provide a business justification and change-control reference, and receive approval before using the User Administrator role.

## Business Scenario

An organisation wants to reduce the risks created by permanently assigned administrative roles.

The IAM team introduces Microsoft Entra PIM so administrators receive privileged access only when it is required. Role activation must be controlled, approved, time-limited and auditable.

The organisation also performs access reviews to confirm that eligible administrators still require privileged access.

## Fictional Identities

* **PIM Test Administrator 01** — Eligible for the User Administrator role and responsible for requesting temporary activation.
* **PIM Role Approver 01** — Reviews activation requests and access-review decisions.
* **PIM Validation User 01** — A fictional user created during the authorised test to prove that the activated role provided the expected permissions.

## Project Objectives

* Replace standing administrative access with an eligible assignment.
* Configure approval-based role activation.
* Require multifactor authentication during activation.
* Require business justification and ticket information.
* Limit each role activation to one hour.
* Perform an authorised administrative task.
* Confirm the privileged task through Microsoft Entra audit logs.
* Deactivate the role after completing the task.
* Verify that no active privileged role remains.
* Perform an access review of the eligible assignment.
* Preserve sanitised evidence in GitHub.

## Technology and Licensing

* Microsoft Entra ID
* Microsoft Entra Privileged Identity Management
* Microsoft Entra ID Premium P2
* Microsoft Entra audit logs
* Microsoft Entra access reviews
* GitHub for project documentation and evidence

## Privileged-Access Workflow

1. The test administrator receives an eligible User Administrator assignment.
2. The administrator requests activation through PIM.
3. MFA, justification and ticket information are required.
4. The request is sent to an independent approver.
5. The approver validates and approves the request.
6. The User Administrator role becomes active for a limited period.
7. The administrator performs an authorised validation task.
8. Microsoft Entra records the action in its audit logs.
9. The administrator manually deactivates the role.
10. An access review confirms whether continued eligibility is justified.

## Security Principles Demonstrated

* Just-in-time privileged access
* Least privilege
* Separation of duties
* Time-bound access
* Multifactor authentication
* Approval workflow
* Business justification
* Change-control traceability
* Auditability
* Periodic access certification

## Outcome

The lab successfully demonstrated the complete lifecycle of privileged access: eligibility, activation request, independent approval, temporary role activation, privileged task execution, auditing, manual deactivation and access review.

No real production identities or confidential credentials are included in this repository.
