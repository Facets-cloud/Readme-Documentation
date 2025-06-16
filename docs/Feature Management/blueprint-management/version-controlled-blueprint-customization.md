---
title: Version-Controlled Blueprint Customization
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
Manage and track changes to your Blueprints using your [version control systems.](https://readme.facets.cloud/docs/integrating-vcs-accounts) By creating a separate branch through the Facets Control Plane, you can make modifications and subsequently merge them back into the master branch via a pull request, thereby updating the Blueprint with the changes.

**Note:** This feature is available upon request. Contact Facets Support to enable this feature in your control plane.

### How to create a branch in the Git repository from the Facets Control Plane?

1. Open **Blueprints** and select the required Blueprint.
2. In the **Designer** tab, you'll see the Blueprint's Branches in the breadcrumb at the top of the screen.
3. Clicking on it will reveal a dropdown containing a list of the branches.
4. To create a new branch in the repository, click on **Add branch.**
5. In the pop-up, mention the **Branch Name** and click **Add.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/bb30fe1-image.png">
  Click on the image to expand
</Image>

You have successfully added a new branch to the Repository.

**Note:** You can **Sync with Git** to force synchronization between your Git repository and the Control Plane.

### How to select an existing branch?

1. In the **Designer** tab, click on the Blueprint's Branches in the breadcrumb at the top of the screen.
2. This will reveal a dropdown containing a list of the branches.
3. Search for the desired branch in the dropdown and select the branch.
4. Click **Apply.**

You have successfully selected a branch.

## FAQ

### 1\. Why should I use the Version-Controlled Blueprint Customization feature?

Using this feature enhances accountability in managing Blueprint changes. It allows you to keep track of all changes made, ensuring your Blueprint is always up-to-date.

### 2\. How can I access the Git branches in Facets?

The Git branches can be accessed from the breadcrumb in the Designer tab in Facets.

### 3\. How do I merge my changes into the master branch?

After making changes in your separate branch, you can raise a pull request to merge these changes into the master branch.
