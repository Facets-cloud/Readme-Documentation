---
title: Getting Started - Petclinic Project
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
## Overview of Starter Project

The **Facets Starter Project** offers a quick way to deploy and manage web applications, using the Petclinic application as a practical example. This getting started guide will help you understand how Facets can significantly enhance the workflows of both operations and development teams compared to traditional methods.

The Starter Project comes preconfigured with a project, linked resources, and an environment, making it ready for deployment. The **goal is to deploy the Pet Clinic application** on Facets.cloud and make it globally accessible.

## Deploy your first application in Facets within minutes

The **Starter Project** is automatically available as a preconfigured project in your Facets Control Plane upon receiving access. It includes the following pre-created components:

1. A Project named **Starter Project.**
2. **Infrastructure ready in the blueprint**: A set of resources, including a service for the application, a Postgres database for persistent data storage, and an ingress for public access. These resources are already connected to interact seamlessly.
3. **An Environment:** A pre-created environment ready for deployment. 
   1. To Launch the environment, navigate to Environments Tab and click on Launch button against the environment that needs to be launched. 
   2. Link your own cloud (optional) and launch the preconfigured environment to deploy the resources created in the blueprint.
4. **Accessing the Live Application:** Once the environment is in running state and the resources are deployed, you will be able to access and interact with your application in real-time globally. The URL for the petclinic application will be available in the Resource Center -> Service -> Live Tab.
5. **Monitoring the deployed application:** Facets includes comprehensive monitoring and logging tools, giving you visibility into the performance and health of any application. Kubernetes Dashboard and other monitoring dashboards for a particular resource can be accessed in the same Live Tab mentioned above. 

Below video demonstrates on how a user can create a project, add resources in the blueprint, configure them and launch an environment to deploy enabled resources in blueprint. 

_Note: For starter project, most of the steps are already done on behalf of the user. _

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F5C5EqdOg8C8%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D5C5EqdOg8C8&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2F5C5EqdOg8C8%2Fhqdefault.jpg&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=5C5EqdOg8C8",
  "title": "Deploying an application in Facets",
  "favicon": "https://www.youtube.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/5C5EqdOg8C8/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=5C5EqdOg8C8",
  "typeOfEmbed": "jsfiddle"
}
[/block]


The forthcoming sections are designed to provide detailed instructions and additional context, equipping you with the necessary tools to fully harness the key features of Facets by engaging in this practical experience.

Lets discuss in detail how one can monitor the deployed application in Facets and what are the other details that can be seen through Facets.