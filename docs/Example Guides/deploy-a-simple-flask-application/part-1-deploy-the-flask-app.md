---
title: Part 1 - Write and Deploy the App
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
# Step 1: Create a blueprint directory and files.

The starting point of interacting with Facets Control Plane is the creation of a <Glossary>blueprint</Glossary>. A blueprint is a git version controlled collection of json files. Each of this json files represents an intent and defines the resources required and their configurations and dependencies. 

For our demo application, we only need an application instance and an ingress to access the application from the outside world. There are 2 parts to creating a blueprint in Facets Control Plane.

1. First is the creation of json files in a pre-defined directory structure and pushing it to a git repository. 
2. The second part is using this git repository to create a blueprint on Facets console.

> 📘 The directory structure and directory names have to be in pre-defined format. Each resource type has a directory named after it. Each resource is defined by a JSON file, usually placed in the instances directory of a resource type. For example, if an application instance is needed, the directory name should be application and its json file would be placed in instances directory inside application directory

Our directory structure would look like below

![480](https://files.readme.io/1f3eda9-Screen_Shot_2022-03-30_at_9.04.04_PM.png "Screen Shot 2022-03-30 at 9.04.04 PM.png")

Create <code>features.json</code> and <code>stack.json</code> as described in [Bootstrap a Blueprint](doc:deploy-our-first-app). 

1. <code>app.json</code> - Create a file named <code>app.json</code> at <code>application/instances</code> the following content in it. This file defines all the application resource related configurations like sizing, autoscaling, load balancing etc.

```json
{
    "$schema": "https://docs.facets.cloud/schemas/application/instances/application.schema",
     "kind": "facets.modules.common.application",
     "disabled": false,
     "apiVersion": "v2",
     "metadata": {
   
     },
     "spec": {
   
      "env": {
   
      },
      "loadbalancing": {
       "rules": [
        {
         "ingress": "ingress",
         "path": "/",
         "portName" : "port5000"
        }
       ]
      },
      "permission": [],
      "release": {
       "strategy": "RollingUpdate",
       "build": {
        "image": "313496281593.dkr.ecr.us-east-1.amazonaws.com/facets/springbootsample/springboot-backend:latest"
       }
      },
      "runtime": {
       "size": {
        "value": "small",
        "namespace": "GP"
       },
       "autoscaling": {
        "cpuThreshold": "50",
        "max": 1,
        "min": 1
       },
       "ports": [{
        "name": "port5000",
        "port": 5000
       }]
      }
```

2. <code>sizing.GP.json</code> - Create a file named <code>sizing.GP.json</code> inside the <code>application/</code> and put the following content in it. This file provides T-Shirt sizing options that can be used in app.json.

```json
{
    "$schema": "https://docs.facets.cloud/schemas/application/sizing.schema",
 
    "small": {
      "podCPULimit": 1,
      "podMemoryLimit": 2
    }
  }
```

3. <code>ingress.json</code> - Create a directory named <code>ingress/instances</code>. Place <code>ingress.json</code> with the following content in it. This file defines all the ingress related resource configurations.

```json
{
    "$schema": "https://docs.facets.cloud/schemas/ingress/instances/ingress.schema",
    "apiVersion": "v2",
    "subdomains" : []
}
```

# Step 2: Launch the App

1. Push all the files to a git repository and [register](doc:deploy-our-first-app#register-the-blueprint) the blueprint in the control plane
2. Push the built using :point_down: 

<TutorialTile title="Push a Build to Facets Control Plane Manually" emoji="✈️" backgroundColor="#802f9d" slug="push-a-build-to-facets-control-plane-manually" id="638dcfb3e5003e002bee7e34" link="https://facets.readme.io/v0.5/recipes/push-a-build-to-facets-control-plane-manually" />

3. [Launch](doc:launch-an-environment) an environment
4. Test the application using the steps [here](doc:deploy-a-service#test-the-application)
