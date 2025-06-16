---
title: Map Custom Domains
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Domain mapping is a powerful tool for businesses looking to align their custom domains with their online presence, thereby boosting both branding and accessibility. Here’s a step-by-step guide to help you map your custom domains:

## How to Map Custom Domains?

1. Login to Facets Control Plane and select the desired project in the **Projects** tab.
2. In the **Blueprint** tab, locate and select the **Ingress** resource and select **Overview** from the drop-down.
3. Now, click on the **Domains** tab. 
4. Select the **Environment** where you want to map your custom domain to the Ingress resource.
5. Click **Map Custom Domain.**
6. In the UI that appears, provide the following details:
   - **Custom Domain Alias: **This unique, user-defined name serves as an alternative web address. 
   - **Custom Domain URL: **This refers to the specific web address associated with a Custom Domain Alias.
7. Click **Create** to finalize the mapping.
8. Now, navigate to your DNS provider. Establish a CNAME record for the designated custom domain, and save the changes.

By following these steps, you can effortlessly map your custom domains, ensuring your online presence is both professional and easily accessible.