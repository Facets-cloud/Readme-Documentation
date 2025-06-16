---
title: Performing Releases
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
This document lists the steps to follow to perform a release. For more information on Releases in Facets, see [Releases](doc:releases-concept).

## How to Perform a Release in Facets?

1. Open **Projects** and select the required Project.
2. Select the **Environments** tab and select the desired Environment.
3. Now, click on the **Release** button.
4. In the modal that appears, select the [type of release](doc:releases-concept) (Full Release, Selective Release, Custom Release) and add comments if any.
5. For Full Release, enable the required toggle buttons in the **Advanced Options.** Click **Apply** or **Plan.**

- **"Apply" and "Plan"** are two options that you can choose while deploying a release in Facets.
- **"Apply"** refers to the process of actually executing the deployment according to the blueprint. This option will immediately start the deployment process and any changes made will take effect in the environment.
- **"Plan"** is a validation check before deploying a release. It allows you to preview the changes that will take place in the environment before actually applying them. The "Plan" option will generate a report that shows what changes will be made, and you can then choose to "Apply the Plan" to execute the deployment.

5. For Selective Release, you have the option to **Group by** **Resource Type** or **Resource Group,** and based on that select the desired resources or resource groups you wish to deploy, then click **Apply.**
6. For Custom Release, add custom commands and enable the required toggle buttons in the **Advanced Options.** Edit or delete the custom command if necessary. Click **Apply.**

## Advanced Options

The **Advanced Options** section is available for all deployment types. This section allows you to enable certain advanced options that can impact the deployment process.

The advanced options in Facets include:

- **Refresh:** When enabled, the release will detect any infrastructure drifts and update resource information in the backed-up database.
- **Force:** A release that is executed with the "Force" option enabled will override any existing resources in the environment. This can be useful when there are conflicting resource definitions in the blueprint.
- **Allow Destructive Action:** When enabled, this option will delete any resources in the environment that are not defined in the blueprint. This can be useful for cleaning up any obsolete resources in an environment.

These advanced options can be used to fine-tune the deployment process and ensure it is executed as expected. It is important to understand the impact of these options before enabling them, as they can potentially cause unexpected behavior in the environment.

## FAQs

### 1. What is a release in Facets?

Releases in Facets are a streamlined way of deploying changes to cloud environments. They are executed using Terraform apply commands and perform a three-way comparison of state to determine and deploy the necessary changes to the corresponding cloud environment.

### 2. What is a Full Release in Facets?

A Full Release in Facets is the default release type and is used for synchronizing all changes in an environment.

### 3. What is a Selective Release in Facets?

A Selective Release in Facets allows for selective deployment of services or changes, commonly used for out-of-turn hotfixes in production environments.