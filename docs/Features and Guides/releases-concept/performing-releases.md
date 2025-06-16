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

<Embed url="https://app.storylane.io/9oes8dv7edgz" title="Releases | Jan 8 5:41 PM" favicon="https://assets.storylane.io/apps/prod/80/icons/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_3f81c38c-9055-45ba-a7bb-3662445f453c/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/9oes8dv7edgz" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F9oes8dv7edgz%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252F9oes8dv7edgz%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_3f81c38c-9055-45ba-a7bb-3662445f453c%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

1. Open **Projects** and select the required Project.
2. Select the **Environments** tab and select the desired Environment.
3. Now, click on the **Release** button.
4. In the modal that appears, select the [type of release](doc:releases-concept) (Full Release, Selective Release, Custom Release) and add comments if any.
5. For Full Release, enable the required toggle buttons in the **Advanced Options.** Click **Apply** or **Plan.**

* **"Apply" and "Plan"** are two options that you can choose while deploying a release in Facets.
* **"Apply"** refers to the process of actually executing the deployment according to the blueprint. This option will immediately start the deployment process and any changes made will take effect in the environment.
* **"Plan"** is a validation check before deploying a release. It allows you to preview the changes that will take place in the environment before actually applying them. The "Plan" option will generate a report that shows what changes will be made, and you can then choose to "Apply the Plan" to execute the deployment.

5. For Selective Release, you have the option to **Group by** **Resource Type** or **Resource Group,** and based on that select the desired resources or resource groups you wish to deploy, then click **Apply.**
6. For Custom Release, add custom commands and enable the required toggle buttons in the **Advanced Options.** Edit or delete the custom command if necessary. Click **Apply.**
7. **[New]** Clicking on Apply will show a **Review Release** table to preview all configuration and artifact changes across an environment before deployment, reducing the risk of unintended updates.

## Advanced Options

The **Advanced Options** section is available for all deployment types. This section allows you to enable certain advanced options that can impact the deployment process.

The advanced options in Facets include:

* **Refresh:** When enabled, the release will detect any infrastructure drifts and update resource information in the backed-up database.
* **Force:** A release that is executed with the "Force" option enabled will override any existing resources in the environment. This can be useful when there are conflicting resource definitions in the blueprint.
* **Allow Destructive Action:** When enabled, this option will delete any resources in the environment that are not defined in the blueprint. This can be useful for cleaning up any obsolete resources in an environment.

These advanced options can be used to fine-tune the deployment process and ensure it is executed as expected. It is important to understand the impact of these options before enabling them, as they can potentially cause unexpected behavior in the environment.
