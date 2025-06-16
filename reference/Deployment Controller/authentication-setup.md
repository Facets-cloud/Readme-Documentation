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
  robots: noindex
next:
  description: ''
---
## How to Authenticate your API requests

Facets API uses Basic Authentication Setup, meaning users require a username and a password to make API calls along with any parameters that may be specific to the endpoint.

The username is your registered email ID with which you access the Facets Control Plane, and the password is the unique token that you can generate from within Facets CP. For detailed instructions on how to generate a token, check out the following section.

### Generate Authentication Token (Password for Basic Auth)

1. Login to Facets Control Plane and click on your user profile picture to display Account Settings menu. 
2. Click on Generate Token to see a popup window.

<Image alt="Generate Token button" width="666px" src="https://files.readme.io/c2763bc-image.png">
  Generate Token button
</Image>

3. Add a note detailing the purpose for generating this token.

<Image title="generate token2.png" alt={2158} width="80%" src="https://files.readme.io/fb10ca6-generate_token2.png">
  Token Note (Click on the image to expand)
</Image>

4. You will see another popup window with a string of characters. This is your personal token and password for the basic authentication to make API calls. 

> 📘 Save this token!
>
> Copy this generated token and note it down somewhere since it will be visible only in this window!

<Image alt="Copy your Token from this popup window" width="666px" src="https://files.readme.io/10b2fb5-image.png">
  Copy your Token from this popup window
</Image>

You can now use this username and password combination to make API calls to Facets Endpoints.
