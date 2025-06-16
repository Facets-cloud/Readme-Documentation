---
title: Set CI/CD Workflow
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
Facets provides various CI/CD strategies to streamline your deployment process and defines how code moves from development to production across your environments. This configuration serves as a template for all services within your project, ensuring consistent deployment practices. This document will guide you through configuring these strategies, enabling you to efficiently manage testing environments, automate promotions, and customise workflows to meet your project's needs.

## How to Configure the CI/CD workflow in Facets?

<Embed url="https://www.youtube.com/watch?v=yLyRSjBJn9g" title="Configuring CI/CD Workflow" favicon="https://www.youtube.com/favicon.ico" image="https://i.ytimg.com/vi/yLyRSjBJn9g/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=yLyRSjBJn9g" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FyLyRSjBJn9g%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DyLyRSjBJn9g%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FyLyRSjBJn9g%252Fhqdefault.jpg%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

1. Open the **Projects** tab and select the required project.
2. Go to the **Project Settings** tab and select **CI/CD.** Here, you will be able to define the CI/CD Flow.
3. Choose from the below CI/CD strategies:

   1. **Branch Per Environment**
   2. **Single Branch Promotion**
   3. **Advanced**

   <Image align="center" src="https://files.readme.io/08418b691b15f091face5378c8226518de4ce85fb58c849d58beda3f5f561388-Screenshot_2025-02-17_at_12.13.21_PM.png" />

### i. Branch Per Environment

This approach maps individual Git branches directly to specific environments, ideal for teams maintaining separate branches for different deployment stages. 

1. Choose a branch pattern (e.g., develo&#x70;*, release/*, main) and select the target environment for that branch
2. Repeat the above steps for all the required environments in the project.
3. Click **Save Changes.**

**Use Case:**

* Each environment needs independent code branches
* Different teams manage different environments
* Environment-specific code variations are required

***

### ii. Single Branch Promotion

This approach creates a promotion-based workflow starting from one branch, ideal for teams practicing trunk-based development.

1. Choose the condition from the dropdown and specify the value it must match.
2. Choose source branch and then select the base environment to which you want to attach artifacts. The selected environment becomes the first environment in the flow.
3. Under the **Set Promotion Workflow** section, all the environments will be listed. Drag and rearrange them in the required order to create the promotion hierarchy, first being the one chosen in the previous step.
4. Click **Save Changes.**

**Use Cases:**

* Following trunk-based development and need controlled, progressive deployments
* Want automated promotions with validation gates

***

### iii. Advanced

This combines Branch per Environment and Single Branch Promotion. It enables you to customize Git rules for mapping branches to specific environments and create flexible promotion workflow for complex deployment scenarios.

1. Select the **Registration type.** 
   1. Choose between an **Environment** or a **Release Stream.** This determines whether you will use environments or release streams to create the workflow.
2. Decide if you want to **map any Git branch to the environment/release stream.**
   1. If yes, map the Git branch to the environment/release stream.
   2. Create multiple CI Rules based on your deployment strategy. 
3. Decide if you want to **promote artifacts from one environment/release stream to another.**
   1. If yes, under **Environments/Release Streams Hierarchy,** select the first environment/release stream.
   2. Drag and rearrange the environments/release streams in the required order to create the promotion hierarchy.
4. Click **Save Changes.**

*Note: Release Streams can be created from the Organization Settings of the control plane.*

**Use Cases:**

* Need maximum flexibility and have complex deployment requirements
* Managing multiple release streams or environments. 

You have successfully created a Streamlined CI/CD Flow in Facets.

***

## FAQ

### 1. How does the "Branch Per Environment" strategy improve deployment workflows in a multi-environment setup?

The "Branch Per Environment" strategy improves deployment workflows by isolating changes in designated branches and environments, reducing the risk of conflicts and ensuring stable, environment-specific testing and deployment.

### 2. Do I need to make any changes to my CI pipeline if I change the branch or environment/release stream?

Yes, if you change the branch or the associated environment/release stream, you will need to update the command in your CI pipeline setup to reflect these changes. This ensures the images are registered in the correct environment or release stream.

### What are promotion workflows?

Promotion workflows are used to promote builds from one environment to another, such as from a QA environment to a Staging environment and finally to a Production environment. These workflows help to ensure that builds are only promoted when they are ready and that the promotion process is well-defined and controlled.

### What are the benefits of using promotion workflows?

By using promotion workflows, organizations can reduce the risk of errors and make it easier to roll back if needed. Additionally, the promotion workflows include auditing information, such as who promoted which build and when, providing a clear record of the promotion process for accountability and transparency purposes.
