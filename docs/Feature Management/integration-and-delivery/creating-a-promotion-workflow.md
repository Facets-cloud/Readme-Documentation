---
title: Creating a Promotion Workflow
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
A Promotion Workflow allows you to promote changes through different environments/release streams, ensuring a streamlined and controlled process for software deployment. This document provides a step-by-step guide for creating a promotion workflow.

## How to Create a Promotional Workflow?

1. Open **Blueprints** and choose the Blueprint. Select the **Promotion Workflow** tab.\
   You will find all the **Promotion Workflows** related to this Blueprint on this page.
2. Click **Create Promotion Workflow** and mention the **Workflow Name.**

## Registration Type

Select the **Registration Type** as **Environment** or **Release Stream.**

### Environment Name

1. If you choose the **Registration Type** as **Environment,** all the **Available Environments** will be displayed under **Promotional Hierarchy.**
2. You can also click the **+** icon beside the environment or drag the environments from the **Available Environments** to the **Environments Hierarchy** column to create the **Promotion Hierarchy.**
3. Click **Create.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/68a2584-image.png">
  Click on the image to expand
</Image>

### Release Stream

1. If you choose the **Registration Type** as **Release Stream,** all the **Available Release Streams** will be displayed under **Promotional Hierarchy.**
2. You can also click the **+** icon beside the release stream or drag the release stream from the **Available Release Streams** to the **Release Streams Hierarchy** column to create the **Promotion Hierarchy.**
3. **Global:** Enabling this toggle will make this workflow available to all the blueprints.
4. Click **Create.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/f3df063-image.png">
  Click on the image to expand
</Image>

You have successfully created a Promotion Workflow in the Facets Control Plane.

## Related guides

* [Promoting an Artifact](https://readme.facets.cloud/docs/creating-a-ci-integration#promoting-an-artifact)
