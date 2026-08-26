# PIM Access Review and Governance

## Purpose

The access review validated whether PIM Test Administrator 01 should continue to remain eligible for the User Administrator role.

Access reviews help organisations identify unnecessary or outdated privileged assignments and support periodic access certification.

## Review Configuration

| Setting                             | Configuration        |
| ----------------------------------- | -------------------- |
| Role reviewed                       | User Administrator   |
| Assignment type                     | Eligible             |
| Review type                         | One time             |
| Reviewer                            | PIM Role Approver 01 |
| Require reason on approval          | Yes                  |
| Show recommendations                | Yes                  |
| Automatically apply results         | No                   |
| Action if reviewer does not respond | No change            |
| Notifications and reminders         | Enabled              |

## Review Scope

The review focused on the eligible User Administrator assignment.

It did not activate the role. It only assessed whether the administrator should continue to have permission to request future time-limited activations.

[View access-review overview](../screenshots/09a-pim-access-review-overview.jpg)

## Independent Reviewer

PIM Role Approver 01 was assigned as the primary reviewer. This maintained separation between the administrator receiving eligibility and the person certifying that access.

[View reviewer configuration](../screenshots/09b-pim-access-review-reviewer.jpg)

## Review Decision

The reviewer approved continued eligibility and recorded the following business justification:

> Eligible User Administrator access remains required for controlled PIM testing. Access is protected by MFA, approval, justification and time-limited activation.

The summary recorded:

* Approved: 1
* Denied: 0
* Not reviewed: 0

[View approved review summary](../screenshots/10a-pim-access-review-approved-summary.jpg)

[View approved review result](../screenshots/10b-pim-access-review-approved-result.jpg)

## Review Completion

After the reviewer completed the decision, the one-time access review was stopped and marked as completed.

Because the assignment was approved, the administrator retained eligible access. The administrator still requires MFA, justification, ticket information and independent approval before the role can become active.

[View completed access review](../screenshots/11-pim-access-review-completed.jpg)

## Governance Outcome

The access review successfully demonstrated:

* Periodic certification of privileged eligibility
* Independent review
* Recorded business justification
* Separation of duties
* Visibility of approved, denied and outstanding decisions
* Controlled completion of the review
* Retention of eligibility without granting standing active privilege

## Important Distinction

Approving an access review does not activate the User Administrator role.

The decision only confirms that the user may remain eligible. Every future activation must still satisfy the configured PIM controls.
