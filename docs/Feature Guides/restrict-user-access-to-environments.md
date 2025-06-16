---
title: Restricting User Access to Environments
excerpt: >-
  Learn how to set user access restrictions using role based access control for
  environments
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Access management for resources is a critical function for any organization. Proper access management helps you formalize who has access to what resources, and what they can do with those resources.

Facets provides the capability to do this with Role-based access Control (RBAC). Find more information about the different roles and permissions in [Managing Users](https://readme.facets.cloud/docs/user-management#rbac).

## Restrict User Access to Environments from your Control Plane

1. Login to your **Control Plane**.
2. Click on the **Settings** icon in your sidebar. This will open the **User Management** screen by default.
3. Find the user you want to restrict access to and click on the **Edit User** icon under the **Actions** column.

<Image alt="Edit User button (Click on the image to expand)" align="center" width="450px" src="https://files.readme.io/cd22eb1-edit_user_button.png">
  Edit User button (Click on the image to expand)
</Image>

4. Choose the environments using the tick box for which the user should have access to, by clicking on the **Restrict Access to Environments** dropdown.

<Image alt="Restrict Access to Environments (Click on the image to expand) " align="center" width="450px" src="https://files.readme.io/e86e003-restrict_access.png">
  Restrict Access to Environments (Click on the image to expand) 
</Image>

> 📘 NOTE:
>
> By default, all new users have access to all the environments based on their role.

5. Click on the **Update User** button. 

<Image alt="Update User button (Click on the image to expand)" align="center" width="450px" src="https://files.readme.io/c2fb914-update_user.png">
  Update User button (Click on the image to expand)
</Image>

6. The list of environments the user has access to will now be visible to you from the **User Management** screen.

<Image alt="Restricted Environment access to User (Click on the image to expand)" align="center" width="450px" src="https://files.readme.io/9f3b1c1-final_view.png">
  Restricted Environment access to User (Click on the image to expand)
</Image>
