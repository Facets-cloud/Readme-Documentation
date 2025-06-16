---
title: Performing Releases
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
This document lists the steps to follow to perform a release. For more information on Releases in Facets, see [Releases](doc:releases-concept).

## How to Perform a Release in Facets?

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2F9oes8dv7edgz&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2F9oes8dv7edgz&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_3f81c38c-9055-45ba-a7bb-3662445f453c%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"449\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/9oes8dv7edgz",
  "title": "Releases | Jan 8 5:41 PM",
  "favicon": "https://assets.storylane.io/apps/prod/80/icons/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_3f81c38c-9055-45ba-a7bb-3662445f453c/preview.gif",
  "provider": "https://www.storylane.io",
  "href": "https://app.storylane.io/9oes8dv7edgz",
  "typeOfEmbed": "jsfiddle"
}
[/block]


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
7. **[New]** Clicking on Apply will show a **Review Release** table to preview all configuration and artifact changes across an environment before deployment, reducing the risk of unintended updates.

## Advanced Options

The **Advanced Options** section is available for all deployment types. This section allows you to enable certain advanced options that can impact the deployment process.

The advanced options in Facets include:

- **Refresh:** When enabled, the release will detect any infrastructure drifts and update resource information in the backed-up database.
- **Force:** A release that is executed with the "Force" option enabled will override any existing resources in the environment. This can be useful when there are conflicting resource definitions in the blueprint.
- **Allow Destructive Action:** When enabled, this option will delete any resources in the environment that are not defined in the blueprint. This can be useful for cleaning up any obsolete resources in an environment.

These advanced options can be used to fine-tune the deployment process and ensure it is executed as expected. It is important to understand the impact of these options before enabling them, as they can potentially cause unexpected behavior in the environment.