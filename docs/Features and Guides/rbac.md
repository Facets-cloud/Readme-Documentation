---
title: RBAC
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: users
      title: Users
    - type: basic
      slug: user-roles
      title: User Roles
    - type: basic
      slug: user-groups
      title: User Groups
    - type: basic
      slug: resource-groups
      title: Resource Groups
---
Facets provides a comprehensive user management system that allows for precise control over access to resources using Role-Based Access Control (RBAC). The user management system in Facets enables users to create roles, resource groups, and user groups, and then assign theses user groups to users. The general user flow is to first create roles and resource groups, then create user groups, and finally assign users groups to the users.

## Concepts

* **User Management**: User Management in Facets, found within Organization Settings, is a system that formalizes access control to Projects, Environments and resources. Key capabilities include creating and editing Users, User Groups, Custom Roles and Resource Groups.

* **[Permissions](https://readme.facets.cloud/docs/user-management-permissions-1)**: Permissions are specific rights that allow users to perform certain actions within Control Plane, such as creating or editing accounts, configuring alerts, or managing resources. They serve as the fundamental building blocks of the RBAC system.

* **[Roles](https://readme.facets.cloud/docs/user-roles)**: Roles define a set of permissions that grant users the ability to perform certain actions within Control Plane. There are predefined system roles as well as the ability to create custom roles. Custom roles allow administrators to define unique sets of permissions, enabling granular control over access to resources and actions.

* **[Resource Groups](https://readme.facets.cloud/docs/resource-groups)**: Resource Groups offer a structured approach to organizing and managing related resources, such as services, databases, and caches. By aligning Resource Groups with team or project structures, organizations can simplify resource management and enhance access control.

* **[User Groups](https://readme.facets.cloud/docs/user-groups)**: User Groups in Facets are designed to streamline the assignment of roles and access to users. A User Group encompasses a default role, accessible projects, environments, resource groups, and accounts. Users can assign environment-specific roles within a User Group, each with distinct permissions. When a user group is assigned to a user, they automatically inherit the access and the permissions associated with the group's default role and any environment-specific roles. Multiple User Groups can be assigned to a single user, and in cases where role conflicts arise, the role from the most recently assigned User Group takes precedence.

* **[User](https://readme.facets.cloud/docs/users)**: Individual accounts within Control Plane that can be assigned User Groups, inheriting the associated access to perform actions within the platform.

* **[Environment-specific roles](https://readme.facets.cloud/docs/user-groups#environment-specific-roles)**: The assignment of roles that are specific to certain environments is possible, providing flexibility in access control across different stages such as development, staging, and production. Environment-specific permissions take precedence over the User Group's default role for that particular environment.

* **[Access Analyser](https://readme.facets.cloud/docs/user-roles#access-analyser)**: A tool that helps administrators review and analyze user access and permissions, ensuring that the RBAC configurations align with organizational policies and security requirements.

***

## Use Cases

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Facets Use Cases</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
      
        .container {
            max-width: 1000px;
            margin: 0 auto;
        }

        h1 {
            color: #2c3e50;
            margin-bottom: 20px;
            font-size: 1.2em;
        }

        .cases-container {
            display: flex;
            justify-content: space-between;
            gap: 20px;
            position: relative;
        }

        .case {
            flex: 1;
            background: white;
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 3px 6px rgba(0,0,0,0.1);
            text-align: center;
            transition: transform 0.2s;
        }

        .case:hover {
            transform: translateY(-5px);
        }

        .team-size {
            font-size: 0.8em;
            color: #666;
            margin-bottom: 10px;
        }

        .icon-container {
            margin: 15px 0;
            display: flex;
            justify-content: center;
            gap: 25px;
        }

        .icon-group {
            text-align: center;
        }

        i {
            font-size: 1.5em;
            margin-bottom: 8px;
        }

        .small i { color: #2196F3; }
        .medium i { color: #1976D2; }
        .large i { color: #0D47A1; }

        .icon-label {
            font-size: 0.7em;
            color: #666;
        }

        .case-title {
            color: #2c3e50;
            font-size: 1em;
            font-weight: bold;
            margin: 15px 0;
        }

        .small .case-title { color: #2196F3; }
        .medium .case-title { color: #1976D2; }
        .large .case-title { color: #0D47A1; }

        @media (max-width: 768px) {
            .cases-container {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        
        <div class="cases-container">
            <div class="case small">
                <div class="team-size">2-10 members</div>
                <div class="case-title">Small Teams</div>
                <div class="icon-container">
                    <div class="icon-group">
                        <i class="fas fa-users"></i>
                        <div class="icon-label">Admin, Dev, Tester</div>
                    </div>
                    <div class="icon-group">
                        <i class="fas fa-folder"></i>
                        <div class="icon-label">Single Project</div>
                    </div>
                </div>
            </div>

            <div class="case medium">
                <div class="team-size">10-50 members</div>
                <div class="case-title">Growing Teams</div>
                <div class="icon-container">
                    <div class="icon-group">
                        <i class="fas fa-user-tag"></i>
                        <div class="icon-label">Custom Roles</div>
                    </div>
                    <div class="icon-group">
                        <i class="fas fa-project-diagram"></i>
                        <div class="icon-label">Multiple Projects</div>
                    </div>
                    <div class="icon-group">
                        <i class="fas fa-layer-group"></i>
                        <div class="icon-label">Resource Groups</div>
                    </div>
                </div>
            </div>

            <div class="case large">
                <div class="team-size">50+ members</div>
                <div class="case-title">Large Organizations</div>
                <div class="icon-container">
                    <div class="icon-group">
                        <i class="fas fa-user-shield"></i>
                        <div class="icon-label">SSO Integration</div>
                    </div>
                    <div class="icon-group">
                        <i class="fas fa-sitemap"></i>
                        <div class="icon-label">Team Hierarchy</div>
                    </div>
                    <div class="icon-group">
                        <i class="fas fa-lock"></i>
                        <div class="icon-label">Granular Access</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</html> 
`}</HTMLBlock>

* **Small Teams with Few Projects**: A simpler setup with fewer roles and resource groups might suffice. For example, create roles such as "Developer," "Tester," and "Admin," and group resources by project. Then create user groups that combine these roles with access to specific projects.

* **Growing Teams with Multiple Projects**: As the number of users and projects grows, a more structured approach is required. Start by creating more specific roles based on the tasks to be performed. Organize resources by project and environment, and create user groups that combine specific roles with access to the correct resource groups.

* **Large Organizations with Multiple Teams and Projects**: A granular approach is needed. Create a wide range of custom roles and resource groups based on team, application, or environment. Use user groups to manage access at the team level, ensuring each team can only access the resources they require. Use OAuth integrations with leading identity providers such as Google OAuth, Azure AD, OneLogin, Okta, and JumpCloud to simplify user access and enhance security.

***

## User Flow: Setting Up Access Control in Facets

Facets' Role-Based Access Control (RBAC) system ensures structured and secure user access management. Follow these steps to configure access control effectively:  

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Facets Access Control Flow</title>
    <style>
     
        .container {
            max-width: 900px;
            margin: 0 auto;
        }

        h1 {
            color: #2c3e50;
            margin-bottom: 20px;
            font-size: 1.2em;
        }

        .flow-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            padding: 10px;
        }

        .step {
            background: white;
            border-radius: 6px;
            padding: 10px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            min-width: 140px;
            position: relative;
            text-align: center;
        }

        .step-number {
            background: #3498db;
            color: white;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 0.8em;
            margin: 0 auto 5px;
        }

        .step h3 {
            color: #3498db;
            margin: 0;
            font-size: 0.9em;
        }

        .step-content {
            color: #666;
            font-size: 0.75em;
            margin-top: 5px;
        }

        .arrow {
            color: #3498db;
            font-size: 18px;
            display: flex;
            align-items: center;
        }

        @media (max-width: 768px) {
            .flow-container {
                flex-direction: column;
                gap: 10px;
            }

            .arrow {
                transform: rotate(90deg);
            }
        }
    </style>
</head>
    <div class="container">
        
        <div class="flow-container">
            <div class="step">
                <div class="step-number">1</div>
                <h3>Define Roles</h3>
                <div class="step-content">Create custom roles with specific permissions</div>
            </div>

            <div class="arrow">→</div>

            <div class="step">
                <div class="step-number">2</div>
                <h3>Resource Groups</h3>
                <div class="step-content">Organize resources by teams/projects</div>
            </div>

            <div class="arrow">→</div>

            <div class="step">
                <div class="step-number">3</div>
                <h3>User Groups</h3>
                <div class="step-content">Set up groups with roles and access</div>
            </div>

            <div class="arrow">→</div>

            <div class="step">
                <div class="step-number">4</div>
                <h3>Users</h3>
                <div class="step-content">Assign User Group(s) to user.</div>
            </div>
        </div>
    </div>
</html> 
`}</HTMLBlock>

1. **Define Custom Roles (if needed)** – Create roles with specific permissions that determine what actions users can perform, such as creating, editing, or deleting resources, performing releases, or viewing logs.  

2. **Organize Resources into Resource Groups** – Group related resources (e.g., databases, caches, services) based on teams, projects, or functions to simplify permission management and ensure structured access control.  

3. **Create User Groups and Assign Access** – Set up **User Groups** that include a **default role** and **environment-specific roles**. Assign access to **Projects, Environments, Resource Groups, and Accounts** within the group. 

4. **Assign Users Groups to Users** – Users inherit access and permissions based on their assigned User Groups.

### Example Scenario

A **DevOps Team** needs access to manage deployments. The administrator:  

* Creates a **"Deployment Manager"** role with permissions to deploy releases and view logs.  
* Groups all relevant resources under the **"E-commerce Backend"** resource group.  
* Sets up a **"DevOps Team"** user group with **Deployment Manager** as the default role and a **Viewer** role for the production environment.  
* Assigns the **DevOps Team** user group to new engineers, automatically granting them the required access.  

By following this structured approach, organizations can enforce security policies while ensuring efficient access management.

***

## Best Practices:

* **Start Simple and Iterate**: Begin with a basic structure and refine it based on user feedback and evolving needs. Avoid overcomplicating things at the beginning.
* **Follow a Naming Convention**: Use clear and consistent naming conventions for roles, resource groups, and user groups to simplify understanding and management.
* **Document Everything**: Maintain clear documentation of all roles, resource groups, and user groups, along with their associated permissions and users. Ensure this documentation is version-controlled.
* **Regularly Review Access**: Conduct periodic reviews of access permissions to ensure users have the appropriate level of access. Remove users from groups if they no longer need access.
* **Utilize Resource Groups**: Leverage resource groups to align with the organization's structure and facilitate resource and permission management.
* **Principle of Least Privilege**: Grant users only the necessary permissions to perform their duties.
* **Centralized Management**: Use the Facets Control Plane as a centralized control center for managing all infrastructure and application access.
* **Automate Where Possible**: Utilize the Facets APIs to automate user management tasks, reducing manual effort and minimizing errors.

***

## FAQs

* **Can I restrict access to specific environments or projects?** Yes, you can select the specific environments or projects in the accessible environment and accessible dropdown in the user group. This will restrict your access to the selected entities.
* **Can I assign multiple roles to a user?** No, a user is assigned a default role derived from user groups. However, you can assign environment specific role within a user group to have distinct set of permissions
* **Can multiple user groups be assigned to a user group?** Yes, a user can be assigned multiple user groups, inheriting access from all of them and default role from the latest assigned user group.
