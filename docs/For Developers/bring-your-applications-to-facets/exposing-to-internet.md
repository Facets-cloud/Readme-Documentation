---
title: Exposing to Internet
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
Now that your dependencies are all mapped, let’s move on to exposing the app to the internet. Here's a step-by-step walkthrough.

## Custom Domains

To make your application accessible using a custom domain on Facets.cloud, follow these steps:

### 1. Set Up Ingress

Facets.cloud uses an ingress to route external traffic to your application. So you have to create an ingress resource in Facets.cloud and configure it with the required port and other ingress rules.

### 2. Map the Custom Domain

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04f111051427bbf0645a00f5f17e1414466258d8899055d71f09e7343f8f832e-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


- Now select the Ingress Resource from **Resource Center**, choose the environment for which you want to configure domains.
- Now, click on the **Domains** tab.
- Select the environment (e.g., staging, production) where you want to map your custom domain.
- Click **Map Custom Domain**.
- In the UI that appears, provide the following details:
  - **Custom Domain Alias**: This unique, user-defined name serves as an alternative web address.
  - **Custom Domain URL**: This refers to the specific web address associated with the Custom Domain Alias.
- Click **Create** to finalize the mapping.

### 3. Update DNS

- Now, navigate to your DNS provider and add a **CNAME** record for the designated custom domain, and save the changes.