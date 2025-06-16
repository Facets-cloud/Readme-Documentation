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
---
Facets provides a comprehensive user management system that allows for precise control over access to resources using Role-Based Access Control (RBAC). The user management system in Facets enables users to create roles, resource groups, and user groups, and then assign theses user groups to users. The general user flow is to first create roles and resource groups, then create user groups, and finally assign users groups to the users.

## Concepts

- **User Management**: User Management in Facets, found within Organization Settings, is a system that formalizes access control to Projects, Environments and resources. Key capabilities include creating and editing Users, User Groups, Custom Roles and Resource Groups.

- **Permissions**: Permissions are specific rights that allow users to perform certain actions within Control Plane, such as creating or editing accounts, configuring alerts, or managing resources. They serve as the fundamental building blocks of the RBAC system.

- **Roles**: Roles define a set of permissions that grant users the ability to perform certain actions within Control Plane. There are predefined system roles as well as the ability to create custom roles. Custom roles allow administrators to define unique sets of permissions, enabling granular control over access to resources and actions.

- **Resource Groups**: Resource Groups offer a structured approach to organizing and managing related resources, such as services, databases, and caches. By aligning Resource Groups with team or project structures, organizations can simplify resource management and enhance access control.

- **User Groups**: User Groups in Facets are designed to streamline the assignment of roles and access to users. A User Group encompasses a default role, accessible projects, environments, resource groups, and accounts. Users can assign environment-specific roles within a User Group, each with distinct permissions. When a user group is assigned to a user, they automatically inherit the access and the permissions associated with the group's default role and any environment-specific roles. Multiple User Groups can be assigned to a single user, and in cases where role conflicts arise, the role from the most recently assigned User Group takes precedence.

- **User**: Individual accounts within Control Plane that can be assigned User Groups, inheriting the associated access to perform actions within the platform.

- **Environment-specific roles**: The assignment of roles that are specific to certain environments is possible, providing flexibility in access control across different stages such as development, staging, and production. Environment-specific permissions take precedence over the User Group's default role for that particular environment.

- **Access Analyser**: A tool that helps administrators review and analyze user access and permissions, ensuring that the RBAC configurations align with organizational policies and security requirements.

***

## Use Cases

[block:html]
{
  "html": "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Facets Use Cases</title>\n    <link rel=\"stylesheet\" href=\"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css\">\n    <style>\n      \n        .container {\n            max-width: 1000px;\n            margin: 0 auto;\n        }\n\n        h1 {\n            color: #2c3e50;\n            margin-bottom: 20px;\n            font-size: 1.2em;\n        }\n\n        .cases-container {\n            display: flex;\n            justify-content: space-between;\n            gap: 20px;\n            position: relative;\n        }\n\n        .case {\n            flex: 1;\n            background: white;\n            border-radius: 8px;\n            padding: 15px;\n            box-shadow: 0 3px 6px rgba(0,0,0,0.1);\n            text-align: center;\n            transition: transform 0.2s;\n        }\n\n        .case:hover {\n            transform: translateY(-5px);\n        }\n\n        .team-size {\n            font-size: 0.8em;\n            color: #666;\n            margin-bottom: 10px;\n        }\n\n        .icon-container {\n            margin: 15px 0;\n            display: flex;\n            justify-content: center;\n            gap: 25px;\n        }\n\n        .icon-group {\n            text-align: center;\n        }\n\n        i {\n            font-size: 1.5em;\n            margin-bottom: 8px;\n        }\n\n        .small i { color: #2196F3; }\n        .medium i { color: #1976D2; }\n        .large i { color: #0D47A1; }\n\n        .icon-label {\n            font-size: 0.7em;\n            color: #666;\n        }\n\n        .case-title {\n            color: #2c3e50;\n            font-size: 1em;\n            font-weight: bold;\n            margin: 15px 0;\n        }\n\n        .small .case-title { color: #2196F3; }\n        .medium .case-title { color: #1976D2; }\n        .large .case-title { color: #0D47A1; }\n\n        @media (max-width: 768px) {\n            .cases-container {\n                flex-direction: column;\n            }\n        }\n    </style>\n</head>\n<body>\n    <div class=\"container\">\n        \n        <div class=\"cases-container\">\n            <div class=\"case small\">\n                <div class=\"team-size\">2-10 members</div>\n                <div class=\"case-title\">Small Teams</div>\n                <div class=\"icon-container\">\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-users\"></i>\n                        <div class=\"icon-label\">Admin, Dev, Tester</div>\n                    </div>\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-folder\"></i>\n                        <div class=\"icon-label\">Single Project</div>\n                    </div>\n                </div>\n            </div>\n\n            <div class=\"case medium\">\n                <div class=\"team-size\">10-50 members</div>\n                <div class=\"case-title\">Growing Teams</div>\n                <div class=\"icon-container\">\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-user-tag\"></i>\n                        <div class=\"icon-label\">Custom Roles</div>\n                    </div>\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-project-diagram\"></i>\n                        <div class=\"icon-label\">Multiple Projects</div>\n                    </div>\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-layer-group\"></i>\n                        <div class=\"icon-label\">Resource Groups</div>\n                    </div>\n                </div>\n            </div>\n\n            <div class=\"case large\">\n                <div class=\"team-size\">50+ members</div>\n                <div class=\"case-title\">Large Organizations</div>\n                <div class=\"icon-container\">\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-user-shield\"></i>\n                        <div class=\"icon-label\">SSO Integration</div>\n                    </div>\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-sitemap\"></i>\n                        <div class=\"icon-label\">Team Hierarchy</div>\n                    </div>\n                    <div class=\"icon-group\">\n                        <i class=\"fas fa-lock\"></i>\n                        <div class=\"icon-label\">Granular Access</div>\n                    </div>\n                </div>\n            </div>\n        </div>\n    </div>\n</html> "
}
[/block]




- **Small Teams with Few Projects**: A simpler setup with fewer roles and resource groups might suffice. For example, create roles such as "Developer," "Tester," and "Admin," and group resources by project. Then create user groups that combine these roles with access to specific projects.

- **Growing Teams with Multiple Projects**: As the number of users and projects grows, a more structured approach is required. Start by creating more specific roles based on the tasks to be performed. Organize resources by project and environment, and create user groups that combine specific roles with access to the correct resource groups.

- **Large Organizations with Multiple Teams and Projects**: A granular approach is needed. Create a wide range of custom roles and resource groups based on team, application, or environment. Use user groups to manage access at the team level, ensuring each team can only access the resources they require. Use OAuth integrations with leading identity providers such as Google OAuth, Azure AD, OneLogin, Okta, and JumpCloud to simplify user access and enhance security.



***

## User Flow: Setting Up Access Control in Facets

Facets' Role-Based Access Control (RBAC) system ensures structured and secure user access management. Follow these steps to configure access control effectively:  

[block:html]
{
  "html": "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Facets Access Control Flow</title>\n    <style>\n     \n        .container {\n            max-width: 900px;\n            margin: 0 auto;\n        }\n\n        h1 {\n            color: #2c3e50;\n            margin-bottom: 20px;\n            font-size: 1.2em;\n        }\n\n        .flow-container {\n            display: flex;\n            justify-content: center;\n            align-items: center;\n            gap: 15px;\n            padding: 10px;\n        }\n\n        .step {\n            background: white;\n            border-radius: 6px;\n            padding: 10px;\n            box-shadow: 0 2px 4px rgba(0,0,0,0.1);\n            min-width: 140px;\n            position: relative;\n            text-align: center;\n        }\n\n        .step-number {\n            background: #3498db;\n            color: white;\n            width: 20px;\n            height: 20px;\n            border-radius: 50%;\n            display: flex;\n            align-items: center;\n            justify-content: center;\n            font-weight: bold;\n            font-size: 0.8em;\n            margin: 0 auto 5px;\n        }\n\n        .step h3 {\n            color: #3498db;\n            margin: 0;\n            font-size: 0.9em;\n        }\n\n        .step-content {\n            color: #666;\n            font-size: 0.75em;\n            margin-top: 5px;\n        }\n\n        .arrow {\n            color: #3498db;\n            font-size: 18px;\n            display: flex;\n            align-items: center;\n        }\n\n        @media (max-width: 768px) {\n            .flow-container {\n                flex-direction: column;\n                gap: 10px;\n            }\n\n            .arrow {\n                transform: rotate(90deg);\n            }\n        }\n    </style>\n</head>\n    <div class=\"container\">\n        \n        <div class=\"flow-container\">\n            <div class=\"step\">\n                <div class=\"step-number\">1</div>\n                <h3>Define Roles</h3>\n                <div class=\"step-content\">Create custom roles with specific permissions</div>\n            </div>\n\n            <div class=\"arrow\">→</div>\n\n            <div class=\"step\">\n                <div class=\"step-number\">2</div>\n                <h3>Resource Groups</h3>\n                <div class=\"step-content\">Organize resources by teams/projects</div>\n            </div>\n\n            <div class=\"arrow\">→</div>\n\n            <div class=\"step\">\n                <div class=\"step-number\">3</div>\n                <h3>User Groups</h3>\n                <div class=\"step-content\">Set up groups with roles and access</div>\n            </div>\n\n            <div class=\"arrow\">→</div>\n\n            <div class=\"step\">\n                <div class=\"step-number\">4</div>\n                <h3>Users</h3>\n                <div class=\"step-content\">Assign User Group(s) to user.</div>\n            </div>\n        </div>\n    </div>\n</html> "
}
[/block]


1. **Define Custom Roles (if needed)** – Create roles with specific permissions that determine what actions users can perform, such as creating, editing, or deleting resources, performing releases, or viewing logs.  

2. **Organize Resources into Resource Groups** – Group related resources (e.g., databases, caches, services) based on teams, projects, or functions to simplify permission management and ensure structured access control.  

3. **Create User Groups and Assign Access** – Set up **User Groups** that include a **default role** and **environment-specific roles**. Assign access to **Projects, Environments, Resource Groups, and Accounts** within the group. 

4. **Assign Users Groups to Users** – Users inherit access and permissions based on their assigned User Groups.



### Example Scenario

A **DevOps Team** needs access to manage deployments. The administrator:  

- Creates a **"Deployment Manager"** role with permissions to deploy releases and view logs.  
- Groups all relevant resources under the **"E-commerce Backend"** resource group.  
- Sets up a **"DevOps Team"** user group with **Deployment Manager** as the default role and a **Viewer** role for the production environment.  
- Assigns the **DevOps Team** user group to new engineers, automatically granting them the required access.  

By following this structured approach, organizations can enforce security policies while ensuring efficient access management.

***

## Best Practices:

- **Start Simple and Iterate**: Begin with a basic structure and refine it based on user feedback and evolving needs. Avoid overcomplicating things at the beginning.
- **Follow a Naming Convention**: Use clear and consistent naming conventions for roles, resource groups, and user groups to simplify understanding and management.
- **Document Everything**: Maintain clear documentation of all roles, resource groups, and user groups, along with their associated permissions and users. Ensure this documentation is version-controlled.
- **Regularly Review Access**: Conduct periodic reviews of access permissions to ensure users have the appropriate level of access. Remove users from groups if they no longer need access.
- **Utilize Resource Groups**: Leverage resource groups to align with the organization's structure and facilitate resource and permission management.
- **Principle of Least Privilege**: Grant users only the necessary permissions to perform their duties.
- **Centralized Management**: Use the Facets Control Plane as a centralized control center for managing all infrastructure and application access.
- **Automate Where Possible**: Utilize the Facets APIs to automate user management tasks, reducing manual effort and minimizing errors.

***

## FAQs

- **Can I restrict access to specific environments or projects?** Yes, you can select the specific environments or projects in the accessible environment and accessible dropdown in the user group. This will restrict your access to the selected entities.
- **Can I assign multiple roles to a user?** No, a user is assigned a default role derived from user groups. However, you can assign environment specific role within a user group to have distinct set of permissions
- **Can multiple user groups be assigned to a user group?** Yes, a user can be assigned multiple user groups, inheriting access from all of them and default role from the latest assigned user group.