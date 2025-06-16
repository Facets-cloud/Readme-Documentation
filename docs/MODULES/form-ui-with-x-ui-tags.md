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
| **Conditional Display**         | [`x-ui-visible-if`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-visible-if)             | Conditionally display this field only if another field has a specific value. _For example, show replicaCount only if deploymentType is set to "ReplicaSet"._                       |
| **Dynamic Data Sources**        | [`x-ui-dynamic-enum`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-dynamic-enum)         | Populates a dropdown based on values from another field. _For example, allow selecting a port for a health check from the list of container ports defined in the same deployment._ |
| **Dynamic Data Sources**        | [`x-ui-output-type`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-output-type)           | Marks the field as a special output type. _For example, an Ingress upstream can be selected from available Services that export a compatible output interface._                    |
| **Dynamic Data Sources**        | [`x-ui-secret-ref`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-secret-ref)             | Allows the field value to reference a secret defined at the project level. _For example, link to a stored API key without exposing its value._                                     |
| **Dynamic Data Sources**        | [`x-ui-variable-ref`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-variable-ref)         | Allows the field value to reference a variable defined at the project level. _For example, reuse a common region or environment name._                                             |
| **Dynamic Data Sources**        | [`x-ui-typeable`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-typeable)                 | Allows a field value to be typed instead of selecting it from the dropdown values                                                                                                  |
| **Environment Management**      | [`x-ui-overrides-only`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-overrides-only)     | Show this field only when overriding for a specific environment. _For example, a CIDR block must be set per environment and shouldn't have a default value._                       |
| **Environment Management**      | [`x-ui-override-disable`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-override-disable) | Prevents a field from being modified by the user for any environment - ensuring that a blueprinted or default value remains intact.                                                |
| **Form Layout & Presentation**  | [`x-ui-order`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-order)                       | Specify the rendering order of fields.                                                                                                                                             |
| **Form Layout & Presentation**  | [`x-ui-placeholder`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-placeholder)           | Provide example input placeholder text.                                                                                                                                            |
| **Form Layout & Presentation**  | [`x-ui-toggle`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-toggle)                     | Renders a group of fields as a collapsible section. _For example, show health check settings inside a deployment only if the user chooses to enable health checks._                |
| **Form Layout & Presentation**  | [`x-ui-yaml-editor`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-yaml-editor)           | Enables a YAML editor for complex object fields. _For example, custom values.yaml for a Helm chart deployment._                                                                    |
| **Validation & Error Handling** | [`x-ui-error-message`](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#x-ui-error-message)       | Defines a custom error message to show when validation fails. _For example, “CIDR must be a valid private IP block” for a pattern mismatch._                                       |

***

## **Detailed Examples**

### Conditional Display

#### **`x-ui-visible-if`**

Conditionally shows fields based on another field’s value (User can enter multiple conditions under this flag and the field will be visible only if all the conditions are met).

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
  readiness_timeout:
    type: integer
    title: Readiness Timeout
    default: 10
    minimum: 0
    maximum: 10000
    x-ui-placeholder: "Enter readiness timeout for the Pod"
    x-ui-error-message: "Value must be between 0 and 10000"
    x-ui-visible-if:
      field: spec.runtime.health_checks.readiness_check_type
      values: ["PortCheck", "HttpCheck", "ExecCheck"]
 liveliness_timeout:
 		type: integer
    title: Liveliness Timeout
    default: 10
    minimum: 0
    maximum: 10000
    x-ui-visible-if:
      - field: spec.runtime.health_checks.liveliness_check_type
        values: ["PortCheck", "HttpCheck", "ExecCheck"]
      - field: spec.runtime.health_checks.liveliness_start_up_time
      	values: ["10"]
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a576f8e5ad8f9c901a4274c3f35719d9f366f020685c0355d2c0f284e959494-Screenshot_2025-04-11_at_4.42.45_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

***

### Dynamic Data Sources

#### **`x-ui-dynamic-enum`**

Dynamically populates enum values from a schema path.

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
readiness_port:
  type: string
  title: Readiness Port
  x-ui-dynamic-enum: spec.runtime.ports.*.port
  x-ui-disable-tooltip: "No Ports Added"
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d75fcc71231625c29d08ad681e54a718d38183e90eb73baa5bef9cbfbf4beb7-Screenshot_2025-04-11_at_4.59.40_PM.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

#### **`x-ui-output-type`**

Lists down all the resources whose output is of type mentioned in "x-ui-output-type".

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
arn:
  title: ARN
  type: string
  pattern: '^(arn:aws:iam::(\d{12}|aws):policy\/[A-Za-z0-9+=,.@\-_]+|\$\{[A-Za-z0-9._-]+\})$'
  x-ui-error-message: "Value doesn't match pattern, accepted value pattern
  x-ui-output-type: "iam_policy_arn"
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d5c489fe55c854b2b3efb6b0df838d2aa50c6c98096dab27630dc9a6347d48c8-Screenshot_2025-04-11_at_4.29.05_PM.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

#### **`x-ui-secret-ref`**

Allows referencing or creating secrets (this flag shows a dropdown along with capability to type as well).

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
db_password:
  type: string
  x-ui-secret-ref: true
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d6dbfac73e11cac2ebbf1f5307f575782b5893ed74fd2cee9417ccf5590c4bb-Screenshot_2025-04-11_at_2.37.05_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

#### **`x-ui-variable-ref`**

Allows referencing or creating variables (this flag shows a dropdown along with capability to type as well).

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
db_username:
  type: string
  x-ui-variable-ref: true
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/61b8d5a044c0f75d0819d752a1d3c3b65e1b52fde32ee43d667ee0b2cc760bde-Screenshot_2025-04-11_at_2.16.07_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


<br />

<br />

</div></div>

#### **`x-ui-typeable`**

Allows a field value to be typed instead of selecting it from the dropdown values

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
java_version:
  title: Java Version
  type: string
  description: Java version to use for the build
  default: '17'
  enum:
  - '8'
  - '11'
  - '17'
  - '21'
  x-ui-typeable: true
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/02786c3bf910b58546a8640cf588fa623213b8c38c9b15887c4686cc4c47c8a5-Screenshot_2025-05-15_at_1.41.25_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

***

### Environment Management

#### **`x-ui-overrides-only`**

Only visible at the environment level and not visible at the blueprint level

<div style="display: flex; flex-direction: row; gap: 10px;"><div style="flex: 1;width:25rem">

```yaml
cidr:
  type: string
  default: "defaultValue"
  x-ui-overrides-only: true
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60a1233a4594f28d1a85b82a0a67971131ca4e2ce058e688c7f63e46da9df6c1-Screenshot_2025-04-11_at_2.41.51_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

#### **`x-ui-override-disable`**

Only visible at the blueprint level and not visible at the environment level

<div style="display: flex; flex-direction: row; gap: 10px;"><div style="flex: 1;width:25rem">

```yaml
restart_policy:
      type: string
      title: Restart Policy
      description: Restart Policy- Always, OnFailure, Never
      x-ui-override-disable: true
      enum:
        - Always
        - OnFailure
        - Never
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c50c9dbbc86c343fa8a0ced892a7bde80a57cdb3815efdb7182c29e057114419-Screenshot_2025-04-11_at_3.03.43_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

***

### Form Layout & Presentation

#### **`x-ui-order`**

Controls the exact order of rendered fields.

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
x-ui-order:
  - restart_policy
  - db_password
  - memory
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dfd51a7ddba395ede8f2616b633593dba947e244208fc7316286dbbe99dca7e0-Screenshot_2025-04-11_at_3.12.23_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

#### **`x-ui-placeholder`**

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
memory:
  type: string
  title: Memory
  x-ui-placeholder: "Enter Memory (e.g., 1Gi or 512Mi)"
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6467897f4cfcb85aa3def63571fd50f57612cd64ffccf7d7992e2d6c6263f525-Screenshot_2025-04-11_at_2.09.36_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

#### **`x-ui-toggle`**

Sets value for collapsible groups. If true, the group is collapsed by default every time the form is rendered.

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
cloud_permissions:
      type: object
      title: Cloud Permissions
      description: Assign roles, define access levels
      x-ui-toggle: false
      properties:
        aws:
          type: object
          title: AWS
          x-ui-toggle: true
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba8c898bd6f1c5783d479ebba1ad75ff9e7dea8f6e4fa6bc4059c23d50aa0910-Screenshot_2025-04-11_at_3.31.54_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

#### **`x-ui-yaml-editor`**

YAML editor for object-type fields.

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
values:
  type: object
  title: Values
  description: YAML Editor
  x-ui-yaml-editor: true
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0d5d5c79436b9deb1134d9499552d9424e306cb91bf28694fda6a604440aee49-Screenshot_2025-04-11_at_12.27.13_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

***

### Validation & Error Handling

#### **`x-ui-error-message`**

Customises error messages on validation.

<div style="display: flex; flex-direction: row; gap: 1px;"><div style="flex: 1;width:25rem">

```yaml
memory:
  type: string
  pattern: "^\\d+(Mi|Gi)$"
  x-ui-error-message: "Invalid memory format. Use Gi or Mi."
```

</div><div style="display:flex; flex: 1; align-items:center">

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5de38638c625340a80391fe3282e338b1c27784e5552c1c5635746dc8a98251b-Screenshot_2025-04-11_at_1.57.43_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


</div></div>

- [🔝 Return to top](https://readme.facets.cloud/docs/form-ui-with-x-ui-tags#detailed-examples)