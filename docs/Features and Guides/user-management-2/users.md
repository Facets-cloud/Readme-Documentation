---
title: Users
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
This page describes how to create and manage users in Facets. Users are individuals who access and utilize the Facets platform. User is the central component of user management in Facets.

## Prerequisites

Before you can manage users in Facets, you need the following:

- Access to the Settings area of the Facets Control Plane.
- Appropriate permissions to manage users, which may be tied to a specific role.

***

## Use cases:

### Creating a User

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fb2ktukrhgy4q&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fb2ktukrhgy4q&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_1e499a2d-ac7d-40e7-84cc-7451cc6ce21b%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"431\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/b2ktukrhgy4q",
  "title": "Users",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_1e499a2d-ac7d-40e7-84cc-7451cc6ce21b/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/b2ktukrhgy4q",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

### Generating an Authentication Token (Personal Token)

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Feiwvatpg1bt6&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Feiwvatpg1bt6&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_a5e53e18-ac4e-478b-b5ce-7daa78215cc8%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"431\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/eiwvatpg1bt6",
  "title": "Person Token",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_a5e53e18-ac4e-478b-b5ce-7daa78215cc8/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/eiwvatpg1bt6",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

***

## User Attributes

When creating a user, you can configure the following attributes:

- **User email**: This is a mandatory field used as the user's login and for email notifications.
- **Password**: A mandatory field for user authentication.
- **User Group**: A mandatory field that specifies the group the user belongs to and thus defines their access rights.
- **Default Role**: A Default Role is derived from the assigned user group(s) for a user. It sets the basic, CP-wide access level for the user, applying across all accessible entities unless overridden by an environment-specific role.

***

## FAQs

- **How do I reset a user password?** (Note that the sources do not discuss password reset).
- **What should I do if I lose my personal access token?** You will need to generate a new personal access token as the previous one is not recoverable.
- **How can a user be removed from Facets?** Click on the Delete action button for that particular user to remove access.
- **How to update permissions of an existing user?** Create a new role with the updated permissions if it doesn't exist already, create a user group using this role and assign this new user group to the user.
- **How to provide access for a new project environment to existing users?** Create new