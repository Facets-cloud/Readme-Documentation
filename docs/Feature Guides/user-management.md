---
title: Managing Users
excerpt: How to add users and assign permissions to your users
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
During the set up of Facets Control, an admin role would have been assigned to you. In this Section, you will learn how to add your developers to Facets Control Plane.

# Adding Users Manually

You can add users manually if you have Admin Credentials. 

Click on the Settings Icon and click on Users.

<Image title="Users button in UI.PNG" alt="Users Button in Settings (Click on the image to expand)" align="center" width="80%" src="https://files.readme.io/b21a031-Users_button_in_UI.PNG">
  Users Button in Settings (Click on the image to expand)
</Image>

Click on Create User and fill in the details as required.

<Image title="Create User popup.PNG" alt="Creating a user manually (Click on the image to expand)" align="center" width="80%" src="https://files.readme.io/2e01539-Create_User_popup.PNG">
  Creating a user manually (Click on the image to expand)
</Image>

# RBAC

Role Based Access Control helps you in assigning roles to users. 

## Base Roles

> 📘 Permissions associated with each role is now listed as a tooltip in the Create User screen.
>
> You can also refer to [Granular Permissions](https://readme.facets.cloud/docs/user-management#granular-permissions-for-rbac-roles) section for a description of all permissions.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Base Role
      </th>

      <th>
        Roles
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ADMIN
      </td>

      <td>
        All pages, buttons and actions are accessible to the ADMIN role, including those in the DEVELOPER and VIEWER roles.
      </td>
    </tr>

    <tr>
      <td>
        DEVELOPER
      </td>

      <td>
        The following actions are available for DEVELOPER role in the listed screens:\
        • **Environments**screen: Pause/Resume Releases\
        • **Secrets and Variables** screen: Edit an Entry and Submit Changes.\
        • **Releases** screen: Configure Release and Selective Release, Schedule Release and Unlock State.\
        • **Overrides**screen: Add and Delete Override.\
        • **Backup**screen: Create Snapshots.\
        • **Provided Resources** screen: Update Resources.\
        • **Template Inputs** screen: Create New Tenants and Edit Tenants.\
        • **Alerts Centre** screen: Silence Alert\
        • All the access privileges of VIEWER role.
      </td>
    </tr>

    <tr>
      <td>
        VIEWER
      </td>

      <td>
        • **Environments**screen:  Sync with Git\
        • **Environment Overview** screen: Renew and Download K8s credentials and Sync with Git\
        • **Backup**screen: List Snapshots
      </td>
    </tr>

    <tr>
      <td>
        GUEST
      </td>

      <td>
        Usually gets assigned for a new user by default. Useful for Admin to filter and assign a role later.
      </td>
    </tr>

    <tr>
      <td>
        CLUSTER\_ADMIN
      </td>

      <td>
        Perform Releases
      </td>
    </tr>
  </tbody>
</Table>

## Additional Roles

> 🚧
>
> Any Base Role can be assigned Additional Roles that give access to specific actions in Facets.

| Additional Roles    | Roles                                                       |
| :------------------ | :---------------------------------------------------------- |
| K8S\_READER         | Can download K8s credentials and do readonly operations     |
| K8S\_DEBUGGER       | Can download K8s credentials and do write operations on K8s |
| CLI\_ARTIFACT\_PUSH | Can push artifacts using CLI                                |

## Granular Permissions for RBAC roles

RBAC roles defined in Facets have a list of associated permissions that grant the user privileges to perform certain actions as listed in [Base Roles table](https://readme.facets.cloud/docs/user-management#base-roles). You can find a comprehensive list of permissions listed below.

| Permission                    | Description                                                         |
| :---------------------------- | :------------------------------------------------------------------ |
| ALERTS\_CONFIGURE             | Grants permission to configure alerts.                              |
| APPLICATION\_ROLLING\_RESTART | Grants permission to initiate a rolling restart for an application. |
| ARTIFACTORY\_WRITE            | Grants permissions to create and edit artifactories.                |
| ARTIFACTS\_DELETE             | Grants permissions to delete artifacts.                             |
| ARTIFACTS\_WRITE              | Grants Write permissions for actions related to artifacts.          |
| CHANNEL\_WRITE                | Grants permission to create and edit channels.                      |
| ENVIRONMENT\_CONFIGURE        | Grants permission to configure environments.                        |
| ENVIRONMENT\_DELETE           | Grants permission to delete environments.                           |
| ENVIRONMENT\_DESTROY          | Grants permission to destroy environments.                          |
| ENVIRONMENT\_LAUNCH           | Grants permission to launch environments.                           |
| ENVIRONMENT\_WRITE            | Grants permission to create, edit and configure environments.       |
| OAUTH\_INTEGRATION\_DELETE    | Grants permission to delete OAuth integration.                      |
| OAUTH\_INTEGRATION\_WRITE     | Grants permission to add and edit OAuth integration.                |
| STACK\_CONFIGURE              | Grants permission to pause and unpause releases in an environment.  |
| STACK\_WRITE                  | Grants permission to add and edit blueprints.                       |
| SUBSCRIPTION\_DELETE          | Grants permission to delete subscriptions.                          |
| SUBSCRIPTION\_WRITE           | Grants permission to create and edit subscriptions.                 |
| TEMPLATE\_WRITE               | Grants permission to create and edit tenants.                       |
| USER\_WRITE                   | Grants permission to create and edit user and also edit passwords.  |

# Google OAuth Integration

If you are using google workspace for your team logins, Facets can use the same login mechanism to give your users an instant access. 

## ☝️ Create an Oauth Client ID in your google console

Please refer to the google docs below 

<Embed url="https://support.google.com/cloud/answer/6158849?hl=en" title="Setting up OAuth 2.0" favicon="https://support.google.com/favicon.ico" provider="support.google.com" href="https://support.google.com/cloud/answer/6158849?hl=en" />

<Image align="center" width="80%" src="https://files.readme.io/700bc57-google-oauth.png" />

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Variable Name
      </th>

      <th>
        Value
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Application Type
      </td>

      <td>
        Web Application
      </td>
    </tr>

    <tr>
      <td>
        Name
      </td>

      <td>
        Any name indicating the name of the Oauth 2.0 client
      </td>
    </tr>

    <tr>
      <td>
        Authorized Redirect URIs
      </td>

      <td>
        {user.CP_URL}login/oauth2/code/`<unique-registration ID>`
      </td>
    </tr>
  </tbody>
</Table>

> 📘
>
> This unique registration ID will be used later in the Facets UI to onboard the integration. We suggest it to be a single word all lower case.

## ✌️ Add the integration in Facets

![](https://files.readme.io/d151f83-oauth-add.png "oauth-add.png")

Click on the "Oauth Integrations" and choose "Add new Google Integration". 

<Image align="center" width="80%" src="https://files.readme.io/ebca59d-add_new_google.png" />

Fill in the values as below

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Variable Name
      </th>

      <th>
        Value
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Registration Id
      </td>

      <td>
        `<unique-registration ID>` given in redirect URI
      </td>
    </tr>

    <tr>
      <td>
        Client Id
      </td>

      <td>
        From Google Console
      </td>
    </tr>

    <tr>
      <td>
        Client Secret
      </td>

      <td>
        From Google Console
      </td>
    </tr>

    <tr>
      <td>
        Login Button Text
      </td>

      <td>
        Text that will appear in the CP Login screen. For e.g. \<OrgName>
      </td>
    </tr>
  </tbody>
</Table>

> 📘
>
> Logout to see this new button on the login screen. Any new user by default will receive a GUEST role until an ADMIN assign her to a desired [Role](doc:user-management#rbac)