---
title: Manage Infrastructure as Code (IaC) Version
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
Facets provides users with the capability to change the stream, and major and minor IaC version directly from the Control Plane. It allows teams to track changes, collaborate, and roll back to stable configurations if needed.

## How to Manage IaC Version from your Control Plane?

Facets allows you to manage the IaC version from your **Environment Settings** screen.

> 📘
>
> **Note:** IaC version or stream change will take effect from the next release after the change.

1. Login to Facets Control Plane and select the desired project in the **Projects** tab.
2. Select the **Environment** in the **Environments** tab where you want to manage the IaC version.
3. Select **Environment Settings** tab and select **Releases.**
4. Under **IaC Versions,** make the required modifications and then click **Save Changes.**

You should see a success toaster popup confirming your changes.

> 📘 NOTE
>
> **Note:** If there is no defined IaC version for an environment during deployment, Facets will automatically select the latest version of IaC from `PRODUCTION` stream.
