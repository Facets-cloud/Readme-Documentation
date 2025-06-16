---
title: 3. Performing Releases
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
This document outlines the process of performing a release, using advanced options, and validating changes safely.

## How to Perform a Release

Explore this step-by-step demo to walk through the release process.

<Embed url="https://app.storylane.io/9oes8dv7edgz" title="Releases | Jan 8 5:41 PM" favicon="https://assets.storylane.io/apps/prod/124/icons/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_3f81c38c-9055-45ba-a7bb-3662445f453c/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/9oes8dv7edgz" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F9oes8dv7edgz%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252F9oes8dv7edgz%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_3f81c38c-9055-45ba-a7bb-3662445f453c%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

***

## Plan and Apply Plan Flow

You can do a two-step validation and deployment workflow using **Plan** and **Apply Plan**:

* **Plan**:
  * Runs a dry-run of the deployment to preview the changes without applying them.
  * Allows you to inspect what modifications will be made to infrastructure, configuration, and artifacts.

* **Apply Plan**:
  * Executed after a successful Plan.
  * Applies exactly what was previewed during the Plan step, ensuring consistency between validation and deployment.

***

## Review Release Table

<Image align="center" width="600px" src="https://files.readme.io/5500b6fc0f228f218e9458ff68cbc0e8d994efdbc0848c16628d327c5f38bc38-image.png" />

When triggering a release directly using **Apply**, Facets shows a **Review Release Table** before applying any changes. This table provides visibility into:

* Infrastructure changes
* Artifact updates
* Configuration updates

The Review Release Table helps prevent unintended updates by giving you a chance to inspect all changes before deployment.

> This table is **only shown** when triggering **Apply** directly, not during Plan.

***

## Advanced Options

Available across all release types, the **Advanced Options** section allows users to enable deployment-level controls.

<Image align="center" width="600px" src="https://files.readme.io/6adc900497d5c221c9c4d98c25c16087baac684d51e64f97a2f417892f32d63c-Screenshot_2025-04-08_at_4.01.34_PM.png" />

<br />

| Option                       | Description                                                                                                             |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Refresh**                  | Detects infrastructure drift and updates internal state with the actual resource info.                                  |
| **Force**                    | Overrides existing resources, useful in case of conflicting definitions in the blueprint.                               |
| **Allow Destructive Action** | Deletes resources in the environment that are not defined in the blueprint. Use carefully to avoid accidental removals. |

***

## Use Cases

| Scenario                                    | Suggested Action                                           |
| ------------------------------------------- | ---------------------------------------------------------- |
| Validate changes before a production deploy | Use **Plan**, then **Apply Plan**                          |
| Deploy a targeted fix                       | Use **Selective Release**, then **Apply**                  |
| Clean up obsolete resources                 | Enable **Allow Destructive Action** under Advanced Options |
| Align state with real infrastructure        | Enable **Refresh** to detect drift before release          |

***

## Troubleshooting

| Issue                                     | Possible Cause                                    | Resolution                                                   |
| ----------------------------------------- | ------------------------------------------------- | ------------------------------------------------------------ |
| Unexpected deployment behavior            | State drift or outdated definitions               | Use **Refresh** to sync state                                |
| Resources unintentionally removed         | **Allow Destructive Action** was enabled          | Ensure all required resources exist in the blueprint         |
| Plan output doesn’t show expected changes | Missing updates in blueprint or incorrect context | Review blueprint or re-trigger the release with updated data |

***

## FAQs

**Q: What happens after I click Plan?**\
A: Facets shows a detailed plan output listing what changes will occur. No resources are changed at this stage.

**Q: Can I modify the release after a Plan is generated?**\
A: To include new changes, you need to re-initiate the release and generate a new Plan.
