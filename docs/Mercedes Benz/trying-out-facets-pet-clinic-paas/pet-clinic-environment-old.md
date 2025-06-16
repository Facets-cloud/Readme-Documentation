---
title: Creating and Launching an Environment
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
After creating your Blueprint and resources, you can now launch the first manifestation of it: an Environment.

## How to Create an Environment?

1. Open **Blueprints** and select the required Blueprint.
2. Now, select the **Environments** tab and you will be greeted with a prompt to create your first Environment.
3. The next step is to select the cloud provider. This will trigger a form for further configuration.
4. Assign a unique **Name** to your environment.
5. Select the **Infrastructure Type** as **Provisioning a New Infrastructure.**
6. Select your preferred **Release Stream** and its corresponding **Region.**
7. Now, link your **Cloud Account** with the Facets control plane or select a pre-configured cloud account. For more details, refer to the [Integrating Cloud Accounts](https://readme.facets.cloud/docs/integrating-cloud-accounts) documentation.
8. Click **Create.**

You have successfully created an Environment.

A logical environment would be created by clicking the **Create** button. However, please note that the environment will not be launched immediately and will appear as 'stopped' on the **Environments** tab.

## How to Launch the Environment?

* Select the specific environment and select the **Releases** tab.
* Click **Launch.**

You have successfully launched your Environment.

## Environment Overview

After launching the environment, you can find all relevant details about it on the environment overview page. This can be accessed by selecting the Environment and select the Overview section.

The **Environment Overview** page consists of several useful widgets and some of them are as follows:

1. The **Environment Information** widget provides a comprehensive summary of your environment's details.
2. The **Recent Successful Releases** widget showcases the latest successful releases linked to your environment.
3. The **Cluster Allocation** widget visually displays the CPU request and memory request associated with your environment.
4. The **IaC Version** widget indicates your environment's current version. Refer to the [IaC in Facets](https://readme.facets.cloud/docs/iac-using-facets) documentation to know more about it.

By exploring these widgets, you can get a well-rounded understanding of your environment's status and functionality.

Let's continue by [Linking the Resources.](doc:pet-clinic-linking-a-resource)
