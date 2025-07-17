---
title: Building a Facets Module
excerpt: >-
  This section explains how to turn a module concept into a working Facets
  module. You'll define the module interface using `facets.yaml`, connect it to
  Terraform logic, and use the Facets CLI to scaffold and validate your work.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: ci-of-innersourcing
      title: Continuous Integration
---
> 📘 Modules can be built using our **'Module Generation' MCP**. Try it <Anchor label="here" target="_blank" href="https://github.com/Facets-cloud/facets-module-mcp">here</Anchor>

We follow the recommended Facets module development workflow:

### 1. Plan the Capability

The goal is to model a reusable capability — like provisioning an S3 bucket. You should define what parts of the configuration developers should control, and what should be embedded as opinionated logic.

For example, this S3 bucket module lets developers:

* Set a bucket name
* Choose whether it is public or private
* Select a lifecycle policy using simple enums — like `standard`, `short`, or `longterm`

These enums are an example of organizational context and abstraction. Instead of asking developers to input raw retention periods, the module translates these values internally (e.g., `short` = 30 days, `standard` = 90 days, `longterm` = 365 days). This ensures consistency and simplifies configuration for consumers.

***

### 2. Define the Module Contract (`facets.yaml`)

Use `facets.yaml` to define your module’s public interface and metadata. This includes:

* `intent`, `flavor`, `version`, and cloud provider
* Developer-facing `spec` inputs
* Cross-module `inputs` typed via `@outputs/...`
* Structured `outputs` (bucket, policies, etc.)

This file serves as the module's single source of truth for configuration and wiring.

> You can use the [Facets CLI](https://github.com/Facets-cloud/module-development-cli/blob/main/README.md) to scaffold and validate this YAML structure.

```yaml
intent: aws-s3-bucket
flavor: secure-bucket
version: '1.0'
description: Provision a secure S3 bucket with lifecycle and access policies.
clouds:
  - aws
spec:
  title: S3 Bucket Settings
  description: Inputs to configure bucket behavior.
  type: object
  properties:
    bucket_name:
      type: string
      title: Bucket Name
    is_public:
      type: boolean
      title: Make Public
      default: false
    lifecycle_policy:
      type: string
      title: Lifecycle Policy
      enum: [standard, short, longterm]
      default: standard
  required:
    - bucket_name

inputs:
  cloud_account:
    type: "@outputs/aws_account"
    providers:
      - aws
outputs:
  attributes.bucket_name:
    title: Bucket Name
    type: "@outputs/bucket_name"
  attributes.read_policy:
    title: Read IAM Policy
    type: "@outputs/iam_policy"
  attributes.write_policy:
    title: Write IAM Policy
    type: "@outputs/iam_policy"
```

***

### 3. Write the Terraform Logic

Your Terraform module must only use the standard variables injected by the Facets engine. These map directly to your `facets.yaml`:

```text
variable "instance" {
  description = "Developer-supplied configuration."
  type = object({
    kind    = string
    flavor  = string
    version = string
    spec = object({
      bucket_name       = string
      is_public         = bool
      lifecycle_policy  = string
    })
  })
}

variable "instance_name" {
  description = "Globally unique resource name."
  type        = string
}

variable "environment" {
  description = "Environment metadata."
  type = object({
    name        = string
    unique_name = string
  })
}

variable "inputs" {
  description = "Cross-module inputs."
  type = object({
    cloud_account = object({
      region = string
    })
  })
}
```

> 🛑 Do not define additional input variables.

***

### 4. Generate Outputs via Locals

Facets modules expose outputs using the `output_attributes` object. This is a flat key-value map where each key represents an output field that can be consumed by other modules.

You may optionally define output\_interfaces if your module exposes an interface that developers can connect to — such as a Postgres reader or writer — which typically includes standard attributes like url, user, and password.

```hcl
locals {
  output_interfaces = {}

  output_attributes = {
    bucket_name       = aws_s3_bucket.this.bucket
    read_policy       = aws_iam_policy.read_policy.policy
    write_policy      = aws_iam_policy.write_policy.policy
  }
}
```

> 🔐 Mark sensitive outputs using the `sensitive(...)` wrapper — for example, `sensitive(aws_s3_bucket.this.bucket)`. Never expose secrets as plain text; marking them as sensitive ensures they are not rendered in logs or UI.. Never expose secrets as plain text — ensure any secret values are flagged to prevent them from being rendered or logged.

***

### 5. Providers

Facets modules do not define provider blocks internally. Instead, they consume providers through upstream modules using typed inputs.

To declare that your module depends on a provider, use the `providers` key inside the `inputs:` block in `facets.yaml`:

```yaml
inputs:
  cloud_account:
    type: "@outputs/aws_account"
    providers:
      - aws
```

This declares that the module expects a `cloud_account` input which includes a usable `aws` provider configuration.

> 📌 This approach allows each building block to independently receive and use the provider it needs. It also enables gradual upgrades — not every module must migrate to a new provider version at the same time.

***

## Facets Module Generation MCP

You can also build custom modules using our **Module Creation Platform (MCP)** — a powerful CLI tool designed to simplify and accelerate the process of writing Terraform modules for Facets.

Some key advantages of using this MCP:

* **Faster** module creation with guided prompts and validations
* **Standardized** structure that aligns with Facets' module registry
* **Supports custom logic**, templating, and metadata integration

Try it out <Anchor label="here" target="_blank" href="https://github.com/Facets-cloud/facets-module-mcp">here</Anchor> and start building modules tailored to your infrastructure needs.