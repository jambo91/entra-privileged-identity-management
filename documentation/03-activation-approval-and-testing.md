# PIM Activation, Approval and Testing

## Purpose

This test validated that an eligible administrator could obtain temporary User Administrator permissions only after satisfying the configured PIM security controls.

## Test Process

### 1. Eligible Role Assignment

PIM Test Administrator 01 received a direct, eligible assignment for the User Administrator role.

[View eligible assignment evidence](../screenshots/01-user-administrator-eligible-assignment.jpg)

### 2. Activation Request

The test administrator requested activation and provided:

* Multifactor authentication
* Business justification
* Change-control information
* A requested activation duration within the one-hour limit

The request entered a pending-approval state.

[View pending activation request](../screenshots/02-activation-request-pending-approval.jpg)

### 3. Independent Approval

PIM Role Approver 01 reviewed the request separately from the requesting administrator.

[View approver request evidence](../screenshots/03-approver-pending-request.jpg)

The request was approved after its purpose and time-limited nature were confirmed.

[View approved request evidence](../screenshots/04-activation-request-approved.jpg)

### 4. Temporary Role Activation

After approval, the User Administrator role appeared under Active assignments with an activation end time.

[View active role evidence](../screenshots/05-user-administrator-active-assignment.jpg)

### 5. Privileged Task Validation

The activated administrator created the fictional account PIM Validation User 01. This task confirmed that the temporary User Administrator permissions were effective.

The Microsoft Entra audit log recorded a successful Add user activity.

[View privileged activity audit evidence](../screenshots/06a-privileged-user-creation-audit-activity.jpg)

The audit target confirmed that the action affected the intended fictional validation account.

[View audit target evidence](../screenshots/06b-created-user-audit-target.jpg)

### 6. Privilege Removal

After completing the authorised task, the administrator manually deactivated the role.

The Active assignments page then showed that no privileged role remained active.

[View no-active-role evidence](../screenshots/07-no-active-privileged-role.jpg)

### 7. PIM Audit Verification

PIM audit history recorded the successful activation and deactivation events.

[View activation audit evidence](../screenshots/08a-pim-role-activation-audit.jpg)

[View deactivation audit evidence](../screenshots/08b-pim-role-deactivation-audit.jpg)

## Test Result

The test succeeded.

The administrator could not use the privileged role until the activation controls and approval workflow were completed. The role then became active for a limited period, enabled the authorised task and was removed immediately after use.

## Security Validation

The test demonstrated:

* Just-in-time administration
* MFA-protected activation
* Independent approval
* Recorded business justification
* Time-limited privileged access
* Successful privileged action auditing
* Manual removal of privilege
* No standing active User Administrator access after the task
