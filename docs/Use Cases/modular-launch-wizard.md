---
title: Modular Environment Launch Wizard
excerpt: >-
  Customize and control the provisioning of environment by defining your own
  Launch process
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

The **Modular Launch Wizard** provides a **flexible and customizable** approach to launching environments. Unlike the usual launch wizard, this feature allows devops to **define their own launch process** to cater their specific use-case, control which resources should be configured during the launch flow, and configure environments beyond the default single-network, single-cluster setup.

By leveraging **[Facets' module system](https://readme.facets.cloud/docs/introduction)**, users can control the launch process dynamically using the `x-ui-overrides-only` function in module YAML definitions, ensuring only relevant resources and configurations are displayed in the launch flow. This function hides non-essential fields from the UI unless explicitly enabled in the configuration, allowing users to:

- Display only necessary resources and inputs, avoiding clutter.
- Dynamically adjust which steps appear based on module dependencies.
- Ensure a more intuitive and efficient deployment process by eliminating irrelevant configurations.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d0ec77430759aed9770652e1e738719e229f204f3d15613278f71717dee8eb8-diagram-export-31-03-2025-16_48_44.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3df9e53c9ea706685625ade5f67c1ab447127020c0a38ebba9de7798fc443474-Untitled_design_1.png",
        "",
        "Kubernetes Cluster Module having x-ui-overrides-only in the YAML definition and the resource appearing during launch flow."
      ],
      "align": "center",
      "caption": "Kubernetes Cluster Module having x-ui-overrides-only set as true in the YAML definition and the resource appearing during launch flow."
    }
  ]
}
[/block]


## Key Features

- **User-Controlled Deployment Process** – Define your own launch flow based on your infrastructure needs.
- **Dynamic Resource Configuration** – Display only relevant resources by using `x-ui-overrides-only` in module YAML.
- **Supports Advanced Architectures** – Enables launching **serverless, multi-cluster, and other complex environments** beyond the default assumptions.
- **Improved Flexibility & Control** – Avoid unnecessary fields and steps in the launch process.

## How It Works

The **Modular Launch Wizard** dynamically renders forms based on **enabled resources** rather than using predefined UI fields. It follows these steps:

### Step 1: Cloud Provider Selection

- Users select a cloud provider (AWS, Azure, or GCP) and link a cloud account.

### Step 2: Resource Configuration

- A sequence of steps is created based on **enabled resources** that contain `x-ui-overrides-only` in their module YAML.
- The sequence of configuration steps is dynamically arranged according to **input-output dependencies** between resources.
- Configure resources one by one using the form mode
- **Non-mandatory fields with `x-ui-overrides-only` are optional**, ensuring a smooth workflow.
- Once all mandatory fields are configured, users can proceed to the next steps and launch the environment.

## Comparing the Previous and New Launch Wizards

| Feature                     | Previous Launch Wizard         | Modular Launch Wizard                    |
| --------------------------- | ------------------------------ | ---------------------------------------- |
| **Customization**           | Fixed UI, predefined fields    | User-controlled, dynamically rendered    |
| **Supported Architectures** | Single network, single cluster | Serverless, multi-cluster, custom setups |
| **Module Support**          | Limited customization          | Full control using `x-ui-overrides-only` |
| **Flexibility**             | Assumes default configurations | Users define necessary fields and flow   |

## Use Cases & Benefits

- **Serverless Deployments** – Configure an environment without requiring a persistent cluster.
- **Multi-Cluster Architectures** – Deploy multiple clusters within a single environment launch.
- **Custom Infrastructure Configurations** – Tailor the launch process based on specific resource needs.
- **Optimized User Experience** – Remove unnecessary steps and assumptions, making deployments more efficient.

## Getting Started

1. **Define Custom Modules** – Ensure your modules include `x-ui-overrides-only` to control which resources appear in the launch wizard. This function will also ensure that the fields are configurable at environment level only thus the fields won't appear in the configurations form.
2. **Add Required Resources** – Based on your use case, enable only the modules you need.
3. **Follow the input-output driven Process** – Configure resources dynamically, ensuring dependencies are met.
4. **Launch Your Environment** – Once all required fields are set, proceed with launch.

## Troubleshooting

### Why aren't my custom fields appearing in the launch wizard?

- Ensure your module YAML includes `x-ui-overrides-only` for the fields you want to expose.
- Verify that your module is enabled in the environment.

### Can I still use the old launch wizard?

- Yes, the **Modular Launch Wizard** is only available for projects with a custom base blueprint.
- Default projects will continue using the static launch wizard.

## Conclusion

The **Modular Launch Wizard** empowers users with **greater control and flexibility** in defining their deployment process. By leveraging **Facets' module system**, users can tailor their infrastructure provisioning workflow, ensuring a streamlined and efficient launch experience.