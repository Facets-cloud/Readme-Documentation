---
title: Authentication Setup
excerpt: >-
  This page will help you generate a basic authentication token for use with
  Facets API requests.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## How to Authenticate your API requests?

Facets API employs a Basic Authentication Setup. This setup necessitates that users have a username and a password to execute API calls, in addition to any parameters specified to the endpoint.

The username is your registered email ID with which you access the Facets Control Plane. The password, on the other hand, is a unique token generated within the Facets Control Plane. For detailed instructions on how to generate a token, refer to the section below:

## How to Generate an Authentication Token (Password for Basic Auth)?

1. Login to Facets Control Plane and click on your user profile picture. This will open the **Account Settings** menu. 
2. In the **Account Settings** menu, select the **Personal Token** tab. This page displays all your previously generated tokens.
3. Click **Generate Token.**
4. In the **Create Personal Access Token** pop-up, mention the **Token Name.**
5. A new pop-up window will appear displaying a string of characters.
6. This string constitutes your personal token. This will function as your password for basic authentication when making API calls.

> 📘 Save this token!
> 
> It is crucial to copy and securely store this generated token. **It will only be visible within this specific pop-up!**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e1176a-image.png",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


With this personal token (your password) and username, you are now equipped to make API calls to Facets Endpoints.