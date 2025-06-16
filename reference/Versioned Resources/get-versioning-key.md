---
title: Get Versioning Key for a Resource
excerpt: getArtifactsByResourceNameAndResourceType
api:
  file: deployment-controller.json
  operationId: get-versioning-key
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
  pages:
    - type: endpoint
      slug: get-list-of-n-artifacts
      title: Get list of "N" artifacts
---
> 🚧 Your Control Plane URL will vary
>
> The Control Plane URL, denoted as <code>YOUR\_CP\_URL</code> for this API reference document is [https://facetsdemo.console.facets.cloud](https://facetsdemo.console.facets.cloud).\
> Replace that with the Control Plane URL unique to your account.

## API Endpoint

Any versioned resources will have a  `versioningKey` that is uniquely associated with that resource.

This API processes a `GET` request to fetch the details for a given environment, resource type and resource name. 

```text Hover on the Text and Click the Notepad icon to Copy
https://{YOUR_CP_URL}/cc-ui/v1/artifacts/cluster/{clusterId}/resourceType/{resourceType}/resourceName/{resourceName}
```

* This API endpoint has three **path parameters**, `clusterID`, `resourceType` and `resourceName`.

### **Path parameters**

* `clusterId` of type `String` is the unique ID for the environment where you want to perform a rollback. You can find this ID in the Environment Overview screen in Facets UI.
* `resourceType` of type `String` is the defined type of resource. This should be the same as it is defined in your blueprint.
* `resourceName` of type `String` is the name of the resource. 

## **Authenticate your API request**

To learn more about how to generate a basic authentication token for use with Facets API requests, check [Authentication Setup](ref:authentication-setup).

> 📘
>
> Facets API uses Basic Authentication.

## Generate a Sample Request ➡️
