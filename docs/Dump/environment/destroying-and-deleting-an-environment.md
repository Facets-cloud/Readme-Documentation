---
title: Destroying and Deleting an Environment
excerpt: ''
deprecated: false
hidden: true
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

1. Open **Projects** tab and choose the Project that contains the environment.
2. Select the **Environments** tab and select the Environment you intend to destroy.
3. Click the **Destroy** button in the top right corner.
4. In the pop-up, enter 'Confirm' and click **Confirm.**

**Note:** This will delete the Kubernetes cluster and its dependent infra resources.

You have successfully destroyed an environment.

## How to Delete an Environment?

To completely delete the environment and remove it from the Control plane:

1. Open **Projects** tab and choose the Project that contains the environment.
2. Select the **Environments** tab and select the Environment you intend to delete.
3. Select the **Environment Settings** tab and click on **Danger Zone.**
4. Click Delete Environment.\
   **Note:** An environment can only be deleted after it has been [destroyed](https://readme.facets.cloud/docs/destroying-and-deleting-an-environment#how-to-destroy-an-environment).
5. In the pop-up, enter 'Confirm' and click **Confirm.**

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
