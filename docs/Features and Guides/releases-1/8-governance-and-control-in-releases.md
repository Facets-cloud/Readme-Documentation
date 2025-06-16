---
title: 8. Governance and Control in Releases
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
There is built-in governance and control mechanisms to ensure that every release is safe, compliant, and well-reviewed before deployment. These controls are designed to help teams catch issues early, enforce policy standards, and streamline collaboration.

This document provides an overview of governance and control as it applies specifically to **releases**. For detailed implementation and setup, refer to the linked documentation.

***

## Overview

During the release process, a series of automated checks and workflow steps are applied to ensure secure and predictable infrastructure delivery. These include:

- **Validation Summary Panel**
- **Guardrail Policies**
- **Approval Workflows**

Each mechanism plays a key role in preventing misconfigurations, enforcing organizational policies, and enabling collaborative decision-making before changes are deployed.

***

## Key Governance Features in Releases

### 1. Validation Summary Panel

Before a release is triggered, validation errors or misconfigurations are automatically checked.

- If any issues are found, a **Validation Summary Panel** is displayed.
- Users are prompted to **review and fix** errors before proceeding with the release.
- This ensures blueprint accuracy and alignment with environment context.

[Learn more about the Validation Summary Panel](https://readme.facets.cloud/docs/validation-summary-panel)

***

### 2. Guardrail Policies

Platform administrators can define **Guardrail Policies** to enforce best practices and organizational standards.

- If a release violates any guardrail, the user will see a **Guardrail Error** during the release flow.
- These policies can be used to block unsafe operations or highlight risky changes.

Example use cases:

- Preventing deletion of critical infrastructure.
- Blocking changes in production without approvals.
- Enforcing tagging standards or blueprint constraints.

[Read more on Guardrail Policies](https://readme.facets.cloud/docs/guardrail-policy)

***

### 3. Approval Workflow

There's support for built-in **Approval Workflow** to add an extra layer of human oversight before a release is executed.

- If configured, a release may require **one or more approvals** before proceeding.
- Users will see a **Pending Approval** prompt during the release flow.
- Approvers can review the plan, configuration, and guardrail context before accepting or rejecting the release.

[How Approval Workflow works](https://readme.facets.cloud/docs/approval-workflow)  
[Pending Approval Requests](https://readme.facets.cloud/docs/pending-approval-requests)

***

## Use Cases

| Scenario                                                        | Governance Feature        |
| --------------------------------------------------------------- | ------------------------- |
| Catch blueprint or config issues before deployment              | Validation Summary Panel  |
| Enforce no direct changes to production                         | Guardrail Policy          |
| Ensure changes are reviewed by a peer or admin                  | Approval Workflow         |
| Block releases that introduce destructive actions               | Guardrail + Validation    |
| Allow only authorized users to deploy to sensitive environments | RBAC or Approval Workflow |