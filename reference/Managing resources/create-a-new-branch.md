---
title: Create a New Branch
excerpt: ''
api:
  file: deployment-controller.json
  operationId: create-a-new-branch
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

This API processes a `POST` request to create a new branch in the Blueprint.

```text Hover on the Text and Click the Notepad icon to Copy
https://{YOUR_CP_URL}/cc-ui/v1/designer/{stackName}/{branch}/create-branch
```

* This API endpoint has two **path parameter**, `stackName` and `branch`.

### **Path parameters**

* `stackName` of type `String` is the name of the Blueprint where you want to create a branch.
* `branch` of type `String` is the name of the branch.

## **Authenticate your API request**

To learn more about how to generate a basic authentication token for use with Facets API requests, check [Authentication Setup](ref:authentication-setup).

> 📘
>
> Facets API uses Basic Authentication.

## Generate a Sample Request ➡️
