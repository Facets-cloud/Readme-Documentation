---
title: JumpCloud
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
## Adding Integration for JumpCloud SSO in Facets

1. Log in to your Control Plane and navigate to **Setting > OAuth Integrations** from the left pane.  
   This page displays all the configured OAuth Integrations in Facets.
2. Click **Add Integrations.**
3. Select **JumpCloud** as the provider.
4. Enter the **Registration ID.**  
   **Note:** Based on your input, Facets will generate a **Redirect URL.** Copy this URL and proceed to [Creating an Application in JumpCloud.](https://readme.facets.cloud/docs/jumpcloud#creating-an-application-in-jumpcloud)
5. Fill in the following details:
   1. **Client ID**
   2. **Client Secret**
   3. **Login Button Text**: Choose the text that will appear in the Control Plane Login screen. Facets recommends using your organization's name.
      > 📘 
      > 
      > **Note: **
      > 
      > 1. Log in to the JumpCloud console and open the application.
      > 2. Under the SSO tab, you will find the **Client ID.**
      > 3. On the left plane, click **Client Secret Valid** and select **Regenerate Secret.** This is the **Client Secret.**
6. Click **Create.**

You have successfully set up JumpCloud integration in Facets.

## Creating an Application in JumpCloud

To integrate JumpCloud with Facets, it is crucial to first create a custom OIDC application within JumpCloud, from which you can generate the Client ID and Client Secret. Please follow the steps outlined below:

1. Log in to the JumpCloud Admin Portal and navigate to **User Authentication > SSO Applications.**
2. Click **+ Add New Application** 
3. Select **Custom Application** and click **Next.**
4. Now, select **Manage Single Sign-On (SSO),** choose **Configure SSO with OIDC** then click **Next.**
5. Mention the **Display Label** (mandatory), **Description**, **User Portal Image** and click **Next.**
6. Review the details and click **Configure Application.**
7. In the SSO tab, mention the **Redirect URL.**  
   **Note:** Paste the URL generated in step 4 of [Adding Integration for JumpCloud SSO in Facets.](https://readme.facets.cloud/docs/jumpcloud#adding-integration-for-jumpcloud-sso-in-facets)
8. Mention the **Login URL.**  
   **Note:** The **Login URL** is your organization's **Control Plane URL.**
9. Under **Attribute Mapping,** select **Email** and **Profile** as **Standard Scopes.**
10. Next, go to the **User Groups** tab and select the necessary user groups that require access to the application.
11. Click **Activate.**

You have successfully created Facets as an application in JumpCloud.

Now, continue with Step 5 in [Adding Integration for JumpCloud SSO in Facets.](https://readme.facets.cloud/docs/jumpcloud#adding-integration-for-jumpcloud-sso-in-facets)