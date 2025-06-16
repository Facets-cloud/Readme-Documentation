---
title: GitOps for Overrides
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
The GitOps feature in Facets allows you to manage resource overrides directly through your Git repositories. You can make overrides through both the UI and the Git repository, and they will automatically sync with each other. In this guide, you will learn how to enable and use the GitOps feature.

**Note:** Once the GitOps for Overrides feature is enabled, it cannot be disabled or reverted.

### Why Use GitOps for Overrides?

1. Centralized Management: GitOps consolidates all resource override configurations in a single repository, ensuring consistency and traceability across environments.
2. Version Control: Every change made to the resource configurations is versioned, enabling easy rollback and auditability.
3. Collaboration: By leveraging Git, teams can collaboratively review, approve, and merge changes before applying them, enhancing the governance process.
4. Synchronization: Facets ensures continuous synchronization between the UI and Git, providing a unified view of the resource configurations.
5. Scalability: For large projects with multiple environments, GitOps simplifies managing overrides across teams and projects by maintaining structured configurations in Git.

## How to configure GitOps for Overrides?

1. Open **Projects** and select the project where you want to configure GitOps.
2. Go to the **Project Settings** tab and select the **GitOps** tab.
3. Enable the **Gitops for Overrides.**
4. For **Repository Setup**, choose between creating a new repository or using an existing one:
   1. If you choose to **Create a new repository,** enter your VCS **Organization Name.**
   2. If you choose to **Use an existing repository,** provide the **Overrides Repository URL** and the **Overrides Branch.**
5. Decide whether you want to enable **Restrict Changes from UI.**
6. Click **Save Changes.**

> 📘
>
> * Once you click **Save Changes,** the migration process will begin.
> * The migration can take some time to complete. During this period, please refrain from making any overrides.
> * You can monitor the migration status directly in the UI. If the migration fails, you will need to configure it again

You have successfully configured GitOps for Overrides. All existing override data has been migrated to your specified repository, and any future overrides will be saved there automatically.

## What happens when you restrict users from making changes via the UI?

When the Restrict Changes from UI feature is enabled in Facets, it imposes limitations on user interactions within the user interface. Here’s a detailed breakdown of the implications:

1. Users will be unable to make direct modifications from the Facets UI. This includes:
   1. Enabling or Disabling Resources
   2. Overriding Resources
   3. Attaching Images
   4. Domain Mapping for Ingress resources\
      All related buttons and options within the UI will be disabled, preventing any direct changes.
2. Users will need to use Git to override resources. An **Edit from Git** button will be provided, directing users to the relevant Git repository for making updates.
   1. **For Previously Overridden Resources:** Clicking the **Edit from Git** button will navigate users to the specific resource JSON file within the Git repository.
   2. **For New Overrides:** If it’s the first time an override is being made for a resource, the Edit with Git button will guide users to the repository. Here’s how to proceed:
      1. Create a JSON resource file named according to the resource specified in the UI, following this directory structure:
         ```Text Structure
         blueprint_name>/<environment_name>/<resource-type>/instances/<resource-name>.json
         ```
         ```Text Example
         infra-dev/stage/services/instances/springboot.json
         ```
   3. After creating the file, specify the necessary overrides within the JSON. Save the changes to Git, and they will automatically sync with the Facets UI.
3. Facets will continuously synchronize with Git, ensuring that any updates made in Git are promptly reflected in the resources in Facets.

By enabling the Restrict Changes from UI feature, you streamline and centralize resource management through Git, promoting a more controlled and auditable change process.

***

## FAQs

1. What if the migration process fails?\
   If the migration fails, you can reconfigure GitOps in the project settings. Monitor the migration status in the UI for detailed error information.
