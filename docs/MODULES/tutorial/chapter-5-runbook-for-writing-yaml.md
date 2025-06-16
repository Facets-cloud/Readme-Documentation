---
title: 2a. Detailed Runbook for Writing YAML
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
This runbook provides guidance on writing YAML files for custom resources in the Facets platform. It explains the structure, fields, and conventions required to define new resources, ensuring clarity and consistency across implementations.

## Key Fields in facets.yaml:

- **intent**: High-level capability or resource type (e.g., "database", "storage").
- **flavor**: Specific implementation of the intent (e.g., "AWS RDS", "Google AlloyDB").
- **version**: Version of the module, allowing for version control and updates.
- **description**: Briefly describes the purpose or function of the resource.
- **clouds**: List of supported cloud providers (e.g., AWS, GCP).
- **inputs:** Input parameters that the Terraform module requires to function correctly.
- **outputs: **Outputs that the Terraform module produces.
- **spec**:
  - Define the **spec** properties using JSON Schema for validation.
  - Include fields like `type`, `properties`, `required`, and validation rules (e.g., `enum`, `pattern`).
  - This section can be quite extensive and depends on the nature of the intent, flavour and version.
- **sample**: Provide a sample configuration to serve as a default template when the resource is created in UI.

Let us now talk about input, output and spec section in detail.

By following this runbook, you can create robust YAML definitions for custom resources in the Facets platform, ensuring consistency, usability, and compliance with platform standards.

## Inputs Section

Inputs defines the input parameters that the Terraform module requires to function correctly. Each input is defined as a key-value pair, where the key is the name of the input and the value is an object describing the input.

Within each input object:

- **type: **This field indicates the kind of data expected by the module for that input. For instance, if the type is @outputs/databricks_account, that means the input databricks_account should be the output of a module that produces a databricks_account.
- **providers:** This field identifies the provider(s) associated with the input. These providers are used to configure resources in other Terraform modules with the help of this provider. This field offers flexibility for interoperability among various Terraform modules.
- adds_capability: set to true, indicates that this input enhances the capabilities of the resource.

**Example:**

```Text yaml
inputs:  
  databricks_account:  
    type: "@outputs/databricks_account"  
    providers:  
      - databricks  
  network_details:  
    type: "@outputs/aws_vpc"  
         adds_capability: true  
    default:  
      resource_type: network  
      resource_name: default
```

## Outputs Section

Output section defines the outputs that the Terraform module produces. Each output is also defined as a key-value pair, where the key is the name of the output, and the value is an object describing the output.

Within each output object:

- **type: **This field denotes the kind of data the module produces for that output. For example, if the type is @outputs/databricks_account, this output can be utilized as an input of this type in another module.
- **providers:** This field identifies the provider(s) relevant to the output. It includes additional details about the provider:
  - source: Specifies the origin of the provider.
  - version: Indicates the version of the provider being used.
  - attributes: Enumerates the specific pieces of data that the output will return. This information about the provider can be used to configure resources in other Terraform modules, enhancing the module’s interoperability.

**Example:**

```Text yaml
outputs:
  default:
    type: "@outputs/databricks_account"
    providers:
      databricks:
        source: databricks/databricks
        version: 1.59.0
        attributes:
          host: attributes.host
          account_id: attributes.account_id
          client_id: attributes.client_id
          client_secret: attributes.client_secret

```

## Spec Section

The **spec** section is a critical part of the YAML file. It uses JSON Schema to define properties, data types, and validation rules, ensuring consistency and clarity.

### Key JSON Schema Elements:

- **type**: Specifies the data type (e.g., `string`, `boolean`, `object`).
- **properties**: Lists the sub-properties of an object.
- **items**: Defines the schema for array elements.
- **title**: Provides a human-readable name for the property.
- **description**: Explains the property’s purpose.
- **enum**: Limits values to a predefined set.
- **minimum/maximum**: Sets numerical constraints.
- **pattern**: Uses regular expressions for string validation.
- **required**: Marks mandatory fields.

### Custom UI Fields (x-ui-\* Fields)

Facets extends JSON Schema with custom `x-ui-*` fields to enhance the user interface. These custom UI fields can be added to any field in the spec section for a desired behavior and display of that resource property.

### Common x-ui-\* Fields:

Some commonly used fields are:

- **x-ui-api-source**: Fetches dynamic data for dropdowns from an API.
- **x-ui-placeholder**: Provides placeholder text in input fields.
- **x-ui-validation**: Adds custom validation rules.
- **x-ui-visible-if**: Toggles visibility based on another field’s value.

See the complete list and its details at [x-ui-fields](https://readme.facets.cloud/docs/facets-yaml-x-ui-fields)

## Sample YAML file

Below is the sample YAML for intent: redis, flavor: k8s, version: 0.1

```yaml
intent: redis
flavor: k8s
version: "0.1"
description: Adds Redis module for Kubernetes flavor
clouds:
  - aws
  - azure
  - gcp
  - kubernetes
spec:
  title: Redis Configuration
  type: object
  properties:
    redis_version:
      type: string
      title: Redis Version
      description: Specifies the version of Redis.
      enum:
        - "6.2"
        - "7.0"
      x-ui-placeholder: "Select Redis version"
    persistence_enabled:
      type: boolean
      title: Persistence Enabled
      description: Enable persistence across restarts.
    size:
      type: object
      title: Size Configuration
      properties:
        cpu:
          type: string
          title: CPU
          pattern: "^([1-9]|[12][0-9])$"
          description: Number of CPU cores.
          x-ui-placeholder: "e.g., '2'"
          x-ui-error-message: "Value must be between 1 and 32."
        memory:
          type: string
          title: Memory
          pattern: "^(1|2|4|8)G$"
          description: Memory size.
          x-ui-placeholder: "e.g., '4G'"
          x-ui-dynamic-enum: "size_options"
  required:
    - redis_version
    - persistence_enabled
```