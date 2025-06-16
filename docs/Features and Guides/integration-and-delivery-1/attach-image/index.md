---
title: Attach Image in a Service
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
## Overview

Once you've configured your project-level CD flow, you need to consume it at the service level. Facets provides flexible options for managing image deployments and promotions for individual services. This document serves as a detailed guide on managing and deploying container images of a service in Facets.

## How to Attach an Image to a Service Resource?

<Embed url="https://app.storylane.io/demo/vqccd5lqvmn8" title="CI/CD | Feb 17 12:18 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_a974a08a-4b8f-4c50-9a38-4b16f64e3892/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/vqccd5lqvmn8" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fvqccd5lqvmn8%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fvqccd5lqvmn8%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_a974a08a-4b8f-4c50-9a38-4b16f64e3892%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

1. In the **Images** Tab of any Service Resource, you can change the strategy from the edit icon.
2. Facets offers two CI/CD strategies:
   1. **Manually attach images for this service in all environments.**
   2. **Use the CI/CD workflow set at the project level.**

### Manually Attach Images for this Service in All Environments

1. Select Manually Attach Images for This Service in All Environments and click Save Changes.
2. In the **Images** tab, you will find all the environments listed and images can be manually attached to each environment. 
3. Images can be attached by either specifying the URL of the image or select the image. For selecting the image, select the container registry (from the list of CRs which are added to the control plane), select the repo and then select the tag of the image. 

You have successfully attached the image to that environment. Repeat this process for all the remaining environments.

***

### Use the CI/CD Workflow Set at the Project Level

After selecting the project CI/CD flow option in your service's Images tab, you'll see a visual representation of:

* All environments in your CD flow and current images deployed in each environment
* Available promotion paths between environments and Image status and deployment information

**Image Registration**\
When your CI pipeline builds a new image, Facets provides a command that maps this image to the correct environment based on the source branch. This command needs to be run everytime a new image is built corresponding to that branch of git repo.

```json
# Install FacetsCTL
curl -sSL https://facets-cloud.github.io/facets-schemas/scripts/fctl_install.sh | bash && source ~/.bashrc

# Set up environment variables
export DOCKER_IMAGE_URL="https://example.com/your/image"
export TOKEN="your_access_token"
export GIT_REF="your_git_branch"

# Register and push the Docker image
curl -s https://facets-cloud.github.io/facets-schemas/scripts/fctl_register.sh | bash -s -- -u <username> -c <control_plane_url> -p <project_name> -s <service_name> -a default -i "true"
```

**Integration with CI Pipeline**

* Instead of manually running the registration command each time, add the Facets command to your existing CI pipeline. 
* Each time code is committed to a configured branch, CI pipeline builds the image and with the command added in the file, image is automatically registered with the correct environment. No manual intervention required.
* Once the image is registered in the environment linked to the source branch in the CI Rule, it can be promoted to further environments based on the promotion workflow defined.

To know more about Integration with CI Pipeline, refer to the "Integrate with CI System" in Images Tab. 

<Image align="center" src="https://files.readme.io/0a400eca32e56dbf0f53079bb47f77e42f5bf576b3e147398564ba272c68aa87-Screenshot_2025-02-18_at_11.49.53_AM.png" />

***

### Use CLI to push and register the artifacts

In Facets, you can perform all the above actions using CLI commands as well. Read about it in detail in the Facets CLI Section. 

***

## FAQ

### 1. Why do I need to add my container image to a container registry?

Adding your image to a container registry is essential because it allows the image to be stored in a central, accessible location. This ensures that the image can be pulled and used during the deployment of your application.

### 2. What happens if I turn off the "Push Image" toggle?

If you turn off the "Push Image" toggle, the image will only be registered in the container registry but not pushed. This means the image data won't be uploaded, and the deployment process will not be able to pull the image, causing your deployment to fail.

### 3. Can I deploy my application if I only register the image and do not push it?

No, you cannot deploy your application if the image is only registered but not pushed.

## Related Guides

* [CI/CD Workflow](https://readme.facets.cloud/docs/cicd-workflow)
* [Container Registries](https://readme.facets.cloud/docs/container-registries)
