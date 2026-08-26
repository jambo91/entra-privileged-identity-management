# Microsoft Entra Privileged Identity Management

## Project Status

🟡 Project in progress — privileged-access design and implementation underway.

## Project Overview

This home-lab project demonstrates an enterprise-style Microsoft Entra Privileged Identity Management implementation.

The project focuses on replacing permanent administrative access with controlled, time-limited and auditable role activation.

## Business Scenario

A fictional organisation has identified that administrators hold permanent privileged access even when they are not performing administrative work.

This creates unnecessary security risk if an administrator’s account is compromised.

The organisation requires a solution that:

* Removes standing administrative access
* Provides just-in-time role activation
* Requires multifactor authentication
* Requires a business justification
* Uses time-limited role assignments
* Requires approval for sensitive role activation
* Sends notifications when privileged roles are activated
* Reviews privileged access regularly
* Records privileged activity in audit logs

## Planned Implementation

The project will include:

1. A dedicated fictional privileged-access test user
2. An eligible Microsoft Entra role assignment
3. Role activation settings
4. Multifactor authentication for activation
5. Business-justification requirements
6. Time-limited role activation
7. An approval workflow
8. Just-in-time role activation testing
9. Privileged role deactivation
10. Assignment and activation audit logs
11. Privileged-role access review
12. Sanitised implementation evidence

## Privileged Access Model

The project will demonstrate the difference between:

* **Permanent active access** — the user always has the role
* **Eligible access** — the user can activate the role only when needed
* **Time-bound active access** — the user has the active role for a limited period

## Security Principles

The implementation follows these principles:

* Least privilege
* Just-in-time access
* Separation of duties
* Time-limited privilege
* Strong authentication
* Approval and accountability
* Continuous review
* Auditability

## Environment

* Microsoft Entra ID
* Microsoft Entra ID Premium P2
* Microsoft Entra Privileged Identity Management
* Microsoft Authenticator
* Fictional cloud-only identities
* Home-lab environment

## Documentation

Detailed design, implementation, testing, troubleshooting and evidence will be added as the project progresses.

## Security Notice

This repository will not contain passwords, authentication QR codes, access tokens, recovery codes, telephone numbers, confidential tenant information or unredacted personal data.

