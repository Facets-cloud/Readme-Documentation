---
title: Generic SSO
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
Facets allows users to enhance their login experience by integrating a custom Single Sign-On (SSO) solution through OPEN\_ID. This feature streamlines the authentication process, providing users with a secure way to access the Facets control plane.

## Prerequisite

* Users need to have pre-existing accounts created through OPEN\_ID.
* Users must have OAUTH\_INTEGRATION\_WRITE authority.

## Adding Integration for Generic SSO in Facets

1. Navigate to **Setting > OAuth Integrations** from the left pane.\
   This page displays all the configured OAuth Integrations in Facets.
2. Click **Add Integrations** and select **Custom SSO** as the **Provider.**
3. Fill in the following information:
   1. **Registration ID:** A unique identifier for your application.
   2. **Client ID:** A public identifier for your client application during authentication.
   3. **Client Secret:** A confidential key for secure communication with the authorization server.
   4. **Authorization URL:** The link where users authenticate and grant access to your application.
   5. **JWK Set URI:** A URL pointing to a set of public keys used for token verification.
   6. **Token URI:** The endpoint where the authorization code is exchanged for an access token.
   7. **User Info URI:** Endpoint to fetch additional user information after authentication.
4. Select the **Client Authentication Method** between **Post** and **Basic.**\
   **Note:** We recommend using the 'Post' method for enhanced security in client authentication
5. **Login Button Text:** Choose the text that will appear in the Control Plane Login screen. Facets recommends using your organization's name. 
6. Click **Create.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/d7b7076-image.png">
  Click on the image to expand
</Image>

You have successfully set up Custom SSO integration in Facets.
