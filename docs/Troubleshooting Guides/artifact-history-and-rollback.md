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
## How to View the Artifact History?

The process of viewing the artifact history and performing a rollback in the Facets Control Plane is as follows:

1. Open **Blueprints** and select the desired Blueprint.
2. Select the **Environments** tab and select the required environment.
3. Select the **Resource Center** tab and select the service for which you want to view the history.
4. In the Resource Details Overview page, the **Artifact** section will display the currently registered image if any.
5. Click on **History** in the Artifact widget to view a list of previously registered artifacts. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b296f6-image.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


## How to perform a Rollback?

1. On the artifact history page, select the rollback icon on a previously registered image.
2. In the popup that appears, click **Confirm** to verify the rollback.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1f6ebc0-image.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


If the rollback is successful, the dialog window closes, a success toaster is displayed, and both the current image and history list are refreshed.