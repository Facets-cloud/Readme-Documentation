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

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2F9oes8dv7edgz&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2F9oes8dv7edgz&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_3f81c38c-9055-45ba-a7bb-3662445f453c%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"449\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/9oes8dv7edgz",
  "title": "Releases | Jan 8 5:41 PM",
  "favicon": "https://assets.storylane.io/apps/prod/124/icons/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_3f81c38c-9055-45ba-a7bb-3662445f453c/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/9oes8dv7edgz",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

***

## Plan and Apply Plan Flow

You can do a two-step validation and deployment workflow using **Plan** and **Apply Plan**:

- **Plan**:
  - Runs a dry-run of the deployment to preview the changes without applying them.
  - Allows you to inspect what modifications will be made to infrastructure, configuration, and artifacts.

- **Apply Plan**:
  - Executed after a successful Plan.
  - Applies exactly what was previewed during the Plan step, ensuring consistency between validation and deployment.

***

## Review Release Table

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5500b6fc0f228f218e9458ff68cbc0e8d994efdbc0848c16628d327c5f38bc38-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


When triggering a release directly using **Apply**, Facets shows a **Review Release Table** before applying any changes. This table provides visibility into:

- Infrastructure changes
- Artifact updates
- Configuration updates

The Review Release Table helps prevent unintended updates by giving you a chance to inspect all changes before deployment.

> This table is **only shown** when triggering **Apply** directly, not during Plan.

***

## Advanced Options

Available across all release types, the **Advanced Options** section allows users to enable deployment-level controls.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6adc900497d5c221c9c4d98c25c16087baac684d51e64f97a2f417892f32d63c-Screenshot_2025-04-08_at_4.01.34_PM.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


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

**Q: What happens after I click Plan?**  
A: Facets shows a detailed plan output listing what changes will occur. No resources are changed at this stage.

**Q: Can I modify the release after a Plan is generated?**  
A: To include new changes, you need to re-initiate the release and generate a new Plan.