---
title: User Groups
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
# Overview

- User Group is a structured collection of role and accessible entities designed to simplify the management of user roles and access. 
- When a User Group is assigned to a user, they automatically inherit the access and permissions associated with the group's default role and any environment-specific roles.
- Each User Group includes:
  - [ ] A default role (defining baseline permissions)
  - [ ] Accessible projects, environments, resource groups, and accounts
  - [ ] Optional environment-specific roles with granular permissions for individual environments

## Usecases:

1. **Team-Based Access:** Easily manage access for different teams (e.g., development, QA, operations) by creating separate User Groups with tailored permissions.
2. **Environment Control:** Provide varying access levels for the same users in different environments (e.g., full access in development, read-only in production).
3. **Resource Isolation:** Ensure users only access the projects, resources, and accounts they need, adhering to the principle of least privilege.
4. **Simplified Management:** Reduce administrative overhead by managing permissions at a group level rather than for individual users.

## Prerequisites:

1. Users must have the necessary permissions to manage user groups.
2. Roles and resource groups must be defined before they can be assigned to a user group.

<br />

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fdfa2n6t491lc&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fdfa2n6t491lc&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_4b86d5cc-aa9e-4e4d-aa68-3ea2f302a6a7%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"431\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/dfa2n6t491lc",
  "title": "Create User Group",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_4b86d5cc-aa9e-4e4d-aa68-3ea2f302a6a7/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/dfa2n6t491lc",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

# Default Role

- A Default Role defines the basic level of access granted to users been assigned a User Group. It applies to the entire Facets Control Plane and all clusters the user has access to.
- The default role applies across all accessible entities, unless overridden by an environment-specific role.
- It is used to set a baseline level of access that is common for all members of a user group, irrespective of their environment, hence it is a required field.

# Accessible Entities

User Groups define the specific entities their assigned users can access. Carefully configuring these entities ensures security, limits exposure, and maintains the principle of least privilege.

### 1. Projects

- A large organisation may have multiple projects specific to different teams. By creating specific User Groups for each project, you can ensure that developers, testers, and operations staff only access the resources that are relevant to their assigned project. 
- If no projects are selected, then all projects are accessible

### 2. Environments

- Environments like Development, Staging, and Production can be restricted per User Group, ensuring users only access what they need.
- This minimises risks associated with unauthorised access or unintended modifications in critical environments.
- If no environments are selected, then all environments within accessible projects are accessible.

### 3. Resource Groups

- Resource Groups enable fine-grained control over access to infrastructure components, ensuring teams manage only the resources relevant to their responsibilities.
- If no resource groups are selected, then all resources within accessible environments and projects are accessible.

### 4. Accounts

- To manage access across different cloud and version control accounts. 
- This ensures that users are limited to the specific accounts that are relevant to their roles and responsibilities.
- If no accounts are selected, then all accounts integrated within the control plane are accessible

> 📘 Important Considerations:
> 
> - If no selection is made in Projects, Environments, Accounts, or Resource Groups, the User Group will have access to all respective entities within the Facets Control Plane.
> - It is highly recommended to be explicit about which entities a User Group has access to, by always making a selection in each dropdown.

# Environment-specific Roles

Environment-specific roles allow you to override the Default Role and grant users distinct permissions for specific environments.

1. Customize user permissions for each environment to align with different security requirements or development workflows (e.g., developers may have read and write access in dev but only read in production).
2. Environment-specific roles take precedence over the default role. This means that if a user has a default role and an environment specific role, the environment specific role permissions will be applied when they access that environment.
3. When multiple user groups are assigned to a user, a user will have only one default role, that will be derived from the last assigned user group. Environment specific roles are assigned within the user group, they will override the default role when user accesses that environment.