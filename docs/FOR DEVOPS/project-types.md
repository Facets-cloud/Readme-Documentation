---
title: Project Types
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
Imagine you're managing multiple projects with varying infrastructure needs. Instead of manually setting up base blueprint every time, Project Types lets you standardize and reuse existing base blueprint, ensuring faster setup, consistency, and fewer errors across your projects.

Think of it as taking your custom-configured project template for your custom use case and turning it into a reusable starting point for your team. Create a template once, reuse it forever.

## Overview

With Project Types, you can:

* Create standardised templates from existing projects or Git repositories.
* Control resources list for a Project.
* Automatically configure cloud provider settings for new projects.
* Maintain consistent project setups across teams and reduce manual configuration time.
* Track which templates are used by which projects.

**Prerequisites**\
Permission to edit Project Types and familiarity with your organization's project types and resource requirements.

***

## Creating Your First Project Type

1. Navigate to Ops Center.
2. Locate and click on the Project Type option.
3. This will take you to the Project Type Dashboard page, where you can:
   * View all existing project types.
   * See associated projects and respective creators.
   * Track which projects are using which Project Type.
   * Delete project types that are not linked to any existing projects.

Now to create a new Project Type:

1. Click on the Create Project Type button.
2. Fill in the following details:
   * **Name**: Enter a unique name for the project type.
   * **Description**: A brief description of the project type's purpose.
   * **Project Source**: Choose the source for the project type configuration. You have two ways to do it:
     * **Existing Project**: Select from a dropdown of existing projects. The respective Git configuration will be automatically imported from the selected project.
     * **Existing Project Type**: Select from a dropdown of existing project types. The respective Git configuration will be automatically imported from the underlying project of the selected project type.
     * **Custom Git Linking**: Configure the project type using a custom Git repository.
       * **Git Account**: Select the associated Git account.
       * **Git Repository URL**: Provide the repository’s URL.
       * **Git Ref**: Specify the exact commit ID or branch to be used.
       * **Relative Path**: Define the path to the project configuration within the repository.
   * **IAC Tool:** Choose the **IAC Tool and the IAC Tool Version** (All the projects made from this project type will have resources that are supported by the selected IAC tool).
   * **Allowed Clouds**: The cloud provider which will host your project.
3. After filling in the details, click **Create** to save the project type.

***

## Map Resources to Project Type

Post Project Type creation, you can define exactly which resources are mapped to respective project type, ensuring only selected resources are accessible within the resource list of the Project.

**Steps to Map Resources :**

1. Click **Manage Resources** to view all existing modules, including all published custom modules. The list will contain only resources that are supported by the IAC Tool that was selected while creating that project type.

> **Note:** By default, all resources are selected for a project type and Preview modules are not visible in this list.

2. Select or deselect intents and flavors according to requirements.
3. Save your configuration to apply changes.

**Example Use Case:**

Suppose you want to restrict the use of a specific MongoDB flavor, like Atlas, in projects tied to a particular project type. In that case you can navigate to the Project Types list screen, click on "Manage Resources" of the respective project type and uncheck the Atlas flavor under the MongoDB intent, save your changes, and you’re set.

Later, if that flavor is needed, you can always edit the resource list linked to that project type to re-include it.

### See It in Action

<HTMLBlock>{`
<div>
  <script async src="https://js.storylane.io/js/v2/storylane.js"></script>
  <div class="sl-embed" style="position:relative;padding-bottom:calc(54.03% + 25px);width:100%;height:0;transform:scale(1)">
    <iframe loading="lazy" class="sl-demo" src="https://app.storylane.io/demo/kcwmhync3cvt?embed=inline" name="sl-embed" allow="fullscreen" allowfullscreen style="position:absolute;top:0;left:0;width:100%!important;height:100%!important;border:1px solid rgba(63,95,172,0.35);box-shadow: 0px 0px 18px rgba(26, 19, 72, 0.15);border-radius:10px;box-sizing:border-box;"></iframe>
  </div>
</div>
`}</HTMLBlock>

***

## Using Project Types

Once project type is created, one can now

* While creating a new project, select a pre-configured project type from the dropdown menu during Create Project Flow. You can also see which resources are mapped to the respective project type by clicking on the "i" button next to it.
* The system will automatically populate the allowed cloud environments for the project based on the selected project type.
* Based on the chosen project type, the Allowed Clouds for the project will be auto-populated, ensuring compliance with the template's configurations which you can modify based on your Project Requirements.

***

### See it in Action :

<Embed url="https://app.storylane.io/demo/0efoota7qnbj" href="https://app.storylane.io/demo/0efoota7qnbj" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F0efoota7qnbj%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F0efoota7qnbj%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_1fea70b1-fe23-4c10-9216-2676583c69f2%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

No more manual setup. No more forgetting critical settings. Just consistent, reliable project creation every time

## Best Practices

* Use descriptive names for project types to easily identify their purpose.
* Maintain detailed descriptions for better team understanding.
* Remove unused project types to keep the system organized.

## FAQs

### Can I edit an existing Project Type?

Currently, project types cannot be edited. You can create a new project type or delete an existing one (if it’s not linked to any projects) and recreate it.

### Why I am unable to delete a Project Type?

Verify that no projects are currently using the project type. To unlink a project type from a Project you have to delete the very Project to begin with. Additionally, do check your administrative permissions.

### What is the purpose of the Git Ref field?

The Git Ref allows you to specify a particular commit ID or branch from the repository. This ensures that the correct version of the project files is used.

### Can I change a Project Type’s mapped resources later?

Yes, except for the default type—you can anytime come to Project Types and update instantly.

### Can I change linked Project Type after creation of a Project ?

Yes, you can change a project type which is linked to a Project at any given time.\
Steps : Project Settings -> Select desired Project Type from Dropdown -> Save

### What if a resource isn’t listed in My Project when it is there in Project Type?

The resources list within Project reflects allowed clouds and along with Project Type—check those settings if something’s missing.

## Support

For additional support or questions about Project Types, contact the Facets support team