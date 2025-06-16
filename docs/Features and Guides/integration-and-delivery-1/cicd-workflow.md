---
title: CI/CD Workflow
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
Facets provides various CI/CD strategies to streamline your deployment process. This document will guide you through configuring these strategies, enabling you to efficiently manage testing environments, automate promotions, and customize workflows to meet your project's needs.

## How to Configure the CI/CD workflow in Facets?

1. Open the **Projects** tab and select the required project.
2. Go to the **Project Settings** tab and select **CI/CD.** Here, you will be able to define the CI/CD Flow.
3. Facets provides three CI/CD strategies:
   1. **Branch Per Environment**
   2. **Single Branch Promotion**
   3. **Advanced**

### Branch Per Environment

This approach allows you to map each Git branch to its respective testing environment for streamlined testing.

1. Choose the condition from the dropdown and specify the value it must match.
2. Select the environment to which you want to attach artifacts.
3. Repeat the above steps for all the required environments in the project.
4. Click **Save Changes.**

### Single Branch Promotion

This approach allows you to map a Git branch to an environment. You will then set the promotion workflow and promote changes to other environments.

1. Choose the condition from the dropdown and specify the value it must match.
2. Select the environment to which you want to attach artifacts. The selected environment becomes the first environment in the flow.
3. Under the **Set Promotion Workflow** section, all the environments will be listed. Drag and rearrange them in the required order to create the promotion hierarchy.
4. Click **Save Changes.**

### Advanced

This combines Branch per Environment and Single Branch Promotion. It enables you to customize Git rules for mapping branches to specific environments and create flexible promotion workflows.

1. Select the **Registration type.** 
   1. Choose between an **Environment** or a **Release Stream.** This determines whether you will use environments or release streams to create the workflow.
2. Decide if you want to **map any Git branch to the environment/release stream.**
   1. If yes, map the Git branch to the environment/release stream.
   2. Choose the condition from the dropdown and specify the value it must match.
   3. Then, select the environment/release stream to which you want to attach artifacts.
   4. Click Add to add a new column for a different environment/release stream.
3. Decide if you want to **promote artifacts from one environment/release stream to another.**
   1. If yes, under **Environments/Release Streams Hierarchy,** select the first environment/release stream.
   2. Drag and rearrange the environments/release streams in the required order to create the promotion hierarchy.
4. Click **Save Changes.**

You have successfully created a Streamlined CI/CD Flow in Facets.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FyLyRSjBJn9g%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DyLyRSjBJn9g&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FyLyRSjBJn9g%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=yLyRSjBJn9g",
  "title": "Configuring CI/CD Workflow",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/yLyRSjBJn9g/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=yLyRSjBJn9g",
  "typeOfEmbed": "youtube"
}
[/block]


## FAQ

### 1. Do I need to make any changes to my CI pipeline if I change the branch or environment/release stream?

Yes, if you change the branch or the associated environment/release stream, you will need to update the command in your CI pipeline setup to reflect these changes. This ensures the images are registered in the correct environment or release stream.

### 2. How does the "Branch Per Environment" strategy improve deployment workflows in a multi-environment setup?

The "Branch Per Environment" strategy improves deployment workflows by isolating changes in designated branches and environments, reducing the risk of conflicts and ensuring stable, environment-specific testing and deployment.