---
title: Role-Based Access Control
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
This documentation guides administrators through the setup of Role-Based Access Control (RBAC) for your organization, covering Custom Roles, Blueprint and Environment Access, Blueprint Templates, and Resource Management.

**Creating Custom Roles**

Custom roles allow organizations to define specific access permissions, ensuring precise control over their resources and security policies. Refer to the [Creating Custom Roles](https://readme.facets.cloud/docs/custom-roles) documentation.

**Role-Based Access Control (RBAC) for Blueprints and Environments**

Blueprint and Environment RBAC operates through user groups. It provides permissions to specific User Groups for accessing designated Blueprints and Environments. Users within these groups gain access to the allocated Blueprints and Environments. Refer to the [Creating a User Group](https://readme.facets.cloud/docs/creating-a-user-group) documentation.

**Role-Based Access Control (RBAC) for Blueprint Templates**

A Blueprint template is a versatile tool that simplifies the creation of Blueprints. It acts as a reusable framework, offering pre-defined resources and configurations, streamlining the Blueprint development process.

RBAC for Blueprint templates ensures that only users with roles containing 'Blueprint Template - Write' or 'Blueprint Template - Delete' permissions can create or delete templates. Refer to the [Creating Custom Roles](https://readme.facets.cloud/docs/custom-roles) documentation.

**Role-Based Access Control (RBAC) for Resources**

Resource management in Facets is made efficient and secure through Role-Based Access Control (RBAC). Administrators have the ability to add resources to Resource Groups. These resource groups are then assigned to user groups, ensuring that users within these groups only have access to the specific resources they need.
