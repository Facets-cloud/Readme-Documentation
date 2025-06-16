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

* Access to the Settings area of the Facets Control Plane.
* Appropriate permissions to manage users, which may be tied to a specific role.

***

## Use cases:

### Creating a User

<Embed url="https://app.storylane.io/demo/b2ktukrhgy4q" title="Users" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_1e499a2d-ac7d-40e7-84cc-7451cc6ce21b/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/b2ktukrhgy4q" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fb2ktukrhgy4q%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fb2ktukrhgy4q%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_1e499a2d-ac7d-40e7-84cc-7451cc6ce21b%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

### Generating an Authentication Token (Personal Token)

<Embed url="https://app.storylane.io/demo/eiwvatpg1bt6" title="Person Token" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_a5e53e18-ac4e-478b-b5ce-7daa78215cc8/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/eiwvatpg1bt6" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Feiwvatpg1bt6%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Feiwvatpg1bt6%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_a5e53e18-ac4e-478b-b5ce-7daa78215cc8%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

***

## User Attributes

When creating a user, you can configure the following attributes:

* **User email**: This is a mandatory field used as the user's login and for email notifications.
* **Password**: A mandatory field for user authentication.
* **User Group**: A mandatory field that specifies the group the user belongs to and thus defines their access rights.
* **Default Role**: A Default Role is derived from the assigned user group(s) for a user. It sets the basic, CP-wide access level for the user, applying across all accessible entities unless overridden by an environment-specific role.

***

## FAQs

* **How do I reset a user password?** (Note that the sources do not discuss password reset).
* **What should I do if I lose my personal access token?** You will need to generate a new personal access token as the previous one is not recoverable.
* **How can a user be removed from Facets?** Click on the Delete action button for that particular user to remove access.
* **How to update permissions of an existing user?** Create a new role with the updated permissions if it doesn't exist already, create a user group using this role and assign this new user group to the user.
* **How to provide access for a new project environment to existing users?** Create new
