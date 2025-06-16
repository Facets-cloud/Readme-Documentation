---
title: Integrate Version Control Systems (VCS) with Facets
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
This document provides a step-by-step guide for integrating version control system(VCS) accounts in your Control Plane. **Github**, **Gitlab**, and **Bitbucket** can currently be integrated with Facets.

## How to Add a VCS Account in Facets?

Navigate to **Settings > Accounts** from your sidebar.\
All the accounts integrated with Facets will be displayed here. 

## Github account

1. Select **Github** from the Add Account widget on the screen.
2. Fill in the **Account Name** you want to associate with this account in the Control Plane. 
3. Enter the link where this is **Hosted on** and click **Next.**
4. Now, click **Generate Token.** 
   1. This will redirect you to the GitHub **Personal Access Tokens** page where the  **Scopes** are pre-selected.\
      **Note:** When creating your Personal Access Token, Facets recommends setting the expiry to the maximum time frame for ease of use.
   2. Click **Generate Token** and copy the generated token.
5. Paste the **Personal Access Token** in the Control Plane and click **Link.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/2f97690-image.png">
  Click on the image to expand
</Image>

You have successfully linked your GitHub account. Your account details will now be available under the Account Management page.

## GitLab account

1. Select **GitLab** from the Add Account widget on the screen.
2. Fill in the **Account Name** you want to associate with this account in the Control Plane and click **Next.**
3. Now, click **Generate Token.** 
   1. This will redirect you to Gitlab's **Personal Access Tokens** page.
   2. Click **Add new token.**
   3. Mention the **Token name,** and **Expiration Date.** The **Scopes** are pre-selected.\
      **Note:** When creating your Personal Access Token, Facets recommends setting the expiry to the maximum time frame for ease of use.
   4. Click **Create personal access token** and copy the generated token.
4. Paste the **Personal Access Token** in the Control Plane and click **Link.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/4f4fec7-image.png">
  Click on the image to expand
</Image>

You have successfully linked your Gitlab account. Your account details will now be available under the Account Management page.

## Bitbucket account

1. Select **Bitbucket** from the Add Account widget on the screen.
2. Fill in the **Account Name** you want to associate with this account in the Control Plane. 
3. Copy/Create an App password in Bitbucket by [following this guide](https://support.atlassian.com/bitbucket-cloud/docs/app-passwords/).
4. Enter your Gitlab **Username** and the **App password.**
5. Click **Add Account.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/418e4f0-image.png">
  Click on the image to expand
</Image>

You have successfully linked your Bitbucket account. Your account details will now be available under the Account Management page.
