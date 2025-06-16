---
title: Get Blueprint Resources
excerpt: ''
api:
  file: deployment-controller.json
  operationId: get-blueprint-resources
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
> The Control Plane URL, denoted as <code>CP\_URL</code> for this API reference document is [https://facetsdemo.console.facets.cloud](https://facetsdemo.console.facets.cloud).\
> Replace that with the Control Plane URL unique to your account.

## API Endpoint

This API processes a `GET` request to retrieve a list of resources within the specified Blueprint and synchronize any associated changes.

```text Hover on the Text and Click the Notepad icon to Copy
https://<CP_URL>.console.facets.cloud/cc-ui/v1/designer/{stackName}/{branchName}/files
```

This API endpoint has two path parameters, `stackName` and `branch`.

## Path Parameters

* `stackName` of type String is the name of the Blueprint.
* `branch` of type String is the name of the branch.

## **Authenticate your API request**

To learn more about how to generate a basic authentication token for use with Facets API requests, check [Authentication Setup](ref:authentication-setup).

> 📘
>
> Facets API uses Basic Authentication.

## Generate a Sample Request ➡️

Fill in the mandatory parameters below to generate a sample request.
