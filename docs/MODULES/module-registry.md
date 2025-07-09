---
title: Module Registry
deprecated: false
hidden: true
metadata:
  robots: index
---
The **Module Registry** in Facets provides a centralized, searchable **catalogue of all infrastructure modules** available within a Control Plane (CP).

It includes both system-provided **Facets Modules** and Organisation-authored **Custom Modules**, enabling teams to discover, understand, and manage reusable building blocks across environments and projects.

As we know by now, in Facets, a module is defined by a unique combination of **Intent**, **Flavor**, **Version**.

***

## What the Registry Includes

The registry presents each module as an entry with the following metadata:

| Field                | Description                                                                                            |
| :------------------- | :----------------------------------------------------------------------------------------------------- |
| **Intent**           | The core capability offered by the module (e.g., `redis`, `vpc`)                                       |
| **Flavor**           | The specific implementation of the intent (e.g., `memorystore`, `terraform-aws`)                       |
| **Version**          | The semantic version of the module (e.g., `1.0`, `2.0`)                                                |
| **Description**      | A short summary of what the module provisions                                                          |
| **Spec**             | The developer-facing configuration schema (drives UI form)                                             |
| **Sample**           | An example configuration (helps drive JSON form rendering)                                             |
| **Inputs**           | Cross-module typed inputs (e.g., dependencies on `@outputs/kubernetes`)                                |
| **Outputs**          | Declared module outputs that can be consumed by other modules                                          |
| **ReadMe**           | Module-level documentation for usage, behavior, and examples                                           |
| **Clouds Supported** | Lists cloud providers (e.g., AWS, GCP, Azure) supported by the module                                  |
| **Usage Map**        | References to projects and environments where this module is currently being used in the control plane |

***

## Custom Module-Specific Metadata

In addition to the standard fields, custom modules include additional metadata to support governance and lifecycle workflows:

| Field                 | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| **Last Modified By**  | The user who last updated the module                                        |
| **Last Modified At**  | Timestamp of the most recent modification                                   |
| **Module State**      | Indicates if the module is in `preview` or `published` mode                 |
| **GitHub Repo Link**  | Points to the source repository of the module, if linked                    |
| **Actions Available** | Depending on permissions: publish module, delete module, or update metadata |

### Module State

Custom modules in Facets can exist in one of the following states:

* **Preview:** Modules in active development or validation phase. These can be used in test projects to experiment, iterate, and verify behavior. This is the default state when a module is first registered locally via the CLI.
* **Published:** Modules that have been reviewed and are considered production-ready. These are available for use across all projects within the Control Plane and are visible to all users.

Typically, module developers write and test their modules locally, register them as preview modules, and validate them within isolated test projects. Once validated, they promote the module to published, making it available across the organisation for broader use.

Transitions between states (e.g., preview → published) are governed by user permissions and organizational policy.

***

## Using the Registry

<Embed typeOfEmbed="jsfiddle" url="" />

***

## Why It Matters

For DevOps engineers and platform teams, the Module Registry acts as a single source of truth for:

* Discovering reusable infrastructure patterns
* Understanding dependencies and usage impact
* Managing lifecycle and versions of infrastructure modules
* Enabling safe, consistent, and environment-aware provisioning

Whether you're building new environments, updating blueprints, or analyzing infra usage, the Module Registry is your infrastructure catalogue and control surface.