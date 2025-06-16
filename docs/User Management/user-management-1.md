---
title: User Management
excerpt: How to add user roles, create user groups and assign permissions to your users
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

Facets provides the capability to do this using Role-based Access Control (RBAC). From your Control Plane, you can:

* Create and manage **Users** and assign them to specific User Groups.
* Create **Custom Roles** with unique permissions.
* Create **User Groups**, for predefined Roles or custom Roles and assign environment-specific permissions.

Facets also provides the capability to integrate your Control Plane with Google Workspace and give your users the ability to login directly using Google OAuth.\
Click here to know more about [Google OAuth Integration](https://readme.facets.cloud/docs/google-oauth-integration). 

## User Management Workflow

1. Facets provides you with some **System Defined Roles** and the ability to add **Custom Roles** with specific granular permissions.

<Image alt="System Defined Roles" align="center" width="500px" border={true} src="https://files.readme.io/1069f0a-image.png">
  System Defined Roles
</Image>

2. Administrators (Users with Admin access) can create **User Groups** that encompass **Roles** and can grant environment-specific permissions to **Users** in that User Group. 

> ❗️ NOTE
>
> All environments are accessible by default when creating a User Group. 
>
> If you want to allow access to limited environments only, then please select specific environments in the User Groups create/edit screen.

3. Admins can create/edit **Users** and add them to **User Groups**.

## Roles and Permissions

For more information on managing Roles and Permissions, refer to [Roles and Permissions in User Management](https://readme.facets.cloud/docs/roles-and-permissions).

## User Groups

For more information on creating or managing User Groups, refer to [User Groups](doc:user-groups).
