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

1. Navigate to the **Releases** tab and click on the **Release** button.
2. In the modal that appears, select **Full Release** and click **Apply.**

You have successfully performed a release. Refer to the [Performing Releases](https://readme.facets.cloud/docs/performing-releases) documentation to know more about it.

## How to access the application using Ingress?

You have two options:

1. Navigate to the **Resource Center** and choose the Service linked to the Ingress. 
   1. In the **Kubernetes** tab, look for the **Ingress Rules** widget, where you will find the link to access the application.
2. Alternatively, navigate to the **Resource Center** and select the Ingress resource. 
   1. In the **Overview** tab, look for the **Interfaces** widget. 
   2. If multiple resources have been linked to this Ingress, select the resource in the interfaces dropdown. 
   3. Here, you'll find the **host,** which you can use to access the application.

Great, now that the application is up and running, the next crucial step is indeed to [monitor the deployed application.](doc:monitoring-your-deployed-application)
