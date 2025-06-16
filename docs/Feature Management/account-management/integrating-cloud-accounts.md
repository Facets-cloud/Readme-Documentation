---
title: Integrating Cloud Accounts
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
This document provides a step-by-step guide for integrating cloud accounts with Facets. Amazon, Azure, and Google Cloud Platform (GCP) are the three types of cloud accounts that can be integrated with Facets.

## How to Add a Cloud Account in Facets?

Navigate to **Settings > Accounts.** All the accounts in Facets will be displayed here. Here, you will also be able to add new VCS and Cloud accounts.

### Microsoft Azure

1. From the **Accounts** page, click **Azure.**
2. Mention the **Account Name** and click **Next.**
3. Copy the command that is generated in the modal. 
4. Open the **Microsoft Azure Portal** and click the **Cloud Shell** icon on the top bar.
5. In the **[Cloud Shell](https://portal.azure.com/#cloudshell/)** terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f71b9f-image.png",
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


You have successfully added a new Azure account to the Facets Control Plane.

### Google Cloud Platform (GCP)

1. From the **Accounts** page, click **GCP.**
2. Mention the **Account Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **GCP Cloud Console** and click the **Cloud Shell** icon on the top bar.
5. In the **[Cloud Shell](https://console.cloud.google.com/welcome?project=facets-cp-test&cloudshell=true--)** terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa5147a-image.png",
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


You have successfully added a new Google Cloud Platform account to the Facets Control Plane.

### Amazon Web Services (AWS)

1. From the **Account Management** page, click **AWS.**
2. Mention the **Account Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **AWS Cloud Console** and click the **CloudShell** icon on the top bar.
5. In the **[CloudShell](https://ap-south-1.console.aws.amazon.com/cloudshell/home?region=ap-south-1#e8a9b144-b70c-468d-be1e-fd0249123b16)** terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e68e5b0-image.png",
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


You have successfully added a new AWS account to the Facets Control Plane.

### Kubernetes

**Note:** Before proceeding, [download](https://readme.facets.cloud/page/downloading-the-kubeconfig-file) the kubeconfig file from your Kubernetes cluster.

1. From the **Accounts** page, click **Kubernetes.**
2. Mention the **Account Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Load the kubeconfig file in the terminal and execute the command.
5. Facets will automatically detect if the connection has been successfully established.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/540d5d1-image.png",
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


You have successfully added a new Kubernetes account to the Facets Control Plane.