---
title: Container Registries
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
Facets provides support for multiple Container Registries, including **Elastic Container Registry, Azure Container Registry, Google Artifact Registry, Google Container Registry, Nexus, Docker Hub, Jfrog **and** others.**

**Note:** Users require '`ARTIFACTORY_WRITE`' and '`ARTIFACTORY_DELETE`' permissions to create, modify, or delete a Container Registry.

# How to Add a Container Registry?

1. Navigate to **Settings > Container Registries.** This page will display all the existing Registries. 
2. To add a new registry, select the type of registry you wish to add. 

***

## Elastic Container Registry

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Firqumhpv5kji&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Firqumhpv5kji&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_dc9b2d1d-2c0d-4039-9ae6-e9f4d68bfef8%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"449\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/irqumhpv5kji",
  "title": "Container Registries | Feb 17 12:38 PM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_dc9b2d1d-2c0d-4039-9ae6-e9f4d68bfef8/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/irqumhpv5kji",
  "typeOfEmbed": "jsfiddle"
}
[/block]


1. Select **Elastic Container Registry** from the **Add Container Registry** page.
2. Mention the **Registry Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **AWS Cloud Console** and click the **CloudShell** icon on the top bar.
5. In the [Cloud Shell](https://ap-south-1.console.aws.amazon.com/cloudshell/home?region=ap-south-1#e8a9b144-b70c-468d-be1e-fd0249123b16)terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

You have successfully added a new Elastic Container Registry to Facets. 

***

## Azure Container Registry

1. Select **Azure Container Registry** from the **Add Container Registry** page.
2. Mention the **Registry Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **Microsoft Azure Portal** and click the **Cloud Shell** icon on the top bar.
5. In the [Cloud Shell](https://portal.azure.com/#cloudshell/) terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

You have successfully added a new Azure Container Registry to Facets.

***

## Google Artifact Registry

1. Select **Google Artifact Registry** from the **Add Container Registry** page.
2. Mention the **Registry Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **GCP Cloud Console** and click the **Cloud Shell** icon on the top bar.
5. In the [Cloud Shell](https://console.cloud.google.com/welcome?project=facets-cp-test&cloudshell=true--) terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

You have successfully added a new Google Artifact Registry to Facets.

***

## Other Registries

1. Select the required registry from the options, including **Google Container Registry, Nexus, Docker Hub, JFrog, and others.**
2. Fill in the following mandatory fields:
   1. **Registry Name:** A unique name used to identify the registry in your Docker Build Configurations.
   2. **Registry URL:** The address where your registry is hosted and accessible.
   3. **Username:** The username associated with your registry account.
   4. **Password:** The password for your registry account.
3. Now, click **Create.**

You have successfully added a new Container Registry to Facets.

***

# Mapping Projects to your Container Registry(CR)

After successfully connecting your Container Registry, you can map it to specific projects. This mapping controls registry access across your projects.

1. Navigate to **Settings > Container Registries**. Find your registry in the list
2. Click on the 'Attach Projects' icon. Select projects to map
3. Click **Save** to apply changes

> Once the container registry is added, it can be **restricted to be used only in certain projects**. This can be done using one of the action buttons present in the table against that container registry. If not mapped to anything, it is available in all the projects.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5cbe5646aef87c093e828f9d52714c41d1ef1463c852ee7f4d594ff280bd3d0-Screenshot_2025-02-18_at_11.43.30_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]