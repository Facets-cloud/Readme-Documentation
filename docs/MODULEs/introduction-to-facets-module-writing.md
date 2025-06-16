---
title: Introduction to Facets Module Writing
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
If you’ve written Terraform modules before, you already understand the value of reusable infrastructure code. Facets builds on that idea — but adds structure and standards to make modules shareable, discoverable, and safe to use across teams.

Facets modules aren’t just project-level code snippets. They are **organization-level building blocks**: clearly defined, versioned, and designed to be **inner sourced** and used by others — even if they don’t write Terraform themselves.

Think of a Facets module as a **capability** — for example, “provision a Kubernetes cluster,” or “run a Databricks job.” These modules expose only the configuration developers need to set, using terms they already understand in your organization - like `environment`, `instance`, or `inputs`.

***

### Why Facets Modules?

Most teams using Terraform hit similar challenges over time:

- Different teams write modules differently — no standard pattern
- Inputs are hard to validate or document
- Developers need deep Terraform knowledge to use even simple infrastructure
- Reuse becomes risky or limited to copy-paste

Facets addresses this by introducing **a contract for modules**, built on structured inputs and outputs:

- **Inputs**: What developers are allowed to configure
- **Outputs**: What other modules or services can consume

By enforcing this structure — and using a shared language (`instance`, `environment`, `inputs`) — modules can be rolled out safely across environments, with low friction and no surprises.

***

### Modules as APIs, Not Just Libraries

A good way to think about it: **Terraform modules are like libraries** — they work, but you have to know how to use them. **Facets modules are like APIs** — self-contained, documented, and safe to use even if you didn’t write them.

Modules are defined once by platform teams and published to an internal registry. Developers consume them by selecting a capability and providing a small, focused set of inputs — either in the Facets UI or through a JSON config.

***

### Designing for Simplicity, Not Exhaustiveness

Some might ask: _“Why not expose all the options Terraform supports?”_

Facets takes the opposite approach. Modules are **designed for clarity**. The goal isn’t to make every setting available — it’s to expose just what developers need to safely deploy and manage infrastructure.

This constraint leads to **standardized, predictable assets**. It avoids the chaos of infinite patterns and configurations. And it allows developers to self-serve without needing to understand every detail of what’s happening under the hood.

True self-service at scale depends on two things:

- **Organizational context**: using inputs and language developers already know
- **Strong abstractions**: hiding what doesn’t matter to the consumer

Facets modules are built with both in mind.

***

### Who Writes Modules, and Who Uses Them

- **Platform engineers** write, version, and publish modules to the registry.
- **Developers** configure and use those modules without touching Terraform code — often through a UI.

***

### Module Writing Workflow Summary

Here’s what the process of writing and publishing a Facets module typically looks like:

1. **Plan the capability**  
   Identify the infrastructure capability you want to model (e.g., `gcp-gke`, `aws-s3`, `databricks-job`). Define what should be configurable and what should be opinionated.

2. **Write the Terraform logic**  
   Implement the core infrastructure in standard Terraform. Use only [Facets standard variables](#) (`instance`, `instance_name`, `environment`, `inputs`) to keep it compatible with the Facets system.

3. **Define the module contract**  
   Establish what the module is meant to do, what inputs developers will configure, what outputs will be available to other modules, and an example configuration to support UI rendering.

4. **Generate outputs**  
   Use structured `locals` to define `output_interfaces` and `output_attributes`, including any `secrets`.

5. **Test and validate**  
   Use `terraform validate` and other local checks to ensure inputs, outputs, and logic are working as expected.

6. **Publish the module**  
   Register the module using the Facets CLI. It becomes available in the registry and can be reused across teams.

7. **Enable consumption by developers**  
   Developers can now discover the module and configure it through the Facets UI or by providing a JSON spec — without needing to write or understand the underlying Terraform.

***

### Conceptual Model: From Terraform to Facets

```text
╭────────────────────────╮        ╭────────────────────────────╮        ╭────────────────────────────╮
│   Terraform Logic      │──────▶ │  Facets Module (Contract)  │──────▶ │  Developer Consumption      │
│                        │        │                            │        │                            │
│  - Resource definitions│        │  - Declares what it does   │        │  - Chooses capability      │
│  - Reuseable patterns  │        │  - Defines required inputs │        │  - Provides simple config  │
│                        │        │  - Exposes typed outputs   │        │  - No Terraform required   │
╰────────────────────────╯        ╰────────────────────────────╯        ╰────────────────────────────╯
           │                                 │                                     │
           ▼                                 ▼                                     ▼
   Platform Engineer                Organization-level Abstraction       Application Developer
   authors infrastructure           published to registry                uses module via UI/API
```

> Facets introduces a contract around Terraform modules — defining clear developer-facing inputs and typed outputs. This allows platform teams to publish infrastructure as reusable capabilities, and developers to consume them without needing to understand the underlying Terraform.