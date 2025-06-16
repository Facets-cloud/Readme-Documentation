---
title: Creating a Project
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
## How to create a Project?

1. To create a new Project, navigate to the **Projects** tab and click **Create Project.**
2. In the modal that appears, mention 
   ## **1. Enter Project Name and Description**
   - Enter the **Project Name**  and an optional **Description**.  
   - The description will appear alongside the project name in the project cards on the project overview page.
   ***
   ## **2. Choose Git Account for Repository Creation**
   - Select a **Git Account** to create the repository for the project.  
   - The repository will store the project’s blueprint and Terraform modules, making them accessible outside the UI.  
   - If you haven’t created an account yet, follow [these steps](https://readme.facets.cloud/v1.4/docs/connect-your-git-accounts).  
   - You can also select a different organization account if you prefer not to use your personal account.
   ***
   ## 3. Choose Project Type
   - Select a **Project Type** to use a pre-configured blueprint template with the necessary settings for your project.  
   - You can also create custom project templates in the **Ops Center** for use in future projects. 
   ***
   ## **4. Select Allowed Cloud Provider**
   - Select the **Allowed Cloud** provider to determine the cloud environment where your project will be hosted.  
   - This selection filters the blueprint resources and applies default configurations, or "flavors," tailored to the chosen cloud provider.  
   ***
   ## **5. Select the Type of Environments**
   - Choose the type of **Environments** you want to create for your project (e.g., Development, Staging, Production).  
   - These environments will be created in the UI but must be launched to provision them in the cloud.

## 6. Click Create

- You have successfully created a new Project. This will be accessible from the Projects tab.

<br />

## Sample Product Demo

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fvuvjeaxkja0h&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fvuvjeaxkja0h&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_9f867cab-6bfd-48b1-9a2e-bedf5e7ebede%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"431\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/vuvjeaxkja0h",
  "title": "Create Project v4",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_9f867cab-6bfd-48b1-9a2e-bedf5e7ebede/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/vuvjeaxkja0h",
  "typeOfEmbed": "jsfiddle"
}
[/block]


sad