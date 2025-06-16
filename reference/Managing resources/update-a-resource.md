---
title: Update a Resource
excerpt: ''
api:
  file: deployment-controller.json
  operationId: update-a-resource
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧 Your Control Plane URL will vary
> 
> The Control Plane URL, denoted as <code>YOUR_CP_URL</code> for this API reference document is <https://facetsdemo.console.facets.cloud>.  
> Replace that with the Control Plane URL unique to your account.

**Note:** If any changes are made to the remote Git repository, please utilize the '[Get Blueprint Resources](https://readme.facets.cloud/reference/get-blueprint-resources)' API to synchronize and incorporate all the modifications.

## API Endpoint

This API processes a `PUT` request to update the resource in the Blueprint.

```text Hover on the Text and Click the Notepad icon to Copy
https://{YOUR_CP_URL}/cc-ui/v1/designer/{stackName}/branch/{branch}
```

- This API endpoint has two **path parameter**, `stackName` and `branch`.

### **Path parameters**

- `stackName` of type `String` is the name of the Blueprint.
- `branch` of type `String` is the name of the branch where the resource is located.

### **Body parameters**

- `directory`, `filename`, `resourceName` and `resourceType` are variables of type `String`.
- `content` is an object that will take `key:value` pairs of type `String`.

```json resource
[
  {
    "content": {},
    "directory": "string",
    "filename": "string",
    "resourceName": "string",
    "resourceType": "string"
  }
]
```
```json Example
[
  {
    "content": {
      "flavor": "default",
      "metadata": {
        "labels": {}
      }
    },
    "directory": "service/instances",
    "filename": "billing.json",
    "resourceName": "billing",
    "resourceType": "service"
  }
]
```

## **Authenticate your API request**

To learn more about how to generate a basic authentication token for use with Facets API requests, check [Authentication Setup](ref:authentication-setup).

> 📘 
> 
> Facets API uses Basic Authentication.

## Generate a Sample Request ➡️