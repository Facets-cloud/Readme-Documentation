---
title: Reusing Terraform Code in Facets Modules
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
While Facets modules and templates offer robust composition capabilities, there are scenarios where abstracting common Terraform code blocks, such as naming conventions or standardized resource provisioning, is beneficial. In these cases, leveraging external Terraform modules can promote consistency and reusability across your infrastructure.

## Utilizing External Terraform Modules

To encapsulate reusable logic, you can create standalone Terraform modules that define specific functionalities. These modules can be hosted in any Terraform-compatible registry or version-controlled repository, such as GitHub, GitLab, or Bitbucket.

For example, to standardize S3 bucket provisioning across multiple modules, you might create a Terraform module with the desired configuration and reference it in your Facets modules.

## Referencing Public Terraform Modules

Facets supports referencing public Terraform modules directly in your module definitions. You can specify the `source` attribute in your Terraform configuration to point to the desired module.

**Example:**

```hcl
module "s3_bucket" {
  source  = "git::https://github.com/your-org/terraform-aws-s3-bucket.git"
  version = "1.0.0"
  # Additional module inputs
}
```

In this example, the `s3_bucket` module is sourced from a public GitHub repository.

## Referencing Private Terraform Modules

Facets currently supports referencing public Terraform modules. If you need to reference private modules, additional configuration is required. Please contact the Facets support team to discuss enabling this feature.

For guidance on referencing private modules in Terraform, refer to the [Terraform documentation on module sources](https://developer.hashicorp.com/terraform/language/modules/sources).

## Facets Utility Modules

The [Facets Utility Modules](https://github.com/Facets-cloud/facets-utility-modules) repository contains a collection of reusable Terraform modules designed to work seamlessly with Facets. These modules encapsulate common patterns and best practices, facilitating consistent infrastructure provisioning.

Making these modules public is generally safe and can promote collaboration and reuse across different projects and teams.
