---
title: Creating a CI Integration
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
This document provides a step-by-step guide for creating a CI Integration.

## Create a CI Integration

1. **Access the CI Integration Page:** From the dashboard, click on **Artifacts**, then select **CI Integration.** Here, you'll find all the CI Integrations created within the Facets Control Plane.
2. **Create a New CI Integration:** Click the **Create CI Integration** button.
3. **Name Your CI Integration:** Enter your desired name in the **CI Integration Name** field.\
   **Note:** The CI Integration name should be identical to the corresponding Artifact name for consistency.
4. **Select Registration Type:** Choose between **Environment Name** and **Release Stream.**
5. **Set Global Access:** If you have multiple blueprints, enabling this option allows your CI Integration to be accessible across all Blueprints.
6. **Configure Advanced Options:** Under the **Advanced Options** section, you can configure the promotion hierarchy by selecting the **Promotion Workflow** to define the desired workflow for promoting artifacts. Additionally, you can classify artifacts by choosing the appropriate **CI Rule.**
7. **Finalize Creation:** Click **Create** to finish setting up your CI Integration. 

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/c92f930-CI_Integration.gif">
  Click on the image to expand
</Image>

The new CI Integration will appear under the '**CI Integration**' tab.

## Configuring Container Registry with CI Integration

1. Navigate to **Blueprint > Blueprint Designer** and select the required **Service** type resource.
2. Go to the **Spec** tab to **edit** the service JSON.
3. In the code snippet, under "release" > "build", specify the Container Registry Name for `artifactory` and the CI Integration Name for the `name`.
   ```
   "build": {  
       "artifactory": "<Container-Registry-Name>",  
       "name": "<CI-Integration-Name>"
   };
   ```
4. Click **Save Changes.**

## Pushing an Artifact

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

<Image alt="Push an Artifact" align="center" width="450px" border={true} src="https://files.readme.io/04e1332-image.png">
  Click on the image to expand
</Image>

You have successfully pushed an artifact.

## Promoting an Artifact

1. **Choose the Artifact:** Locate the Environment or Release Stream containing the artifact you wish to promote, then click the **Promote Artifact** icon in the **Actions** column.
2. **Promote the Artifact:** In the pop-up window that appears, click **Promote.**

<Image alt="Promote an Artifact" align="center" width="450px" border={true} src="https://files.readme.io/d83d64d-image.png">
  Click on the image to expand
</Image>

You have successfully promoted the artifact. To learn about creating a promotion workflow, refer to the [Creating a Promotion Workflow](https://readme.facets.cloud/docs/creating-a-promotion-workflow) documentation.

## Related Guide

* [CI Integration](https://readme.facets.cloud/docs/artifacts)
* [Creating CI Rules](doc:ci-rules)
