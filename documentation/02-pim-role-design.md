# PIM Role Design and Security Controls

## Role Selected

The **User Administrator** role was selected for this home-lab project.

This role provided enough permission to demonstrate a real privileged task without using the highly privileged Global Administrator role.

## Assignment Model

The fictional administrator was configured with an **eligible assignment**, not a permanently active assignment.

| Setting                      | Configuration             |
| ---------------------------- | ------------------------- |
| User                         | PIM Test Administrator 01 |
| Role                         | User Administrator        |
| Assignment type              | Eligible                  |
| Membership                   | Direct                    |
| Eligible assignment duration | 30 days                   |
| Activation duration          | Maximum 1 hour            |
| Permanent active assignment  | Not used                  |

An eligible assignment means that the user does not hold the active administrative permissions until an approved activation is completed.

## Activation Controls

The following controls were configured for the User Administrator role:

| Control                     | Configuration        |
| --------------------------- | -------------------- |
| Require MFA on activation   | Yes                  |
| Require justification       | Yes                  |
| Require ticket information  | Yes                  |
| Require approval            | Yes                  |
| Maximum activation duration | 1 hour               |
| Approver                    | PIM Role Approver 01 |
| Notifications               | Enabled              |

## Separation of Duties

Two separate fictional identities were used:

* **PIM Test Administrator 01** requested and used the temporary role.
* **PIM Role Approver 01** independently reviewed and approved the request.

The requesting administrator could not approve their own activation request. This separation reduces the risk of uncontrolled privilege elevation.

## Assignment Expiration and Activation Duration

The assignment-expiration settings and activation-duration settings serve different purposes.

* **Eligible assignment expiration** controls how long the user remains eligible to request the role.
* **Active assignment expiration** controls long-term assignments that are already active.
* **Activation duration** controls how long an eligible user receives temporary privileges after activation.

For this project, the eligible assignment lasted 30 days, while each approved activation was limited to one hour.

## Approval Requirements

The activation request included:

* A business justification
* A change-control reference
* MFA verification
* Approval from a separate identity

The lab used the following fictional change reference:

`IAM-CHG-2026-001`

## Least-Privilege Design

The project avoided assigning Global Administrator to the test account. The lower-privileged User Administrator role was sufficient for the authorised validation task.

The role was manually deactivated immediately after the task was completed, instead of waiting for the one-hour activation period to expire.

## Risk Reduction

This design reduced risk by ensuring that:

* Privileged permissions were not permanently active.
* Activation required strong authentication.
* A separate person approved the request.
* Access had a defined maximum duration.
* The administrative action was recorded.
* Privilege was removed after use.
* Continued eligibility was independently reviewed.
