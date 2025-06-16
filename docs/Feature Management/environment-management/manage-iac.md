---
title: Manage Infrastructure as Code (IaC) Version
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
Facets provides users with the capability to change the stream, and major and minor IaC version directly from the Control Plane. 

## How to Manage IaC Version from your Control Plane?

Facets allows you to manage the IaC version from your **Environment Overview** screen as well as **Releases** screen. 

> 📘 
> 
> **Note: **IaC version or stream change will take effect from the next release after the change.

1. Login to your **Control Plane.**
2. Open **Blueprints** and select the required Blueprint.
3. Select the **Environment** in your defined **Blueprint** where you want to manage the IaC version.

### Using the Environment Overview screen

1. In the **Environment Overview** page, click the **Edit** button in the **IaC Version** widget.
2. In the **Edit IaC Version **popup, make the required modifications and then click **Save Changes.**

You should see a success toaster popup confirming your changes.

### Using the Releases screen

1. Select the desired Environment and select the **Releases** tab.
2. Click on the Ellipsis button to view more options and select **Update IaC Version.**
3. In the **Edit IaC Version **popup, make the required modifications and then click **Save Changes.**

You should see a success toaster popup confirming your changes.

> 📘 NOTE
> 
> **Note: **If there is no defined IaC version for an environment during deployment, Facets will automatically select the latest version of IaC from `PRODUCTION` stream.