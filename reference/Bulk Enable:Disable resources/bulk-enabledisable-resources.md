---
title: Bulk Enable/Disable Resources
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
Facets provides users with the ability to enable and disable the resources in bulk using its API.

## Using REST APIs to Enable/Disable Resources in an Environment

Let's first understand the logic we are going to use to Enable/Disable Resources in an Environment.

* Facets will use the `clusterId` to identify the Environment where you want to update the status of the resources.

### Steps to Enable/Disable Resources

Perform a REST API `PUT` call using the `clusterId` parameter as specified in the "[Enable/Disable Resources in an Environment](https://readme.facets.cloud/reference/enabledisable-resources-in-an-environment)" documentation.

**Response:**

You should get a response confirming that the resources have been updated.

## Using REST APIs to Enable/Disable Resources in a Blueprint

Let's first understand the logic we are going to use to Enable/Disable Resources in a Blueprint.

* Facets will use the `stackName` to identify the Blueprint where you want to update the status of the resources.

### Steps to Enable/Disable Resources

Perform a REST API `PUT` call using the `stackName` parameter as specified in the "[Enable/Disable Resources in a Blueprint](https://readme.facets.cloud/reference/enabledisable-resources-in-a-blueprint)" documentation.

**Response:**

You should get a response confirming that the resources have been updated.
