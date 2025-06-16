---
title: Creating a User Group
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
## How to Create a User Group?

This guide will walk you through the process of creating and managing a User Group.

1. Navigate to **Settings > User Management.**
2. Select the **User Groups** tab. Here, on this page, you will find all the User Groups available in Facets.
3. Click **Create User Group.**
4. In the page that appears, mention the **Group Name **(mandatory).
5. Select the **Default Role**(mandatory), ** Accessible Environments** and **Accessible Accounts.**

> 📘 
> 
> If no **Accessible Environments** are selected, the users in this group will have access to all the environments.

6. Under **Env-specific permissions,** select the required environment and choose the role you wish to assign to that environment. Click **Add Permissions.**

> 📘 
> 
> - **Env-specific permissions** will take precedence over the user group's default role. 
> - In **Env-specific permissions,** you will only be able to select the environments added under **Accessible Environments**  
>   If no **Accessible Environments** are selected, you will be able to select from all the available environments.

7. Select the **Accessible Resource Groups.**

> 📘 
> 
> Selecting **Accessible Resource groups** ensures that the users within this group can only access the  resorce in those specified resource groups.

7. Click **Create.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a610995-image.png",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


You have successfully created a user group.

## Related Guide

- [Creating a User](doc:creating-a-user)
- [Creating Custom Roles](doc:custom-roles)