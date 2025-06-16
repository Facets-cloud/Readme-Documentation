---
title: User Roles
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
      slug: resource-groups
      title: Resource Groups
    - type: basic
      slug: user-groups
      title: User Groups
    - type: basic
      slug: custom-kubernetes-role
      title: Custom Kubernetes Role
---
Define roles with specific [permissions](https://readme.facets.cloud/docs/user-management-permissions-1), then assign these roles to users and user groups. This ensures users only have the necessary access to perform their tasks, following the principle of least privilege. Facets offers both system-defined and custom roles to accommodate various organizational needs.

***

## System-defined Roles

Facets provides a set of pre-defined roles with common permission sets. These roles can be used as is or as a starting point to create custom roles.

<Image align="center" width="600px" src="https://files.readme.io/72470e4b032b8806134f8ab4806ba939f033f30783147820f7db3776ad679e48-Screenshot_2025-02-11_at_6.25.07_PM.png" />

### 1. Admin

* The Admin role has comprehensive access to all functionalities within the system. 
* This includes permissions to create, edit, and delete various resources such as accounts, artifacts, blueprints, and release streams, manage settings, configure environments, and oversee user roles. They have the authority to approve or reject releases, manage billing, and perform critical operations like launching and destroying environments. 
* This role is designed for users who require full control over the system's capabilities.

### 2. Developer

* The Developer role is tailored for users who need to create and manage artifacts, release streams, resources and CI/CD configurations. 
* Developers can add and update Artifact CI, configure alerts, and perform selective releases. They have permissions to view roles and resource groups but do not have access to full release capabilities or the ability to create or edit blueprints. 
* This role is ideal for users focused on development tasks without the broader administrative privileges.

### 3. Environment Admin

* The Environment Admin role provides users with restricted access to specific environments. 
* They can create and edit artifacts, manage release streams, and configure alerts. Environment Admins have the ability to perform operations related to environments, such as launching, updating, and deleting them. 
* This role is designed for users who need to manage environments while ensuring that their access is limited to specific functionalities.

### 4. Viewer

* The Viewer role is designed for users who require read-only access to the system. 
* Viewers can view users, resource groups, roles, and user groups, as well as read Kubernetes resources. They have no permissions to create, edit, or delete any resources, making this role suitable for stakeholders who need to monitor system activities without making changes. 
* This role ensures that sensitive operations are protected while allowing visibility into the system's state.

### 5. Guest

* The Guest role is a highly restricted role that does not grant any permissions within the system. Users assigned to this role have no access to view, create, edit, or delete any resources or functionalities. 
* This role is typically used for individuals who require no interaction with the system's features, ensuring that sensitive data and operations remain secure and inaccessible to unauthorized users.
* The Guest role serves as a placeholder for users who may need to be onboarded in the future but currently do not require any access rights.

***

## Custom Roles

* If the system-defined roles do not meet your specific requirements, you can create custom roles with tailored permissions. [List of available permissions.](https://readme.facets.cloud/docs/user-management-permissions-1)
* This ensures users have only the necessary access to perform their duties, improving security and reducing the risk of accidental misconfigurations.
* Examples of custom roles include a "Release Manager" role with permissions to trigger deployments but not modify resources or a "Support Engineer" role with limited access for troubleshooting.

<Embed url="https://app.storylane.io/demo/faxuvygavjcm" title="Create Role" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_663c3177-cecb-4ada-b4c5-5b63586447b5/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/faxuvygavjcm" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ffaxuvygavjcm%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ffaxuvygavjcm%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_663c3177-cecb-4ada-b4c5-5b63586447b5%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

***

## Clone Role

* The clone role functionality allows you to create a new role by copying the permissions of an existing role. This is useful when you need a new role that is similar to an existing one, but requires minor changes.
* Choose a role in the dropdown **Choose role to duplicate permissions from** to clone the permissions of any Role

***

## Kubernetes Roles

* Kubernetes roles provide fine-grained access control for Kubernetes resources within Facets. These roles determine what actions users can perform on Kubernetes resources in the Facets environments.
* You can create roles that allow developers to deploy and manage applications within their namespaces while restricting their access to other critical resources.
* **System-defined Kubernetes Roles:**
  * **Reader:** Allows users to view Kubernetes resources and pod logs.
  * **Debugger:** Grants permission to debug Kubernetes, access application pods, and restart pods.
* **Custom Kubernetes Roles:** You can create custom Kubernetes roles with specific permissions, allowing you to define tailored access controls. These roles are defined in the `k8s_access_control` resource within the blueprint.
* **Kubernetes Credentials:** The ability to download Kubernetes credentials from the UI is controlled by a separate toggle. Users need at least one of the following permissions (K8S\_READER, K8S\_DEBUGGER, or a custom Kubernetes role) to download credentials.

<Embed url="https://app.storylane.io/demo/3y2vxc9nbbwh" title="Create Custom Role | Feb 13 12:43 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_3edc87cd-77b5-40e2-b8fc-a518be7c6e82/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/3y2vxc9nbbwh" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F3y2vxc9nbbwh%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F3y2vxc9nbbwh%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_3edc87cd-77b5-40e2-b8fc-a518be7c6e82%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

***

## Access Analyser

* The Access Analyzer feature helps administrators quickly identify users who possess specific permissions within the platform. 
* It provides a centralized view of user access rights, streamlining auditing, troubleshooting, and security management
* Tags are used to indicate the source of each permission, allowing administrators to understand how each user acquired their access rights. 
* The permission source can be either a default role assigned to the user or an environment-specific role granted for a particular environment.
* Use Case:
  * **Auditing User Access:** Regularly audit user access to ensure compliance with security policies and identify any potential over-permissions, helping maintain a secure environment.
  * **Troubleshooting Access Issues:** Quickly identify the permissions a user has when troubleshooting access-related problems by determining if the user lacks necessary permissions or if there is a conflict between roles.
  * **Analyzing Environment-Specific Permissions:** Understand how environment-specific roles affect user access within different environments (e.g., development, staging, production) to ensure that sensitive environments are properly secured and access is restricted to authorized personnel.

<Embed url="https://app.storylane.io/demo/tydrh0wlvbx0" title="Access Analyser" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_37fba496-90ba-475a-abcd-fe02adbd3403/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/tydrh0wlvbx0" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ftydrh0wlvbx0%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ftydrh0wlvbx0%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_37fba496-90ba-475a-abcd-fe02adbd3403%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

***

## Best practices

* **Use System-Defined Roles as a Starting Point:** Start with the system-defined roles when possible to understand the basic access needs, and then customize further as required.
* **Combine Roles and User Groups:** To effectively manage permissions for many users, use roles and user groups to control access.
* **Regularly Review Roles and Permissions:** Conduct regular audits of roles and permissions to ensure they remain relevant and aligned with your organization's needs.
* **Use Clear Naming Conventions:** Use clear and descriptive names for roles and groups to improve discoverability and maintainability.
* **Document Custom Roles:** Provide clear descriptions for all custom roles so that it is clear what each role is supposed to do.
* **Test Thoroughly:** Always test new roles and permissions to make sure they work as expected.
