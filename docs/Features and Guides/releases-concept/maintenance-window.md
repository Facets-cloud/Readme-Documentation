---
title: Maintenance Window
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
The Maintenance Window allows users to schedule infrastructure updates during specified time periods without impacting the Control Plane. Follow these steps to configure the Maintenance Window:

## How to schedule a Maintenance Window?

**Note:** Automated updates occur when the Infrastructure as Code (IaC) version is set to the latest; to opt out of these automated updates, pin the environment to an older IaC version.

1. Navigate to the **Projects** tab and select the desired project.
2. Select the **Environment** tab and open **Environment Settings**.
3. In the **Environment Settings**, select the **Releases** tab.
4. In the **Maintenance Window** section, select the day from the **Release On** dropdown to indicate the day on which the release will occur.
5. Specify the **Window's Start Time**; the **Window's End Time** will be automatically populated based on this selection, with an approximate duration of four hours. Note that the end time cannot be edited.
6. Select the required **Timezone** and click **Save Changes.**

You have successfully configured the Maintenance Window.
