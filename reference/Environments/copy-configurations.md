---
title: Copy Environment Configurations
excerpt: ''
api:
  file: deployment-controller.json
  operationId: copy-configurations
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧 Your Control Plane URL will vary
>
> The Control Plane URL, denoted as <code>YOUR\_CP\_URL</code> for this API reference document is [https://facetsdemo.console.facets.cloud.](https://facetsdemo.console.facets.cloud.)\
> Replace that with the Control Plane URL unique to your account.

# API Endpoint

This API enables you to copy all environment configurations from one cluster(environment) to another. It includes resource configurations (overrides), secrets, variables, and environment configurations, making it easy to replicate settings across different clusters.

This API processes a PUT request to copy configurations from one cluster to another cluster.

```
https://{YOUR_CP_URL}/cc-ui/v1/clusters/{clusterId}/copy-configurations
```

* This API endpoint has two main components: `path parameters` - `YOUR_CP_URL` and `clusterId`.
* There is also a `body parameter` containing the source cluster information.

### Path parameters

* `YOUR_CP_URL` of type `String`, is the Control Plane URL specific to your account.
* `clusterId` of type `String`, is the unique ID for the destination cluster where you want to copy the configurations to. You can find this ID in the Environment Overview screen in Facets UI.

### Body parameters

There is one required parameter for making this API call:

* `sourceClusterId` of type `String`, represents the cluster ID from which configurations will be copied.
* *Note: The source cluster ID should be different from the destination cluster ID and must be a valid cluster in your environment.*

### Response Status Codes

The API can return the following status codes:

* `200 OK` - Request processed successfully
* `201 Created` - Configurations copied successfully
* `401 Unauthorized` - Missing or invalid authentication credentials
* `403 Forbidden` - Insufficient permissions to access clusters
* `404 Not Found` - Specified cluster(s) not found

### Authenticate your API request

To learn more about how to generate a basic authentication token for use with Facets API requests, check [Authentication Setup](https://readme.facets.cloud/reference/authentication-setup).\
*Note:  Facets API uses Basic Authentication.*

### Generate a Sample Request ➕

Here's an example of how to use this API:

```bash
curl -X PUT "https://{YOUR_CP_URL}/cc-ui/v1/clusters/{destination_clusterId}/copy-configurations" \
     -H "accept: */*" \
     -H "Content-Type: application/json" \
     -d '{"sourceClusterId": " "}'
```

### Response Example

A successful response will return:

```json
true
```
