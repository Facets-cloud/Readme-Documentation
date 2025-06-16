---
title: Overriding Resources in an Environment
excerpt: Learn how to override different types of resources defined in your blueprint
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Facets provides the flexibility to directly modify any resource configurations in an environment from the Control Plane. This feature is particularly useful when there is a need to make modifications in the environment that will deviate from the Blueprint. Using overrides, you can make any specific changes needed as per your use case.

## How to Override Resources in an Environment?

1. Select the Environment in your defined Blueprint and select the **Resource Center** tab.
2. Select the resource you wish to override and select the **Spec Override** tab.  
   Here, you will find the current configuration values for that resource in the Blueprint and the Environment.
3. Click **Edit** to edit the configuration. Compare it with the original Blueprint configuration and make the necessary changes.  
   **Note:** You can only modify the Environment-level configuration here.
4. Click **Save Changes** and perform a **Release.**

   [block:image]{"images":[{"image":["https://files.readme.io/a58e64f-image.png",null,null],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]

**Note:** Any changes made to the overridden configuration will only take effect after the next release.

You have successfully overridden a resource at the Environment level. 

## How to Roll Back the Overrides?

1. Select the Environment in your defined Blueprint and select the **Resource Center** tab.
2. Select the required resource and select the **Spec Override** tab.
3. Click **History** to view the version history of the **Configurations.**  
   Here, you will find the Current Version and all the Previous Versions.
4. Click the **View Changes** icon beside the Current Version to compare all the changes with the last version.
5. Click the **Compare with Current Version** icon beside the Previous Versions to compare the changes with the current version.
6. Click on the **Configuration Rollback** icon beside a Previous Version you prefer to roll back to that version.
7. Click **Confirm** in the popup that appears. 

**Note:** The rolled back configuration will only take effect after the next release.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/51ea9a0-image.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


You have successfully rolled back the overridden changes.