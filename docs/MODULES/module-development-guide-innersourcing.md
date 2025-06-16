---
title: 'Quick Guide: Module Development (Innersourcing)'
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
Welcome to the **Module Development Guide**! This document provides resources to help you build, understand, and deploy custom modules effectively. Whether you're new to module development or looking to refine your skills, follow the steps below to get started.

***

# Quick Start: Register a Custom Module

Get started with custom modules in Facets by creating and testing a simple S3 bucket module. Detailed Guide for getting started can be found here: [https://github.com/Facets-cloud/module-development-cli/blob/main/README.md](https://github.com/Facets-cloud/module-development-cli/blob/main/README.md)

## Prerequisites

* Access to a Facets Control Plane with necessary permissions
* Basic Terraform knowledge
* FTF CLI

## Phase 1: Create and Test Your Module

### Step I. Set Up Module Structure

```bash bash
ftf generate-module [OPTIONS]
```

By running this command, it prompts for details such as Intent, Flavor, Cloud, Title, and Description.

Options:

* \-i, --intent: (prompt) The intent of the module.
* \-f, --flavor: (prompt) The flavor of the module.
* \-c, --cloud: (prompt) The cloud provider for the module.
* \-t, --title: (prompt) The title of the module.
* \-d, --description: (prompt) The description of the module.

### Step II. Add Module Code

Copy the following Terraform configuration into your `main.tf` This defines the core S3 bucket resource:

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

Add these standard Facets variables to your`variables.tf`(variables can be added through FTF CLI as well. Refer to [README.md](https://github.com/Facets-cloud/module-development-cli/blob/main/README.md) to know on how to do it).

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

Set up your outputs in `outputs.tf`. These values will be available for reference after deployment:

```hcl hcl
locals {
  output_interfaces = {}  # Define network interfaces if applicable
  output_attributes = {
    bucket_name = aws_s3_bucket.this.bucket
    arn         = aws_s3_bucket.this.arn
  }
}
```

Configure your module metadata in `facets.yaml`. This tells Facets how to present and use your module:

```yaml
intent: s3
flavor: aws_s3_bucket
allowed_test_projects: ["test1","test2"]
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

### Step III: Validate Directory

Validate the Terraform configuration for formatting, initialization, and security violations using Checkov.

```Text bash
ftf validate-directory /path/to/module [OPTIONS]
```

Options: 

* \--check-only: Verifies formatting without applying changes.

The command operates directly on the provided path without additional prompts.

## Phase 2: Register Your Module

You'll need to login to your control plane to register your module. To login:

```Text bash
ftf login [OPTIONS]
```

Prompts for Control Plane URL, Username, Token, and Profile. This information is stored under a specified profile for future interactions. Options:

* \-c, --control-plane-url: (prompt) The URL of the control plane. (e.g.`https://<your-company>.console.facets.cloud)`
* \-u, --username: (prompt) Your username.
* \-t, --token: (prompt) Your access token, input is hidden
* \-p, --profile: (prompt) The profile name to use for storing credentials, defaults to default.

Personal Token can be found in the User menu. Click your profile icon in the bottom left, then select 'Personal Token'.

### Step I: Register Module

```bash bash
ftf preview-module /path/to/module [OPTIONS]
```

Options:

* \-p, --profile: (prompt) Profile to use, defaults to default.
* \-a, --auto-create-intent: Automatically create intent if not exists.
* \-f, --publishable: Indicates whether the module is publishable for production.
* \-g, --git-repo-url: Git repository URL from where the code is taken.
* \-r, --git-ref: Git reference or branch name.
* \--publish: Publish the module after preview if set.

### Step II. Enable Testing Project

After registration, your module will only be available in Testing projects. This lets you safely test the module before making it available across all projects.

Any project can be marked as a Testing Project in **UI through Project Settings** or run this command to enable testing mode for your project:

```bash bash
curl -s https://facets-cloud.github.io/facets-schemas/scripts/allow_preview_modules.sh | bash -s -- \
  -c <control-plane-url> \
  -u <your-email> \
  -t <your-token> \
  -p <project-name> \
  -a true
```

To register the module only in selected testing projects, user can mention the name of the projects in the facets.yaml under the field "allowed\_test\_projects" as shown in the sample facets.yaml above.

***

# 📚 Tutorial: Understanding Core Concepts

Begin with our [**tutorial** ](https://readme.facets.cloud/docs/chapter-1-introduction-1)to grasp the fundamentals of module development. Learn about: 

* Module structure and best practices  
* Inputs, outputs, and variables  
* Dependency management  
* Versioning and reusability

***

# 📂 Git Repository: Detailed Documentation & Examples

Explore our [Module Development GitHub Repository](https://github.com/Facets-cloud/module-development-examples) for:

✅ Comprehensive documentation\
✅ Pre-built module templates
