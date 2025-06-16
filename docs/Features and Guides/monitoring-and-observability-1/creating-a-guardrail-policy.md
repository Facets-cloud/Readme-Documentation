---
title: Creating a Guardrail Policy
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
A Guardrail Policy in Facets is a set of predefined rules and conditions designed to enforce security, compliance, and operational standards within your Blueprint. 

Refer to the [Guardrail Policies](doc:guardrail-policy) concept document to learn more about it.

## How to Create a Guardrail Policy?

1. Navigate to **Settings > Guardrails.** This page displays default templates and lists existing policies.
2. To create a new policy, click **Create Policy.**
3. You can either choose to create a policy from scratch or select a **Template** where the **Policy Parameters** are pre-defined.\
   **Note:** Guardrail templates are predefined policy frameworks designed to help you quickly establish security and compliance controls within your Blueprint.
4. Enter the **Policy Name** (mandatory) and **Description.**
5. Select the **Severity** (mandatory) level: **Warning** or **Error.**
   1. **Warning:** Flags potential issues, allowing the release to continue while alerting you to areas that may need attention.
   2. **Error:** Blocks releases with critical issues, ensuring they are addressed before proceeding to release.
6. Select the desired **Blueprint** (mandatory) and **Environment(s).**
7. Now, select the required **Resource Type(s)** and **Resource(s).**
8. Enter the **Rego Code.** Refer to the [Rego Code runbook - Guardrails](https://app.clickup.com/3443930/docs/3936u-40207/3936u-64347) to learn how to enforce Guardrail Policies with Rego.
9. Click **Create.**

You have successfully create a Guardrail Policy in Facets.

## How to Clone an Existing Policy?

To clone an existing policy:

1. Click the **Clone Policy** icon under the **Actions** column beside the policy you wish to clone.
2. The Create Policy page will appear with all the fields pre-filled.
3. Update the **Policy Name** and other required fields if needed, then click **Create.**

You have successfully cloned an existing policy.
