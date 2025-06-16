---
title: Accessing the Live Application
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
After successfully linking your resources, the next step is to perform a release. 

To perform a release:

1. Navigate to **Environment > Releases** from the navigation pane.
2. Click on the **Release** button.
3. In the modal that appears, select **Full Release** and click **Apply.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/194f28f-pet_-_release.gif">
  Click on the image to expand
</Image>

You have successfully performed a release. Refer to the [Performing Releases](https://readme.facets.cloud/docs/performing-releases) documentation to know more about it.

## How to access the application using Ingress?

You have two options:

1. Navigate to **Environment > Resource Center** and choose the Service linked to the Ingress. 

   1. Then, in the **Kubernetes** tab, look for the **Ingress Rules** widget, where you will find the link to access the application.

      <Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/c2e08d9-image.png">
        Click on the image to expand
      </Image>
2. Alternatively, navigate to **Environment > Resource Center** and select the Ingress resource. 

   1. In the **Overview** tab, look for the **Interfaces** widget. 
   2. Here, you will find the **host,** which you can use to access the application.

      <Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/74536e9-image.png">
        Click on the image to expand
      </Image>

Great, now that the application is up and running, the next crucial step is indeed to [monitor the deployed application.](doc:pet-clinic-monitoring-your-deployed-application)
