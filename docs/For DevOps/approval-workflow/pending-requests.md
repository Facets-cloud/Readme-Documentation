---
title: Pending Approval Requests
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Pending requests in the release approval workflow involve changes that are awaiting stakeholder review or system actions before deployment. These requests can occur when the pre-release hook identifies conditions that require manual or automated intervention.

## Common Scenarios for Pending Requests

**Approval Required for Production Changes:** When the pre-release hook flags a production change for review, a Jira ticket is created. Stakeholders are notified to review and either approve or reject the release. Until approval is granted, the request remains pending.

**Concurrent Release Requests**: If multiple releases are triggered while a prior release is still awaiting approval, the earlier request is invalidated, and the latest request takes precedence. The pending status for the earlier request is updated to reflect its invalidation.

**Error Handling:** If the pre-release hook encounters an error or rejects the release (e.g., due to unmet requirements), the request remains in a pending state until corrective actions, such as blueprint modifications, are performed.

**Stakeholder Delays:** Delayed actions from stakeholders (e.g., extended time to approve or reject in Jira) can result in pending requests staying active longer than expected. Notifications and reminders can help expedite the process.

## Managing Pending Requests

Facets provides tools and visibility to manage pending requests effectively:

* **Jira Integration:** Automated ticket creation ensures that stakeholders are immediately informed of pending approvals.
* **Dashboard Monitoring:** Pending requests are visible within the Facets dashboard, allowing users to track the status and take necessary actions.
* **Notifications:** Automated reminders notify stakeholders about pending approvals to minimize delays.
* **Break Glass Scenarios:** Authorised users can bypass the pending status in critical situations, enabling urgent changes to proceed.

By proactively managing pending requests, teams can maintain efficiency and minimize bottlenecks in the release process.
