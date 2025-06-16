---
title: Trigger a Release
excerpt: This page documents the API endpoint to Trigger a Release
api:
  file: deployment-controller.json
  operationId: trigger-a-release
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
> 🚧 Your Control Plane URL will vary
>
> The Control Plane URL, denoted as <code>YOUR\_CP\_URL</code> for this API reference document is [https://facetsdemo.console.facets.cloud.](https://facetsdemo.console.facets.cloud.)\
> Replace that with the Control Plane URL unique to your account.

## API Endpoint

This API processes a <code>PUT</code> request to trigger a release on a selected unique cluster.  

```text Hover on the Text and Click the Notepad icon to Copy
https://{YOUR_CP_URL}/cc-ui/v1/clusters/{clusterId}/deployments/release
```

* This API endpoint has two **path parameters**, <code>YOUR\_CP\_URL</code>, and <code>clusterId</code>.
* There are also two **query parameters**, <code>forceRelease</code>, and <code>withRefresh</code>.

### **Path parameters**

* <code>YOUR\_CP\_URL</code> of type <code>String</code>, is the Control Plane URL specific to your account.
* <code>clusterId</code> of type <code>String</code>, is the unique ID for the cluster where you want to make a release. You can find this ID in the Environment Overview screen in Facets UI.

### **Query parameters**

There are two required keys for making this API call: 

* <code>forceRelease</code> of type <code>Boolean</code> with the default value <code>false</code>. 

> 📘
>
> <code>forceRelease</code> can be used to force trigger a release regardless of any changes to the blueprint or application versions.

* <code>withRefresh</code>  of type <code>Boolean</code> with the default value <code>true</code>. Note that <code>true</code> will take considerably more time to finish deploying.

> 📘 withRefresh is used for Drift detection
>
> Drift detection enables you to detect whether the environment differs, or has drifted, from its blueprint specification. In case the value is set to "true", the deployment will try to match the environment configuration as defined in the blueprint if it has drifted from it.

## **Authenticate your API request**

To learn more about how to generate a basic authentication token for use with Facets API requests, check [Authentication Setup](ref:authentication-setup).

> 📘 Facets API uses Basic Authentication.

## Generate a Sample Request ➡️
