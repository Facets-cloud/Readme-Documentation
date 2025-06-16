---
title: Expanding a PVC
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
This guide is designed to assist you in managing your PVC utilization effectively. If you encounter an alert indicating that your PVC utilization has exceeded a specified limit, it may indicate that you need to resize your PVC. 

## When do you need to expand the PVC?

You might need to expand the PVC when you find the following error.

**Example:** 

`CRITICAL Alert: [Critical] Kubernetes Volume disk space < 15% available - [ 1.36956787109375 ](asi-uat-facets)`

<Image alt="Click on the image to expand" align="center" border={true} src="https://files.readme.io/dbebf23-image.png">
  Click on the image to expand
</Image>

The following sections will provide a step-by-step walkthrough on how to examine and expand a PVC volume accordingly.

## Prerequisites

Before you start, download the Kubeconfig file from the relevant **Environment Overview** page and set it as the active configuration in your terminal using the following command:

```Text BASH
export KUBECONFIG=~/path-to-file/downloaded-kubeconfig
```

## How to Check Disk Utilization?

1. Download the script file from the link provided in this [gist](https://gist.github.com/redmcg/60cfff7bca6f32969188008ad4a44c9a) and save it as **`kubedf.`**
2. Run the **`kubedf`** command to display the usage of all disks. 
3. If you are interested in a specific disk, filter the results using the **`grep`** command.

## How to Resize PVCs in kubernetes?

1. Open the terminal and execute the following command:
   ```Text BASH
   kubectl get pvc <PVC_name>
   ```
   Ensure the **Status** of the PVC you plan to resize is either in a **Bound** or **Available** state.
2. Determine the new size you want for the PVC.
3. To resize the PVC, execute the following command:
   ```Text BASH
   kubectl patch pvc \<PVC_name> -p '{"spec":{"resources":{"requests":{"storage":"\<new_size>"}}}}'
   ```
   where `<PVC_name>` is the name of the PVC and `<new_size>` is the intended new size.
4. Confirm the resizing by running the following command:
   ```Text BASH
   kubectl describe pvc <PVC_name>
   ```
   The **Capacity** field should display the new size. 
5. Ensure that the pod using this PVC is functioning correctly after the resize.

> 📘
>
> 1. For safety, make sure the pod utilizing this PVC runs in a stateful set or deployment with a single replica to avoid data loss.
> 2. We recommend backing up the data in the PV before making any modifications.
> 3. Check the compatibility of the new size with the storage class and the underlying storage system.

## How to resize PVCs in Azure?

In Azure, there are two methods to resize PVCs that utilize Azure Managed Disks:

1. Resizing with the LiveResize preview feature.
2. Resizing with an associated period of downtime.

Resizing PVCs without downtime is possible if either the VM scale sets used for the nodes are supported or the LiveResize preview feature is enabled. If these options are not available, resizing the PVC will require a period of downtime.

### How to Resize using the LiveResize preview feature?

#### Supported VM SKU's

**Note:** Ensure that the SKU name and Region are available (refer to the provided [sheet](https://docs.google.com/spreadsheets/d/1l1rRJ5ZL6Lff5C7KaZ_20gH3tAdwpSM5bgAmnSxOYu0/edit#gid=1085460280) for details) before proceeding. Without these, the utilization of the LiveResize preview feature for resizing is not possible. In such cases, you will need to proceed with Resizing with an associated period of downtime.

#### Enabling LiveResize preview

To enable the LiveResize feature, run the following commands:

1. Verify if the LiveResize feature is already enabled by running: 
   ```
   az feature show --namespace Microsoft.Compute --name LiveResize
   ```
2. Register the feature flag by running: 
   ```
   az feature register --namespace Microsoft.Compute --name LiveResize
   ```

After enabling the LiveResize feature, follow the steps in the **How to Resize the PVC?** section.

### How to Resize with an associated period of downtime?

To Resize PVCs with an associated period of downtime, refer to the official [Expand Azure disk PVC with downtime](https://github.com/kubernetes-sigs/azuredisk-csi-driver/blob/master/docs/known-issues/sizegrow.md) documentation.

## References

* [Use the Azure Disk Container Storage Interface (CSI) driver in Azure Kubernetes Service (AKS)](https://learn.microsoft.com/en-us/azure/aks/azure-disk-csi#resize-a-persistent-volume-without-downtime-preview)
* [Expanding without downtime classic VM SKU support](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/expand-disks?tabs=ubuntu#expanding-without-downtime-classic-vm-sku-support)
