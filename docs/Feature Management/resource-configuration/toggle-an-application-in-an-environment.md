---
title: '[Rework needed] Disable/Enable an Application in an Environment'
excerpt: >-
  Learn how to selectively enable / disable apps per environment for performing
  a Release
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The primary use case for selectively enabling or disabling an application in an environment is to either add or remove that particular application in the next release. This is achieved by overriding the Container Configuration for an application from its Configuration Screen.

## Prerequisites

An application should be defined in the blueprint specification in the environment where you want to override its current configuration.

## Disable an Application from your Control Plane

1. Login to Facets Control Plane. 
2. Select the **Blueprint** which has your **Environment**.

<Image title="blueprint page.png" alt={2560} width="80%" border={true} src="https://files.readme.io/dcede10-blueprint_page.png">
  Select the Blueprint which has the environment with your application (Click on the image to expand)
</Image>

3. Navigate to **Applications** page from the sidebar and click on the Application in question.

<Image title="apps backend.png" alt={2554} width="80%" border={true} src="https://files.readme.io/123da19-apps_backend.png">
  Select the Application whose Container Configurations needs to be overridden. (Click on the image to expand)
</Image>

4. Click on the **Override** button in the Configuration tab.

<Image title="override configuration.png" alt={2163} width="80%" border={true} src="https://files.readme.io/3eda39c-override_configuration.png">
  Click on the Override button. (Click on the image to expand)
</Image>

5. Choose whether you want to disable this application from being included in the next release by ticking the **Disabled** checkbox, and clicking on the **Submit** button at the bottom of the screen. 

<Image title="disabled.png" alt={2014} width="80%" border={true} src="https://files.readme.io/e020f05-disabled.png">
  Tick the Disabled checkbox. (Click on the image to expand)
</Image>

6. You will see a popup window asking you to **Review Changes**. Click on **Submit Changes** to override the configuration.

<Image title="review changes.PNG" alt={1881} width="80%" border={true} src="https://files.readme.io/3547088-review_changes.PNG">
  Review the Changes and Submit. (Click on the image to expand)
</Image>

7. You will see a Toaster popup confirming the change and a notification that this change will be applied in the next release.

<Image title="disabled popup.png" alt={2034} width="80%" border={true} src="https://files.readme.io/19cccf8-disabled_popup.png">
  Success Message. (Click on the image to expand)
</Image>

## Enable an Application from your Control Plane

> 📘 Enabling an Application
>
> You can follow the same steps for enabling a disabled application by deselecting the tick box in Step 5 and submitting the change.

## Constraints

The change of state of an application as toggled by a user will only be enforced on the next release of the environment.
