---
title: Creating CI Rules
excerpt: Route your builds to right environment
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
FCI Rules is a powerful feature that streamlines the process of build routing, empowering users to bypass complex CI pipeline logic and directly push their images to Facets. CI Rules and Promotion Workflow together can be used to automate the reclassification of images to their corresponding environments, catering to all build routing use cases.

- Allocate specific branches to designated environments, and
- Promote builds from one environment to another.

This document provides a step-by-step guide for creating and attaching CI Rules.

## How to Create CI Rules?

1. Open **Blueprints** and choose the Blueprint. Select the **CI Rules** tab.
2. Click the **Create CI Rule** button located at the top right corner.
3. Provide a unique **CI Rule Name** and select the appropriate **Registration Type.**
4. Specify the conditions for the CI Rule. Use the **Add** button to include additional conditions if needed.
5. To validate the CI Rule, click **Test Rule** and enter the necessary details for testing.
6. Finally, click **Create** to successfully create the CI Rule.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d45249c-image.png",
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


Congratulations! You have successfully created a CI Rule. 

## How to Attach CI Rule to CI Integration?

You can attach a CI rule to an integration either during the creation of the CI integration or by editing an existing integration.

1. Open **Blueprints** and choose the Blueprint. Select the **CI Integration** tab to access the CI Integration section.
2. Click the **Edit** icon beside the desired CI integration and select the required **CI Rule.**
3. Click **Save Changes.**

You have successfully attached a CI Rule to an existing CI Integration.

## How to Push Images and Classify with CI Rules?

To push an image to Facets and take advantage of CI Rules for automatic classification, use the following facets ctl push command:

```
facetsctl push --ci <ci_integration_name> --image <docker_image_name> 
--git-ref <git refernece> -e <external_id_here> -d <your_build_description>
```

When you push an image to Facets, the platform takes into account any assigned CI Rule. If a CI Rule is assigned, Facets automatically classifies the image based on the defined rule. 

> 📘 
> 
> Users will be still able to register artifacts to specific release streams or environments using the old push command. For a comprehensive understanding and proper usage of the push command, make sure to refer to the [Facets CLI](https://readme.facets.cloud/docs/command-line-tool-for-facets) documentation.

## How to Reclassify Artifacts?

The Reclassify button allows you to reclassify existing artifacts after attaching or updating a rule. Even if a rule is not attached, you can still click **Reclassify** to declassify all artifacts. To reclassify a CI integration in Facets:

1. Select the desired CI integration and click on **Reclassify.**
2. In the pop-up window, click **Confirm.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9512da7-image.png",
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


You have successfully Reclassified the CI Integration.

Any artifacts that do not match any existing rule will be categorized as unclassified artifacts and moved to the designated **Unclassified Artifacts** section.

## Related Guide

- [Creating a CI Integration](https://readme.facets.cloud/docs/creating-a-ci-integration)