---
title: Creating and Launching an Environment
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
After creating your Blueprint and resources, you can now launch the first manifestation of it: an Environment.

## How to Create an Environment?

1. Navigate to **Blueprint > Environments,** and you will be greeted with a prompt to create your first Environment.
2. The next step is to select the cloud provider. This will trigger a form for further configuration.
3. Assign a unique **Name** to your environment.
4. Select the **Infrastructure Type** as **Provisioning a New Infrastructure.**
5. Select your preferred **Release Stream** and its corresponding **Region.**
6. Now, link your **Cloud Account** with the Facets control plane or select a pre-configured cloud account. For more details, refer to the [Integrating Cloud Accounts](https://readme.facets.cloud/docs/integrating-cloud-accounts) documentation.
7. Click **Create.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d32bb39-pet_-_create_env.gif",
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


You have successfully created an Environment.

A logical environment would be created by clicking the **Create** button. However, please note that the environment will not be launched immediately and will appear as 'stopped' on the **Environments** tab.

## How to Launch the Environment?

- Navigate to the **Environment > Releases** section for that specific environment and click **Launch/Launch Environment.**
- In the popup that appears, click **Confirm.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/769ef01-pet_-_launch_env.gif",
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


You have successfully launched your Environment.

## Environment Overview

After launching the environment, you can find all relevant details about it on the environment overview page. This can be accessed by navigating to the **Environment > Overview** section.

The **Environment Overview** page consists of several useful widgets and some of them are as follows:

1. The **Environment Information** widget provides a comprehensive summary of your environment's details.
2. The **Recent Successful Releases** widget showcases the latest successful releases linked to your environment.
3. The **Cluster Allocation** widget visually displays the CPU request and memory request associated with your environment.
4. The **IaC Version** widget indicates your environment's current version. Refer to the [IaC in Facets](https://readme.facets.cloud/docs/iac-using-facets) documentation to know more about it.

By exploring these widgets, you can get a well-rounded understanding of your environment's status and functionality.

Now, let's move on to [Adding Resources](doc:pet-clinic-adding-resources) to your Blueprint.