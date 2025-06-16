---
title: Branch Creation and Resource Management
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
Facets provides users with the ability to create a branch, generate resources, and perform updates to existing resources in a blueprint using REST API calls.

Given that directly altering the master branch is not recommended, we choose to create a new branch for implementing updates. This ensures that changes are made in a controlled environment before initiating a pull request to merge them into the master branch.

## Using REST APIs to Create a Branch

Let's first understand the logic we will use to create a new branch.

* Facets uses the `stackName` parameter to identify the Blueprint where you want to create a branch.
* The`branch` parameter is used as the new branch name.

### Steps to create a branch

**Note:** Execute the `listBranches` API to update all branches from Git.

Perform a REST API `POST` call using the `branch` and `stackName` parameters as specified in the "[Create a New Branch](https://readme.facets.cloud/reference/create-a-new-branch)" documentation.

**Response:**

You should get a response confirming the creation of a new branch.

## Using REST APIs to Create a Resource

**Note:** If any changes are made to the remote Git repository, please utilize the '[Get Blueprint Resources](https://readme.facets.cloud/reference/get-blueprint-resources)' API to synchronize and incorporate all the modifications.

To create a new resource, you will need the following details:

* The `stackName` parameter is used to identify the Blueprint.
* The`branch` parameter is used to identify the branch in the Blueprint.
* The `resourceName` parameter is the name of the resource.
* The `resourceType` parameter is the type of resource.

### Steps to create a JSON resource

1. Perform a REST API `POST` call using `branch` and `stackName` parameters. 
2. Also, update values such as `resourceName` and `resourceType`.
3. Refer to the "[Create a New Resource](https://readme.facets.cloud/reference/create-a-new-resource)" documentation for additional guidance.

**Response:**

You should receive a response confirming the creation of a new resource.

## Using REST APIs to Update a Resource

To update a new resource, you will need the following details:

* The `stackName` parameter is used to identify the Blueprint.
* The`branch` parameter is used to identify the branch in the Blueprint.
* The `directory` parameter is used to identify the path to create the resource in the branch.
* The `filename` parameter is the name of the file with the extension.
* The `resourceName` parameter is the name of the resource.
* The `resourceType` parameter is the type of the resource.
* The `content` block contains the content to be added to the resource.

**Note:** The content within the `content` tag will replace the content in the resource JSON.

### Steps to update a JSON resource

1. Perform a REST API `PUT` call using `branch` and `stackName` parameters. 
2. Also, update values such as `directory`, `filename`, `resourceName`, and `resourceType`.
3. Add the `content` to be updated in the JSON file.
4. Refer to the [Update a Resource](https://readme.facets.cloud/reference/update-a-resource) documentation for additional guidance.

**Response:**

You should receive a response confirming that the resource has been updated with the provided content.
