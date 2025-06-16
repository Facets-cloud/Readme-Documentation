---
title: Container Registries
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
Facets now provides support for multiple Container Registries, including AWS ECR and other platforms like ACR, GCR, Nexus, and Docker Hub.

**Note:** Users require 'ARTIFACTORY_WRITE' and 'ARTIFACTORY_DELETE' permissions to create, modify, or delete a Container Registry.

## Adding a Container Registry

1. Navigate to **Settings > Container Registries.** This page will display all the existing Registries. 
2. To add a new registry, click **Add Container Registry. **
3. Mention the **Registry Name, Registry Type** and **Registry URL.**
4. Under Registry Types, you can choose between **AWS ECR** and **Others.**
   1. If you select **AWS ECR,** mention the **AWS Key** and **AWS Secret.**
   2. If you select **Others,** this includes platforms such as Docker Hub, Nexus, Google Artifact Registry, and Azure Container Registry, provide the associated **Username** and **Password.**
5. Click **Create.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf3e637-Container_Reg.gif",
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


You have successfully added a new Container Registry to your Control Plane.

## FAQs

### **What container registries are supported by this feature?**

The feature supports a variety of container registries including AWS ECR, ACR (Azure Container Registry), GCR (Google Container Registry), Nexus, and Docker Hub.

### **What information is necessary for setting up the following container registries: ACR, GCR, Nexus, and Docker Hub?**

To configure Others (ACR, GCR, Nexus, Docker Hub), only the user name, password, and registry URL are required.