---
title: Destroying and Deleting an Environment
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
This guide will walk through the steps to destroy and delete an existing environment through the Facets Control Plane.

## How to Destroy an Environment?

This guide outlines the process of destroying an existing environment. If you wish to remove/delete the environment from the Control Plane, refer to the [deletion section](https://readme.facets.cloud/docs/destroying-and-deleting-an-environment#how-to-delete-an-environment) of the documentation.

1. Navigate to **Blueprints > List** and choose the Blueprint that contains the environment you intend to destroy.
2. Select the specific Environment and navigate to **Environment > Releases.**
3. Click the **Destroy** button in the top right corner or click on the ellipsis icon from the top right corner and select **Destroy.**
4. In the pop-up, enter the name of the Environment and click **Confirm.**

**Note:** This will delete the Kubernetes cluster and its dependent infra resources.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/70d7468-destroy.gif">
  Click on the image to expand
</Image>

You have successfully destroyed an environment.

## How to Delete an Environment?

To completely delete the environment and remove it from the Control plane:

1. Navigate to **Blueprints > Environments** and click the **Delete** icon beside the environment you wish to delete.\
   **Note:** An environment can only be deleted after it has been [destroyed](https://readme.facets.cloud/docs/destroying-and-deleting-an-environment#how-to-destroy-an-environment).
2. In the pop-up, enter the name of the Environment and click **Confirm.**

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/2cc8ce1-delete.gif">
  Click on the image to expand
</Image>

You have successfully deleted an environment.

## FAQ

### 1. What happens when I destroy an environment?

When you destroy an environment, the Kubernetes cluster and its dependent infrastructure resources are deleted. However, the environment remains listed in the Control Plane and can be launched again later.

### 2. Can I delete an environment that has not been destroyed?

No, an environment must be destroyed before it can be deleted from the Control Plane.

### 3. Can an environment be destroyed if it is in a LAUNCHING or STOPPED state?

No, an environment cannot be destroyed if it is in either the LAUNCHING or STOPPED state. The system requires the environment to be running to permit its destruction.

### 4. Why can't I destroy my environment?

An environment cannot be destroyed if it is in the following states: LAUNCHING, SCALING\_UP, SCALING\_DOWN, DESTROYING, or STOPPED. This is to prevent any unintended consequences.

### 5. What state is an environment in after it has been destroyed?

After an environment has been successfully destroyed, it is placed in the STOPPED state. This means that all its operations are halted and it will not be functional until it is relaunched.
