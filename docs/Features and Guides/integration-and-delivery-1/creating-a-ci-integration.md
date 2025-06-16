---
title: Creating a CI Integration
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
This document provides a step-by-step guide for creating a CI Integration.

## How to Create a CI Integration?

1. **Access the CI Integration Page:** Open **Blueprints** and choose the Blueprint. Select the **CI Integration** tab. Here, you'll find all the CI Integrations associated with the Blueprint.
2. **Create a New CI Integration:** Click the **Create CI Integration** button.
3. **Name Your CI Integration:** Enter your desired name in the **CI Integration Name** field.\
   **Note:** The CI Integration name should be identical to the corresponding Artifact name for consistency.
4. **Select Registration Type:** Choose between **Environment Name** and **Release Stream.**
5. **Set Global Access:** If you have multiple blueprints, enabling this option allows your CI Integration to be accessible across all Blueprints.
6. **Configure Advanced Options:** Under the **Advanced Options** section, you can configure the promotion hierarchy by selecting the **Promotion Workflow** to define the desired workflow for promoting artifacts. Additionally, you can classify artifacts by choosing the appropriate **CI Rule.**
7. **Finalize Creation:** Click **Create** to finish setting up your CI Integration. 

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/73b1efd-image.png">
  Click on the image to expand
</Image>

The new CI Integration will appear under the '**CI Integration**' tab.

## How to Configure Container Registry with CI Integration?

1. Open **Blueprints** and choose the Blueprint that contains the environment.
2. Select the **Environments** tab and select the Environment
3. Select the **Resource Center** tab and select the required **Service** type resource.
4. Go to the **Spec** tab to **edit** the service JSON.
5. In the code snippet, under "release" > "build", specify the Container Registry Name for `artifactory` and the CI Integration Name for the `name`.
   ```
   "build": {  
       "artifactory": "<Container-Registry-Name>",  
       "name": "<CI-Integration-Name>"
   };
   ```
6. Click **Save Changes.**

## How to Push an Artifact?

1. **Access the CI Integration Details Page:** Navigate to the CI Integration page where you intend to push the artifact.
2. **Select the Release Stream or Environment:** Locate the Release Stream or Environment where you want to push the artifact. Click the **Push Artifact** icon found under the **Actions** column.
3. **Push the Artifact:** In the pop-up window that appears, the Facetsctl command required to push your artifact will be displayed.\
   When pushing an artifact, make sure to use the name you provided while creating the Container Registry for the `artifactory` parameter in the `facetsctl push` command.
   ```
   facetsctl push -i <image_name_here> -a fe-app --registration-type RELEASE_STREAM
    --registration-value QA -e <external_id_here> -d <your_build_description> 
   --artifactory <Container-Registry-Name>
   ```
4. For a comprehensive understanding and proper usage of the push command, make sure to refer to the [Facets CLI](https://readme.facets.cloud/docs/command-line-tool-for-facets) documentation.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/38f85f4-image.png">
  Click on the image to expand
</Image>

You have successfully pushed an artifact.

## How to Promote an Artifact?

1. **Choose the Artifact:** Locate the Environment or Release Stream containing the artifact you wish to promote, then click the **Promote Artifact** icon in the **Actions** column.
2. **Promote the Artifact:** In the pop-up window that appears, click **Promote.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/06e27d2-image.png">
  Click on the image to expand
</Image>

You have successfully promoted the artifact. To learn about creating a promotion workflow, refer to the [Creating a Promotion Workflow](https://readme.facets.cloud/docs/creating-a-promotion-workflow) documentation.

## Related Guide

* [CI Integration](https://readme.facets.cloud/docs/artifacts)
* [Creating CI Rules](doc:ci-rules)
