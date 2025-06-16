---
title: Canary Deployment
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
Facets now supports Argo Rollouts-Canary Deployment for Service resources, enabling incremental rollouts of changes. This strategy allows you to deploy updates to a small subset of your infrastructure initially, validate the changes, and then fully deploy them across your entire infrastructure, thereby reducing the risk associated with new deployments.

## Prerequisites

* Ability to modify/override resource JSON.
* Ability to perform Releases.
* `APPLICATION_DEPLOYMENT_PROMOTE` permission to promote the preview changes.

## Setting the Deployment Strategy to Canary

1. Navigate to **Projects > Blueprint.** 
2. Select the specific **Service** resource JSON and select Configure from the drop-down.
3. Locate the `"strategy": { "type": "RollingUpdate"}` parameter and modify it to `"strategy": { "type": "Canary"}`

```
{
  "release": {
  	"strategy": {
          "type": "Canary"
    }
  }
}
```

4. Save your changes and [perform a Release](https://readme.facets.cloud/docs/performing-releases) to enable Canary Deployment for this resource.

**Note:** When you release artifact and configuration changes for a service with Canary deployment strategy, they will be accessible in a preview state. 

## Configuring the Canary Strategy

* **Understand the Traffic Manager:** We support Canary using Argo Rollouts, and we support all the traffic managers supported by Argo Rollouts. In this use case, we will use Istio as our traffic manager.
* **Learn About Traffic Splitting:** We are using subset-level traffic splitting. To know more about this, refer to the [Istio documentation.](https://argo-rollouts.readthedocs.io/en/stable/features/traffic-management/istio/#subset-level-traffic-splitting)

### Setting up the traffic split

1. Configure the service JSON and set up the traffic split.
2. Insert the following `"steps"` configuration in the `"canary_strategy"` section of your configuration file.
3. Configure the `"setWeight"` and `"pause"` parameters.
   1. **setWeight:** This parameter specifies the percentage of traffic that should be directed to the Canary version of the service.
   2. **pause:** This parameter indicates a pause in the rollout process.

```Text JSON
"steps": [
   {
     "setWeight": 10
   },
    {
     "pause": {}
   }
 ],
```
```Text Example
"strategy":{
            "type":"Canary",
            "canary_strategy":{
               "enable_service":false,
               "steps":[
                  {
                     "setWeight":10
                  },
                  {
                     "pause":{
                        
                     }
                  }
               ],
```

In this example, we only are configuring only one `step` and `pause`(wait). 

* `"setWeight": 10` refers to 10% of the traffic going to the Canary.
* The `pause` value is empty because it signifies an indefinite pause, allowing for manual intervention to promote the Canary version or make further adjustments before continuing with the rollout.

### Configuring the traffic manager (istio)

1. **Reference the Destination Rule and Virtual Service:** Add the following configuration to reference the destination rule and virtual service.\
   To know more about Destination Rule and Virtual Service, refer to the [Istio documentation.](https://argo-rollouts.readthedocs.io/en/stable/features/traffic-management/istio/#subset-level-traffic-splitting)
   1. **Destination Rule:** This defines policies that apply to traffic intended for a service after routing has occurred. These policies determine how requests are handled once they reach the service.
   2. **Virtual Service:** This defines how requests to a service are routed within an Istio service mesh. It specifies the routing rules and the service versions (subsets) the traffic should be directed to..

```Text Example JSON
  "traffic_routing": {
    "istio": {
      "destinationRule": {
        "name": "canary-destination",
        "canarySubsetName": "canary",
        "stableSubsetName": "stable"
      },
      "virtualService": {
        "name": "virtualservice-canary",
        "routes": [
          "primary"
        ]
      }
    }
  }
```

2. **Create the Destination Rule and the Virtual Service:** Define the `destination_rule` and the `virtual_service` in the resource JSON. 

```Text Example JSON
  "destination_rule": {
    "apiVersion": "networking.istio.io/v1alpha3",
    "kind": "DestinationRule",
    "metadata": {
      "name": "canary-destination"
    },
    "spec": {
      "host": "canary",
      "subsets": [
        {
          "name": "canary",
          "labels": {
            "app": "example-canary-service"
          }
        },
        {
          "name": "stable",
          "labels": {
            "app": "example-canary-service"
          }
        }
      ]
    }
  },
  "virtual_service": {
    "apiVersion": "networking.istio.io/v1alpha3",
    "kind": "VirtualService",
    "metadata": {
      "name": "virtualservice-canary"
    },
    "spec": {
      "hosts": [
        "example-canary-service.default.svc.cluster.local"
      ],
      "http": [
        {
          "name": "primary",
          "route": [
            {
              "destination": {
                "host": "example-canary-service",
                "subset": "stable"
              },
              "weight": 90
            },
            {
              "destination": {
                "host": "example-canary-service",
                "subset": "canary"
              },
              "weight": 10
            }
          ]
        }
      ]
    }
  }
```

**Note:** Make sure the `"labels": {"app": "example-canary-service"}` matches the name of the service JSON. For a complete overview of the configuration, refer to the [sample JSON.](https://facets-cloud.github.io/facets-schemas/readme-samples/canary.json)

* Save your changes and [perform a Release](https://readme.facets.cloud/docs/performing-releases). 

## Preview

A preview icon will appear in the Artifact table, Blueprint table, Configuration table, and even in Kubernetes pods when there are available changes for a Canary resource.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/be24121dfe7cf650aca3f25bd50dbc9c5cb0845e9e665e72a4b407ddf20c6f3d-canary1.gif">
  Click on the image to expand
</Image>

## Promote

You can choose to promote or abort the preview changes from Resource Overview page.

1. Navigate to **Resource Overview** page and click on the elipsis icon on the top right corner.
2. Select either **Promote** or **Abort:**
   1. **Promote:** This deploys the Canary changes to the production environment, making them live for all users.
   2. **Abort:** Rolls back the Canary changes and returns the system to its previous state before the Canary deployment.\
      **Note:** This action will revert all pods to the stable version. Any release-triggered changes (Blueprint, Artifact, and configuration) must also be rolled back. Once the rollback is complete, you will need to trigger a release to deploy the updates.
3. Now, click **Confirm.**

This process allows you to control the deployment, ensuring that only stable and verified changes make it to the production environment.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/3c74788f00b49e656e6a7829f909394d46bcd4e72027a62147d66982a9b48805-image.png">
  Click on the image to expand
</Image>
