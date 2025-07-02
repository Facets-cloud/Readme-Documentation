---
title: Form UI with (x-ui-* tags)
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
Facets modules support dynamic, user-friendly form rendering through x-ui extension fields in facets. YAML. These extensions control how inputs are displayed, validated, and interacted with, enabling smart defaults, conditional logic, API-driven dropdowns, YAML editors, and more.

This guide quickly references all supported x-ui fields, helping you build intuitive and robust configuration UIs for your modules.

Here is the table sorted alphabetically first by **Category**, then by **Tag**:

| **Category**                    | **Tag**                                                                                                  | **Short Description**                                                                                                                                                              |
| ------------------------------- | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Conditional Display**         | [`x-ui-visible-if`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-visible-if)             | Conditionally display this field only if another field has a specific value. *For example, show replicaCount only if deploymentType is set to "ReplicaSet".*                       |
| **Dynamic Data Sources**        | [`x-ui-dynamic-enum`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-dynamic-enum)         | Populates a dropdown based on values from another field. *For example, allow selecting a port for a health check from the list of container ports defined in the same deployment.* |
| **Dynamic Data Sources**        | [`x-ui-output-type`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-output-type)           | Marks the field as a special output type. *For example, an Ingress upstream can be selected from available Services that export a compatible output interface.*                    |
| **Dynamic Data Sources**        | [`x-ui-secret-ref`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-secret-ref)             | Allows the field value to reference a secret defined at the project level. *For example, link to a stored API key without exposing its value.*                                     |
| **Dynamic Data Sources**        | [`x-ui-variable-ref`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-variable-ref)         | Allows the field value to reference a variable defined at the project level. *For example, reuse a common region or environment name.*                                             |
| **Dynamic Data Sources**        | [`x-ui-typeable`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-typeable)                 | Allows a field value to be typed instead of selecting it from the dropdown values                                                                                                  |
| **Environment Management**      | [`x-ui-overrides-only`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-overrides-only)     | Show this field only when overriding for a specific environment. *For example, a CIDR block must be set per environment and shouldn't have a default value.*                       |
| **Environment Management**      | [`x-ui-override-disable`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-override-disable) | Prevents a field from being modified by the user for any environment - ensuring that a blueprinted or default value remains intact.                                                |
| **Form Layout & Presentation**  | [`x-ui-order`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-order)                       | Specify the rendering order of fields.                                                                                                                                             |
| **Form Layout & Presentation**  | [`x-ui-placeholder`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-placeholder)           | Provide example input placeholder text.                                                                                                                                            |
| **Form Layout & Presentation**  | [`x-ui-toggle`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-toggle)                     | Renders a group of fields as a collapsible section. *For example, show health check settings inside a deployment only if the user chooses to enable health checks.*                |
| **Form Layout & Presentation**  | [`x-ui-yaml-editor`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-yaml-editor)           | Enables a YAML editor for complex object fields. *For example, custom values.yaml for a Helm chart deployment.*                                                                    |
| **Validation & Error Handling** | [`x-ui-error-message`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-error-message)       | Defines a custom error message to show when validation fails. *For example, “CIDR must be a valid private IP block” for a pattern mismatch.*                                       |

***