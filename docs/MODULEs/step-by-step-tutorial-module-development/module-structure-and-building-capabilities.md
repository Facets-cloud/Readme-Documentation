---
title: Module Structure and Building Capabilities
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
[Git Documentation With Examples](https://github.com/Facets-cloud/module-development-examples/tree/main)

This chapter focuses on how Ops teams can build reusable infrastructure capabilities in Facets.cloud by creating and managing Terraform modules. The goal is to empower developers with modular, declarative configurations while embedding operational best practices and governance into the modules.

***

## Anatomy of a Facets Module

A Facets module is a structured collection of Terraform files and metadata that defines reusable infrastructure capabilities. At its core, a Facets module comprises:

1. **Terraform Files**:

   - **main.tf**: Contains the resource definitions and logic.
   - **variables.tf**: Defines the input parameters required for the module.
   - **outputs.tf**: Specifies the outputs exposed by the module for downstream use.

2. **Metadata File (facets.yaml)**: 

   The central configuration file that defines the Intent, Flavor, supported clouds, schema for inputs, and sample configurations. This file bridges the abstraction layer between Ops-defined capabilities and developer-friendly usage. It enables to view and configure resource forms in the UI.

Module can be initialised in your local machine using FTF CLI. [Read More](https://github.com/Facets-cloud/module-development-cli/blob/main/README.md)

***

## Facets Standard Variables

Facets.cloud provides predefined variables to simplify module development and integration. These variables ensure consistency across modules and facilitate dynamic configurations:

- **`instance`**: Contains the content of the entire declarative configuration JSON, allowing access to all input parameters.
- **`environment`**: Provides details of the Facets environment, such as namespace and other contextual information.
- **`instance_name`**: Holds the name of the resource instance being created.
- **`cluster`**: Includes details of the cluster created within the environment.

These variables should be used within Terraform code to dynamically adapt configurations to the current environment.

### **outputs.tf**

Outputs are **defined at the intent level** and remain the same for all the modules of that particular intent. The file needs to have at least the following two variables defined; otherwise, the module will fail during releases:

```hcl
locals {
  output_attributes = {}
  output_interfaces = {}
}
```

These variables can be empty or set with specific values but must be defined. The values will be visible on the overview page of the resource once it is enabled and released.

***

## Sample Module: AWS S3 Bucket

Example: <https://github.com/Facets-cloud/module-development-examples/tree/main/examples/s3>

Below is a sample directory structure and file contents for an AWS S3 bucket module:

**Directory Structure:**

```
custom_s3_module/
├── main.tf
├── variables.tf
├── outputs.tf
├── facets.yaml
```

**main.tf:**

```hcl hcl
resource "random_string" "bucket_suffix" {
  length  = 4
  special = false
  upper   = false
}

resource "aws_s3_bucket" "this" {
  bucket = "${var.environment.unique_name}-${var.instance_name}-${random_string.bucket_suffix.result}"
  acl    = lookup(var.instance.spec, "acl", "private")

  versioning {
    enabled = lookup(var.instance.spec, "versioning", false)
  }

  server_side_encryption_configuration {
    rule {
      apply_server_side_encryption_by_default {
        sse_algorithm = lookup(var.instance.spec, "sse_algorithm", "AES256")
      }
      bucket_key_enabled = false
    }
  }
}
```

**variables.tf:**

```hcl hcl
variable "instance" {
  description = "The JSON representation of the resource in the facets blueprint."
  type        = any
}

variable "instance_name" {
  description = "The architectural name for the resource as added in the facets blueprint designer."
  type        = string
}

variable "environment" {
  description = "Details about the environment."
  type        = any
}

variable "inputs" {
  description = "A map of inputs requested by the module developer."
  type        = map(any)
}
```

**outputs.tf:**

```hcl hcl
locals {
  output_interfaces = {}  # Define network interfaces if applicable
  output_attributes = {
    bucket_name = aws_s3_bucket.this.bucket
    arn         = aws_s3_bucket.this.arn
  }
}
```

***

## Understanding facets.yaml

The `facets.yaml` file is the metadata blueprint for a Facets module. It specifies critical details about the module, including its intent, flavor, supported cloud environments, input schema, and sample configurations. 

Let us understand in next chapters on what are the key fields in the facets.yaml and how to write a detailed YAML for a particular module. 

**Sample S3 facets.yaml: **

```yaml
intent: s3
flavor: aws_s3_bucket
version: 1.0
clouds:
  - aws
spec:
  properties:
    bucket_name:
      type: string
      description: "Name of the S3 bucket"
    acl:
      type: string
      description: "Access control list"
      default: "private"
    environment:
      type: string
      description: "Deployment environment"
sample:
  kind: s3
  flavor: aws_s3_bucket
  metadata: {}
  disabled: true
  version: "1.0"
  spec:
    bucket_name: "example-bucket"
    acl: "private"
    environment: "prod"
```