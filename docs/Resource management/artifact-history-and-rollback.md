---
title: Rolling Back a Service
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
## View History

The process of viewing the artifact history and performing a rollback in the Facets Control Plane is as follows:

1. Login to Facets Control Plane and select the Environment in your defined Blueprint.
2. Navigate to **Environment > Resource Center** from the sidebar and select the service for which you want to view the history.
3. In the Resource Details Overview page, the **Artifact** section will display the currently registered image if any.
4. Click on **History** in the Artifact widget to view a list of previously registered artifacts.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/07dcb7a-Rolling_back_-_view_history.gif">
  Click on the image to expand
</Image>

## To perform a rollback:

1. On the artifact history page, select the rollback icon on a previously registered image.
2. In the popup that appears, click **Confirm** to verify the rollback.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/793d99a-Rolling_back.gif">
  Click on the image to expand
</Image>

If the rollback is successful, the dialog window closes, a success toaster is displayed, and both the current image and history list are refreshed.
