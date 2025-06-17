---
title: Google Oauth
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
## Creating an OAuth Client ID in your Google Console

1. Go to the Google Console and follow the steps in the [Setting up OAuth 2.0 guide](https://support.google.com/cloud/answer/6158849).
2. Set up an Authorized Redirect URI using the following format: `<YOUR_CP_URL>/login/oauth2/code/<unique-registrationID>`.
3. Make note of the unique Registration ID provided by Google.
   1. Replace `<YOUR_CP_URL>` in the table above with the unique URL for your organization's Control Plane.
   2. We recommend using a single word, all in lower-case, as the `<unique-registrationID>`. This will be used later in the Facets UI when adding the OAuth integration to your Control Plane.

<Image align="center" className="border" width="300px" border={true} src="https://files.readme.io/700bc57-google-oauth.png" />

## Adding Integration for Google OAuth in Facets

1. Navigate to **Setting > OAuth Integrations** from the left pane.\
   This page displays all the configured OAuth Integrations in Facets.
2. Click **Add Integrations** and select **Google** as the **Provider.**
3. Fill in the following information:
   1. **Registration Id:** Use the `<unique-registrationID>` from the Authorized Redirect URI in Step 1.
   2. **Client Id:** Use the Client Id from your Google Console.
   3. **Client Secret:** Use the Client Secret from your Google Console.
   4. **Login Button Text:** Choose the text that will appear in the Control Plane Login screen. For example, you can use your organization's name.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/50990e2-image.png" />

That's it! You have successfully set up Google OAuth integration in Facets. 