---
title: How to use Guardrails
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Creating and Managing Guardrail Policies

This guide explains how to create, configure, and manage guardrail policies in Facets to enforce standards across your cloud infrastructure blueprints.

## Understanding Guardrail Policies

A Guardrail Policy in Facets is a set of predefined rules and conditions designed to enforce security, compliance, and operational standards within your Blueprints. These policies use Rego code to validate resources against your organization's requirements before deployment.

## Creating a New Guardrail Policy

1. Navigate to **Settings > Guardrails**
2. Click **Create Policy**
3. Choose either:
   - Create a policy from scratch
   - Select a template with pre-defined policy parameters

### Using Templates

Facets provides pre-built policy templates that simplify guardrail creation:

- Templates contain pre-written Rego code that enforces common standards
- You only need to provide 1-2 parameter values to customize the template
- Available templates cover security, compliance, and operational best practices

To use a template:

1. During policy creation, select the **Template** option
2. Choose from the available template list
3. Fill in the requested parameter values
4. Review the generated Rego code

### Configuration Options

When creating a policy, you'll need to configure the following settings:

#### Basic Information

- **Policy Name** (required): A unique identifier for your policy
- **Description**: An explanation of what the policy enforces and why

#### Severity Level

Select one of two severity levels (required):

- **Warning**: Flags potential issues while allowing the release to continue
- **Error**: Blocks releases with critical issues until resolved

#### Scope Selection

Define where and how your policy applies:

- **Blueprint** (required): Select the blueprint(s) to which this policy applies
- **Environment(s)**: Specify which deployment environments (dev, staging, production) should enforce this policy
- **Resource Type(s)**: Limit policy application to specific resource types (e.g., databases, compute instances)
- **Resource(s)**: Target individual named resources within your blueprint

#### Policy Logic

- **Rego Code**: Enter the Rego policy code that defines your validation rules or use template-generated code

### Saving Your Policy

After configuring all required fields, click **Create** to save and activate your policy.

## Managing Existing Policies

All guardrail policies can be managed from the **Settings > Guardrails** page:

### Editing Policies

1. Locate the policy you wish to modify
2. Click the **Edit** icon
3. Update the policy settings as needed
4. Click **Save**

### Cloning Policies

To create a variation of an existing policy:

1. Find the policy you want to duplicate
2. Click the **Clone Policy** icon in the Actions column
3. The Create Policy page opens with all fields pre-filled
4. Update the Policy Name and other fields as needed
5. Click **Create**

### Enabling/Disabling Policies

Toggle policies on or off using the switch in the UI on the **Settings > Guardrails** page.

## Policy Enforcement

Policies are automatically evaluated during blueprint releases. Warning-level violations display alerts but allow releases to proceed, while Error-level violations block releases until resolved. All validation results appear on the **Releases** page under the **Validations Summary** panel, with comprehensive logs tracking all policy enforcement actions.

## Interactive Demo: How to Create Guardrail Policies

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fwhlebxmkcdur&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fwhlebxmkcdur&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_9384c658-6860-4357-81b3-bf28f78ed4e3%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/whlebxmkcdur",
  "title": "Create Guardrail Policy",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_9384c658-6860-4357-81b3-bf28f78ed4e3/preview.gif",
  "provider": "https://www.storylane.io",
  "href": "https://app.storylane.io/demo/whlebxmkcdur",
  "typeOfEmbed": "jsfiddle"
}
[/block]