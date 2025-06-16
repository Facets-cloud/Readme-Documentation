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
This document lists the steps to follow to perform a release. 

## How to Perform a Release in Facets?

1. Open **Blueprints** and choose the Blueprint that contains the environment.
2. Select the **Environments** tab and select the Environment.
3. Select the **Releases** tab and click on the **Release** button.
4. In the modal that appears, select the type of release (Full Release, Selective Release, Custom Release) and add comments if any.
5. For Full Release, enable the required toggle buttons in the **Advanced Options.** Click **Apply** or **Plan.**

- **"Apply" and "Plan"** are two options that you can choose while deploying a release in Facets.
- **"Apply"** refers to the process of actually executing the deployment according to the blueprint. This option will immediately start the deployment process and any changes made will take effect in the environment.
- **"Plan"** is a validation check before deploying a release. It allows you to preview the changes that will take place in the environment before actually applying them. The "Plan" option will generate a report that shows what changes will be made, and you can then choose to "Apply the Plan" to execute the deployment.

  [block:image]{"images":[{"image":["https://files.readme.io/f27d48c-image.png",null,"Click on the image to expand"],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]

5. For Selective Release, you have the option to **Group by** **Resource Type** or **Resource Group,** and based on that select the desired resources or resource groups you wish to deploy, then click **Apply.**

   [block:image]{"images":[{"image":["https://files.readme.io/bd009c7-image.png",null,"Click on the image to expand"],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]
6. For Custom Release, add custom commands and enable the required toggle buttons in the **Advanced Options.** Edit or delete the custom command if necessary. Click **Apply.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f7b430-image.png",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


## Advanced Options

The **Advanced Options** section is available for all deployment types. This section allows you to enable certain advanced options that can impact the deployment process.

The advanced options in Facets include:

- **Refresh:** When enabled, the release will detect any infrastructure drifts and update resource information in the backed-up database.
- **Force:** A release that is executed with the "Force" option enabled will override any existing resources in the environment. This can be useful when there are conflicting resource definitions in the blueprint.
- **Allow Destructive Action:** When enabled, this option will delete any resources in the environment that are not defined in the blueprint. This can be useful for cleaning up any obsolete resources in an environment.

These advanced options can be used to fine-tune the deployment process and ensure it is executed as expected. It is important to understand the impact of these options before enabling them, as they can potentially cause unexpected behavior in the environment.