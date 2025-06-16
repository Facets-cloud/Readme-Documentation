---
title: Integrating with CI Pipelines
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
## Step 1: Ensure `facetsctl` is installed

This step verifies that the `facetsctl` tool is installed and accessible. The command `facetsctl --version` is used to check the installed version. There are different versions of `facetsctl`, so it is important to check the version before using the tool.

If not you can view and download the latest `facetsctlv3` package from its [NPM page](https://www.npmjs.com/package/@facets-cloud/facetsctlv3). To know more about installation refer to [Installing Facets CLI](https://readme.facets.cloud/v1.4/docs/integration).

***

## Step 2: Login Using `facetsctl`

Run the following command to log in:

```bash
facetsctl login -u <USERNAME> -t <TOKEN> -f <CP_URL>
```

***

## Step 3: Initialize Artifact

Initialize the artifact based on the inputs:

- If `SERVICE_NAME` is provided:
  ```bash
  facetsctl artifact init -p <PROJECT_NAME> -s <SERVICE_NAME> -a <ARTIFACTORY_NAME>
  ```
- If `CI_NAME` is provided:
  ```
  facetsctl artifact init -p <PROJECT_NAME> -c <CI_NAME> -a <ARTIFACTORY_NAME>
  ```

The artifactory is where your container images are stored. Facets supports multiple container registries including Elastic Container Registry, Azure Container Registry, Google Artifact Registry, Google Container Registry, Nexus, Docker Hub, Jfrog and others

***

## Step 4: Push Artifact (Optional)

Push the artifact into the configured artifact repository using:

```bash
facetsctl artifact push -d <DOCKER_IMAGE_URL>
```

This step is optional, as you can choose to register an image that has already been pushed to an external repository.

***

## Step 5: Register Artifact

Register the artifact into Facets to register already pushed images from an external repository with the Facets Control Plane, making them available for use in deployments:

```bash
facetsctl artifact register -t <REGISTRATION_TYPE> -v <TARGET> -i <DOCKER_IMAGE_URL> -r <RUN_ID>
```

***

## Step 6: Sync Apps

Synchronise apps to ensure that the specified they reach their desired state using:

```
facetsctl release wait APPS -p <value> -e <value> [--sync]
```

This command will wait for the applications to reach their desired state. If the `--sync` flag is provided, a synchronisation will be triggered if the applications are out of sync.

***

## Step 7: Completion

1. Confirm all operations (`login`, `init`, `push`, `register`) are successfully completed.
2. It is important to note that if the image is only registered and not pushed, the application cannot be deployed.
3. There are two versions of the facetsctl CLI tool, v1.0.9 and v1.1.2. The commands and flags may be different in the two versions