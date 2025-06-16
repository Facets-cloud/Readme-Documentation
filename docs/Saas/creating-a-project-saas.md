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
   1. Enter the **Project Name** (mandatory) and **Description.**
   2. Select the **Primary Cloud** provider (mandatory). This determines the default configurations, or 'flavors' while adding resources to the Blueprint.
   3. Select the type of **Environment(s)** you would like to create in your project.
3. Click **Create.**

You have successfully created a new Project. This will be accessible from the Projects tab.

## What are the settings specific to a Project?

1. To access these settings, open the **Projects** tab and choose the relevant project. 
2. From here, select the **Project Settings** tab. This tab contains three tabs: **General, GitOps,** and **Danger Zone.**
3. In the **General** section, you will find:
   1. **Project Name** (uneditable)
   2. **Description:** You can alter the project's summary here.
   3. **Primary Cloud:** Shows the selected cloud service provider.
   4. After making any changes, click **Save Changes** to implement them.
4. The **GitOps,** when configured, allows modifications in the Blueprint via your GitHub repository. Here, you will find the following options:
   1. **Choose Account:** Select the GitOps account you prefer.
   2. **Repository URL:** Specify the location of your repository.
   3. **Branch:** Identify the branch that carries the desired Blueprint.
   4. **Relative Path:** Denotes the directory containing the Blueprint definition in relation to the repository URL.
   5. After making any changes, click **Save Changes.**
5. The **CI/CD tab** allows you to automate your deployment by creating tailored rules and workflows for your development process. Choose between **Branch Per Environment, Single Branch Promotion** or **Advanced.**
6. The **Danger Zone** section provides the option to delete the project. To do so:
   1. Click **Delete.**
   2. A pop-up will appear asking you to confirm the project name. 
   3. Enter the name and click **Delete.**

By understanding and effectively utilizing these settings, you can successfully manage and control your projects Facets.

## FAQ

### 1. Can I edit the name of my project?

No, the Project Name field is not editable once the project has been created.

### 2. What is the "Enable GitOps" feature in my project settings?

The "Enable GitOps" feature lets you adjust your project's Blueprint directly from your GitHub repository. When you turn this feature on, you can choose your GitOps account, specify your repository, and select the branch for your Blueprint.

### 3. How do I delete a project?

i. To delete a project, go to the **Settings** tab of your project and navigate to the **Danger Zone** section. 

ii. Click **Delete.**

iii. A pop-up will appear asking you to confirm the project name. After entering the name, click **Delete** to remove the project.
