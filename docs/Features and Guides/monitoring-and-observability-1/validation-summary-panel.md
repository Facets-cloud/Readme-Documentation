---
title: Validations Summary Panel
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
> 📘 
> 
> **Note:** This feature is only available in the Enterprise Plan.

The Validations Summary Panel serves as a central hub for identifying potential errors, broken references, and instances where resources do not comply with Guardrail policies.

## What is Validation?

Validation is the process of checking the resource JSON's configurations and references for correctness and compliance with predefined rules. This ensures that the resources adhere to required standards and policies, helping to maintain the integrity and functionality of the system.

## When is Validation applied?

Validation is applied during the validation cycle, which is performed every 5 minutes by the Validation Summary Panel. This cycle promptly captures and displays any errors or potential issues that may arise in your resources. The continuous validation helps maintain a high level of accuracy and reliability in your deployments. Additionally, the cycle can be triggered manually by clicking on the validations button on the validations page.

## Types of Validations

The panel performs several types of validations to ensure the adherence of compliance in your resources:

- **Disabled Resource References: **Alerts you when a resource incorrectly references another resource that is disabled.
- **Invalid Reference Expression: **Highlights errors in reference expressions, such as when a service refers to a database using an incorrect path.
- **GuardRails Compliance Issues: **Notifies you of any violations against your defined guardrail policies.
- **Non-Existent Resource Reference: **Warns you when a resource references another resource that does not exist in the Blueprint.
- **JSON Syntax Error: **Detects and signals any JSON syntax errors in the resource configurations, helping you maintain correct syntax.

For more information, refer to the [Types of Validation](types-of-validations) documentation.

## Using Validations Summary Panel

1. Navigate to **Environment > Releases** and select the **Validations** tab.
2. If any validation errors are present in your resource definitions, you can find them on this page with details about the error and the location.
3. To initiate a reevaluation of these validation errors, click **Run Validation.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ddd8ab-image.png",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


You have successfully retriggered the validation process. The system is now undergoing a thorough reevaluation to ensure compliance and accuracy in your configurations.