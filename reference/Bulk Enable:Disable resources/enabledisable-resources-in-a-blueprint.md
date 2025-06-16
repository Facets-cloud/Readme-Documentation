---
title: Enable/Disable Resources in a Blueprint
excerpt: ''
api:
  file: deployment-controller.json
  operationId: enabledisable-resources-in-a-blueprint
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
> The Control Plane URL, denoted as <code>YOUR\_CP\_URL</code> for this API reference document is [https://facetsdemo.console.facets.cloud](https://facetsdemo.console.facets.cloud).\
> Replace that with the Control Plane URL unique to your account.

## API Endpoint

This API processes a `PUT` request to update the status of the resource in an Environment.

```text Hover on the Text and Click the Notepad icon to Copy
https://{YOUR_CP_URL}/cc-ui/v1/designer/{stackName}/resource-enable-disable
```

* This API endpoint has one **path parameter**, `stackName`.

### **Path parameters**

* `stackName` parameter of type `String` is the name of the Blueprint.

### **Body parameters**

* `resourceName` and `resourceType` are the parameter of type `String`.
* Locate the `disabled: true` parameter and set the value to `true` or `false`.

**Note:** Setting `disabled` to `true` will disable the resource, while setting it to `false` will enable the resource.

```json resource
[
  {
    "disabled": true,
    "resourceName": "string",
    "resourceType": "string"
  }
]
```
```json Example
[  
  {  
    "disabled": true,
    "resourceName": "aws-crit",  
    "resourceType": "service"  
  },  
  {  
    "disabled": false,
    "resourceName": "default",
    "resourceType": "postgres"

  }  
]
```

## **Authenticate your API request**

To learn more about how to generate a basic authentication token for use with Facets API requests, check [Authentication Setup](ref:authentication-setup).

> 📘
>
> Facets API uses Basic Authentication.

## Generate a Sample Request ➡️
