---
title: Attach Image
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
This document serves as a detailed guide on managing and deploying container images using Facets.

## How to Attach an Image to a Service Resource?

1. Open the **Projects** tab and select the required project.
2. In the **Blueprint** tab, select the required service resource and choose **Overview** from the dropdown. 
3. Select the **Images** tab.
4. Click on the **edit icon** beside the **Current Strategy.**
5. Facets offers three CI/CD strategies:
   1. **Set a default static image across all environments.**
   2. **Manually attach images for this service in all environments.**
   3. **Use the CI/CD workflow set at the project level.**

### Set a Default Static Image Across All Environments

1. Select **Set a default static image across all environments.**
2. Specify the **Default Image URL.** This image will be deployed for all environments in this project.
3. Click **Save Changes.**

You have successfully attached the image to all the environments. 

### Manually Attach Images for this Service in All Environments

1. Select **Manually Attach Images for This Service in All Environments** and click **Save Changes.**
2. In the **Images** tab, you will find all the environments displayed as cards.
3. Click on **Attach Image** in an environment card. 
4. The Attach Image modal appears.
   1. Here, you can choose to **Select Image** or **Specify URL.**
   2. If you choose to select an image, select the **Container Registry, Repository, **and** Tag.**
   3. If you choose to specify the URL, select the **Container Registry** and mention the **Image URL.**
   4. Click **Attach.**

You have successfully attached the image to that environment. Repeat this process for all the remaining environments.

### Use the CI/CD Workflow Set at the Project Level

This option allows you to use the CI/CD workflow set at the project level. Based on the workflow set in the CI/CD, you will be able to attach images to the environment.

1. Select **Use the CI/CD Workflow Set at the Project Level.** 
2. Click **Save Changes.**  
   This will display the CI/CD set at the projects level in the images tab. 
3. To attach an image, click on the **Attach Image** button. 
4. The **Attach Image** modal appears.
   1. Here, you can choose to **Select Image** or **Specify URL.**
   2. If you choose to select an image, select the **Container Registry, Repository, **and** Tag.**
   3. If you choose to specify the URL, select the **Container Registry** and mention the **Image URL.**
   4. Click **Attach.**

You have successfully attached the image.

## How to Register and Push images using CLI?

Facets allows you to register and push images to the container registries using FacetsCTL.

1. Open the **Projects** tab and select the required project.
2. In the **Blueprint** tab, select the required service resource and choose **Overview** from the dropdown. 
3. Select the **Images** tab.
4. Under **Use CLI,** select the desired **Container Registry** where the updated image must be registered or pushed.
5. If not already installed, execute the command in **Step: 1** to **Install FacetsCTL.**
6. Execute the command in **Step: 2** to **Integrate the Image.** Update the values  such as `DOCKER_IMAGE_URL`and `TOKEN`. 
7. Toggle off **Push Image** to only register the image, or leave it on to register and push the image to the container registry.

## FAQ

### 1. Why do I need to add my container image to a container registry?

Adding your image to a container registry is essential because it allows the image to be stored in a central, accessible location. This ensures that the image can be pulled and used during the deployment of your application.

### 2. What happens if I turn off the "Push Image" toggle?

If you turn off the "Push Image" toggle, the image will only be registered in the container registry but not pushed. This means the image data won't be uploaded, and the deployment process will not be able to pull the image, causing your deployment to fail.

### 3. Can I deploy my application if I only register the image and do not push it?

No, you cannot deploy your application if the image is only registered but not pushed.

## Related Guides

- [CI/CD Workflow](https://readme.facets.cloud/docs/cicd-workflow)
- [Container Registries](https://readme.facets.cloud/docs/container-registries)