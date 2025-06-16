---
title: Creating Projects
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
   1. Select the **Allowed Cloud** provider to determine the cloud environment where your project will be hosted.  
   2. This selection filters the blueprint resources and applies default configurations, or "flavors," tailored to the chosen cloud provider. 
2. In the modal that appears, mention 
   1. **Enter Project Name and Description**
      - Enter the **Project Name**  and an optional **Description**.  
      - The description will appear alongside the project name in the project cards on the project overview page.
   2. **Choose Git Account for Repository Creation**
      - Select a **Git Account** to create the repository for the project.  
      - The repository will store the project’s blueprint and Terraform modules, making them accessible outside the UI.  
      - If you haven’t created an account yet, follow [these steps](<>).  
      - You can also select a different organization account if you prefer not to use your personal account.
   3. **Choose Project Type**
      - Select a **Project Type** to use a pre-configured blueprint template with the necessary settings for your project.  
      - You can also create custom project templates in the **Ops Center** for use in future projects.
   4. **Select Allowed Cloud Provider**
      - Select the Type of Environments
      - Choose the type of **Environments** you want to create for your project (e.g., Development, Staging, Production).  
      - These environments will be created in the UI but must be launched to provision them in the cloud.
   5. **Click Create**
      - You have successfully created a new Project. This will be accessible from the Projects tab.

***

## Settings specific to a Project

1. **Accessing Project Settings**: To access the project settings:  
   1. Open the **Projects** tab and select the relevant project.  
   2. Click the **Project Settings** tab, which contains the following sections: **General, GitOps, CI/CD,** and **Danger Zone**.
2. **General Settings:** In the **General** section, you can:  
   1. **Project Name**: View the uneditable project name.  
   2. **Description**: Edit the project summary.  
   3. **Allowed Clouds**: View the selected cloud service provider.  

**Note:** After making any changes, click **Save Changes** to apply them.

3. **GitOps Settings: **The **GitOps** section allows you to manage and modify the blueprint through your GitHub repository.
   1. **Key Options:**
      1. **Choose Account**: Displays the GitOps account added during project creation. 
      2. **Repository URL**: Displays the URL of the repository added during project setup. 
      3. **Branch**: Shows the branch containing the blueprint. 
      4. **Relative Path**: Displays the directory path containing the blueprint, relative to the repository URL.  
            **GitOps for Overrides:**

### Manage environment-specific configuration overrides directly from the Git repository.

- **Enabling GitOps for Overrides**: Once enabled, overrides are migrated to the Git repository, and you can no longer make changes through the UI.  
- **Restrict UI Changes**: When enabled, Git takes precedence, and any concurrent changes must be made from the repository. 
  - This setting is irreversible once activated. Ensure all overrides are properly migrated before enabling it.
  - After making any changes, click **Save Changes**.

4. **CI/CD Settings**: The **CI/CD** section allows you to automate your deployments by setting up rules and workflows:  
   **Deployment Options:**
   1. **Branch Per Environment**: Map each Git branch to its corresponding environment for efficient testing.  
   2. **Single Branch Promotion**: Link one branch to an environment and automatically promote changes to other environments.  
   3. **Advanced**: Create custom Git rules for mapping branches and setting up flexible promotion workflows.
5. **Danger Zone: **The **Danger Zone** section contains options for deleting the project:  
   1. Click **Delete**. 
   2. Type **Confirm** in the pop-up window.  
   3. Click **Delete** again to finalize the deletion.

***

## FAQs for Creating a Project

1. **Can I change the GitOps account after creating a project?**

**Answer:** Yes, you can change the GitOps account in the **Project Settings > GitOps** section. However, ensure that the new account has access to the correct repository and branch to avoid configuration errors. Verify that permissions are properly configured to prevent deployment failures.

***

2. **How can I ensure that overrides are properly migrated before enabling GitOps for Overrides?**

**Answer:** Before enabling **GitOps for Overrides**, follow these steps to ensure a smooth migration:  

1. Verify that all environment-specific configuration overrides are stored in the repository at the correct path.  
2. Double-check that the repository permissions allow write access.  
3. Test the environment after migration to confirm that the applied configurations match your expected setup.

**Important:** Once overrides are migrated and GitOps is enabled, changes can no longer be made via the UI.

***

3\.** What are the limitations of the "Restrict UI Changes" option?**

**Answer:** When **Restrict UI Changes** is enabled, all modifications must be performed through Git. This ensures configuration consistency but removes the ability to make quick changes through the Facets UI.  

Consider enabling this option only if your team follows strict version control workflows and is comfortable making all changes through version control systems.

***

4. **What’s the difference between "Single Branch Promotion" and "Branch Per Environment"?**

**Answer:**  

- **Branch Per Environment:** Each Git branch is mapped to a specific environment (e.g., the `dev` branch for the Development environment).  
- **Single Branch Promotion:** One branch is linked to multiple environments, and changes are automatically promoted from one environment to the next (e.g., from `staging` to `production`).  

**When to use:**  

- Choose **Single Branch Promotion** if you prefer a linear progression of changes through environments.  
- Choose **Branch Per Environment** if you want parallel testing across multiple branches/environments.