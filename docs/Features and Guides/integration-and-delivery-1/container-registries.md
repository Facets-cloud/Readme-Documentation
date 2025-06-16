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
Facets now provides support for multiple Container Registries, including **Elastic Container Registry, Azure Container Registry, Google Artifact Registry, Google Container Registry, Nexus, Docker Hub, Jfrog** and **others.**

**Note:** Users require '`ARTIFACTORY_WRITE`' and '`ARTIFACTORY_DELETE`' permissions to create, modify, or delete a Container Registry.

## How to Add a Container Registry?

1. Navigate to **Settings > Container Registries.** This page will display all the existing Registries. 
2. To add a new registry, select the type of registry you wish to add. 

### Elastic Container Registry

1. Select **Elastic Container Registry** from the **Add Container Registry** page.
2. Mention the **Registry Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **AWS Cloud Console** and click the **CloudShell** icon on the top bar.
5. In the [Cloud Shell](https://ap-south-1.console.aws.amazon.com/cloudshell/home?region=ap-south-1#e8a9b144-b70c-468d-be1e-fd0249123b16) terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

You have successfully added a new Elastic Container Registry to Facets.

### Azure Container Registry

1. Select **Azure Container Registry** from the **Add Container Registry** page.
2. Mention the **Registry Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **Microsoft Azure Portal** and click the **Cloud Shell** icon on the top bar.
5. In the [Cloud Shell](https://portal.azure.com/#cloudshell/) terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

You have successfully added a new Azure Container Registry to Facets.

### Google Artifact Registry

1. Select **Google Artifact Registry** from the **Add Container Registry** page.
2. Mention the **Registry Name** and click **Next.**
3. Copy the command that is generated in the modal.
4. Open the **GCP Cloud Console** and click the **Cloud Shell** icon on the top bar.
5. In the [Cloud Shell](https://console.cloud.google.com/welcome?project=facets-cp-test\&cloudshell=true--) terminal, execute the command.
6. Facets will automatically detect if the connection has been successfully established.

You have successfully added a new Google Artifact Registry to Facets.

### Other Registries

1. Select the required registry from the options, including **Google Container Registry, Nexus, Docker Hub, JFrog, and others.**
2. Fill in the following mandatory fields:
   1. **Registry Name:** A unique name used to identify the registry in your Docker Build Configurations.
   2. **Registry URL:** The address where your registry is hosted and accessible.
   3. **Username:** The username associated with your registry account.
   4. **Password:** The password for your registry account.
3. Now, click **Create.**

You have successfully added a new Container Registry to Facets.

# Mapping Projects to your Container Registry(CR)

After successfully connecting your Container Registry, you can map it to specific projects. This mapping controls registry access across your projects.

## During Container Registry Creation

After linking your container registry, you can:

1. Select projects where you want the registry to be available in.
2. Click **Save** to map the registry to selected projects.
3. Click **Skip** to configure project mapping later.

## Edit Project Access For Registries

You can always edit registry-project mappings, here's how:

1. Navigate to **Settings > Container Registries**
2. Find your registry in the list
3. Click on the 'attach projects' icon
4. Select projects to map
5. Click **Save** to apply changes

**Note:** If mapping Container Registries to your Projects is enforced at the organization level, it is mandatory that you map registries to at least one project while creating them. You can enforce the mapping of Container Registries to your Projects by navigating to **Settings -> General** and enabling the option.

### Interactive Walkthrough

Here's an Interactive demo showing the step-by-step Container Registry creation process:

<Embed url="https://app.storylane.io/demo/fgqgaq7gzag9" title="Container Registries | Dec 20 4:27 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_01e72f7e-077f-4dfb-ab26-6cfdf9e1c103/project/project_4d01627c-6ec4-4285-bf45-e8f7f44d0e6e/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/fgqgaq7gzag9" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ffgqgaq7gzag9%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ffgqgaq7gzag9%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_01e72f7e-077f-4dfb-ab26-6cfdf9e1c103%252Fproject%252Fproject_4d01627c-6ec4-4285-bf45-e8f7f44d0e6e%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
