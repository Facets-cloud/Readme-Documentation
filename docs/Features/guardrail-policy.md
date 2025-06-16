---
title: Guardrail Policy
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
As organizations scale, the complexity of Blueprints also increases, potentially leading to conflicts. Facets' Guardrail Policies feature enables users to establish rules using Rego code. This feature ensures Blueprint alignment with standards and reduces the risk of errors.

By implementing policies that cover a range of Blueprint resources, organizations can make resource management more efficient. This process reduces the redundancy in policy definitions and ensures comprehensive coverage of organizations' best practices.

## Key Functionalities and Requirements

### Creation and Management of Policies

Manage guardrail policies directly from the **Settings > Guardrails** page. This includes creating new policies, editing existing ones, and removing any outdated or unnecessary policies.

Each guardrail policy, identified by a unique name and description, can be linked to specific Blueprints, environments, and Rego codes, offering a flexible approach to policy management.

### Granular Policy Enforcement

Establish enforcement criteria directly, including elements such as Blueprints, Environments, resource types, and resource names. This allows thorough control and flexibility in selecting the specific components for policy enforcement.

For instance, you have the flexibility to enforce a specific Guardrail Policy for a single resource in a Blueprint, or for a select set of resources within a particular environment in a Blueprint.

### Policy Severity Categories

Guardrail policies are classified into two severity levels: Warning and Error. These severity levels highlight the impact of policy violations on Blueprint alignment with standards. Alerts for warnings and errors can be accessed directly from the Guardrails page.

### Logging and Validation for Guardrail Policies

Policy enforcement actions are recorded in comprehensive logs, providing a detailed account of policy violations and subsequent measures.

> 📘
>
> In the event of policy violations, you can view them on the **Releases** page, under the **Validations Summary** panel.

## FAQs

### 1. What is Rego?

Rego code articulates and enforces policies across your software stack, enabling specific rules for access control, data filtering, and resource allocation. Rego evaluates queries against JSON data to ensure actions comply with specified policies, crucial for maintaining security, compliance, and operational efficiency in software systems.

### 2. Why Rego?

Rego, the policy language of Open Policy Agent (OPA), was chosen for its declarative style, prioritizing query outcomes and enhancing readability for structured documents like JSON. This approach simplifies policy creation, focusing on desired results over execution details.

### 3. How to write and test rego code?

Refer to the [Rego code documentation](https://doc.clickup.com/3443930/d/h/3936u-18744/caa022affb5455a/3936u-64707) for guidance on creating your Rego code.\
Experiment and refine your Rego code in the interactive Rego Code Playground. Visit the [Playground](https://play.openpolicyagent.org/) to test your Rego code.

### 4. Where can I view the Guardrail Policy validations?

You can view them on the **Releases** page, under the **Validations Summary** panel.

### 5. Can I enable or disable a Guardrail Policy?

Yes, you can enable or disable a policy using the toggle in the UI. Navigate to **Settings > Guardrails** page.

### 6. Is it possible to clone a Guardrail Policy?

Certainly, you can clone a Guardrail Policy by using the clone icon under Actions in the UI. Find this option on the **Settings > Guardrail** page.
