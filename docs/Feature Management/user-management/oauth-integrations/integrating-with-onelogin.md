---
title: OneLogin
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
## How to Create an Application in OneLogin?

1. Log in to your OneLogin console and open the admin portal.
2. Navigate to **Applications > Applications** from the top pane and click **Add App.**
3. Search for **OpenId Connect (OIDC)** in the OneLogin app catalog and select it.
4. Now, mention the **Display Name,** **Description**(optional).
5. In the **Configuration** tab, mention the **Redirect URI.**\
   **Eg:** `https://<control-plane-url>/login/oauth2/code/<registration-ID>`
   > 📘
   >
   > * Replace `<control-plane-url>` in the above link with your organization's Control Plane URL.
   > * Note down the `<registration-ID>`, as the same value needs to be entered in your Control Plane.
6. In the **SSO** tab, under **Token Endpoint,** select the **Authentication Method** as **POST.**
7. In the **Users** tab, assign the app to relevant users or groups by selecting them and adding the app to their assigned applications.
8. Click **Save.**

<Image alt="Creating  an App in OneLogin" align="center" width="450px" border={true} src="https://files.readme.io/8b086e4-onelogin.gif">
  Click on the image to expand
</Image>

You have successfully created an application in OneLogin.

## How to Add Integration for OneLogin SSO in Facets?

1. Log in to your Control Plane and navigate to **Setting > OAuth Integrations** from the left pane.\
   This page displays all the configured OAuth Integrations in Facets.
2. Click **Add Integrations.**
3. Select **OneLogin** as the provider.
4. Fill in the following information:

   1. **Registration ID**

   2. **Client ID**

   3. **Client Secret**

   4. **Issuer URL**
      > 📘
      >
      > 1. Log in to the OneLogin console and open the application.
      > 2. Under the **SSO** tab, you will find the **Client Id, Client Secret,** and the **Issuer URL.**

   5. **Login Button Text**: Choose the text that will appear in the Control Plane Login screen. Facets recommends using your organization's name.
5. Click **Create.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/c05f434-image.png">
  Click on the image to expand
</Image>

You have successfully set up OneLogin integration in Facets.
