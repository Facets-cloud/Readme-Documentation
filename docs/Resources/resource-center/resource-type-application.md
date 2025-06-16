---
title: Resource Type - Application
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
Resources of type Application are different from other resources. This document outlines the Resource Details page for applications.

1. Navigate to **Environment >Resources.**

<Image alt="Resources tab in left Navigation menu" width="350px" border={true} src="https://files.readme.io/21a8358-image.png">
  Resources tab in left Navigation menu
</Image>

2. Click on the resource name to view the details of the application resource.
3. On this page, you will find four tabs namely,

* Live Release
* Configuration
* Diff
* Grafana Dashboard

<Image alt="Resource Details screen" width="700px" border={true} src="https://files.readme.io/c1ed46e-image.png">
  Resource Details screen
</Image>

## Live Release

This page displays all the details regarding this live release. 

### Current Registered Artifact

The Current Registered Artifact widget displays the latest active artifact. 

1. Click the **Artifact History** button on the top right corner.

<Image alt="Artifact History navigation" width="700px" border={true} src="https://files.readme.io/03e242b-image.png">
  Artifact History navigation
</Image>

2. The **Artifact History** page appears. Here, you can view the **Currently Registered version** and **Previous Versions.**
3. Click the **Artifact rollback** icon beside the required version to roll back to that Artifact version. 

<Image alt="Artifact rollback navigation" width="700px" border={true} src="https://files.readme.io/8349d27-image.png">
  Artifact rollback navigation
</Image>

4. In the pop-up that appears, click **Confirm.**

<Image alt="Confirm Artifact Rollback pop-up" width="350px" border={true} src="https://files.readme.io/5aeff85-image.png">
  Confirm Artifact Rollback pop-up
</Image>

You have successfully performed an artifact rollback.

### Line Graphs

This depicts all the CPU, Memory, Pods, and Restarts in a line graph.

<Image alt="CPU usage graph" width="700px" border={true} src="https://files.readme.io/b244ce4-image.png">
  CPU usage graph
</Image>

### Horizontal Pod Autoscaling

This widget displays the Current CPU Utilization(%) and the number of pods in this environment. 

### Pods

This displays all the pods that are available in this application resource. 

<Image alt="Available Pods" width="700px" border={true} src="https://files.readme.io/54c48b8-image.png">
  Available Pods
</Image>

**Tail Logs**

1. Click the **Tail Logs** button on the top right corner of the pod.

<Image alt="Tail Logs navigation" width="700px" border={true} src="https://files.readme.io/42d5f65-image.png">
  Tail Logs navigation
</Image>

2. In the pop-up that appears, you will be able to view the tail logs of the Terraform Logs for that pod.

<Image alt="Tail Logs Screen" width="700px" border={true} src="https://files.readme.io/80dbf1a-image.png">
  Tail Logs Screen
</Image>

3. Click on the clipboard icon in the top right corner to copy the logs to the clipboard.

**Rolling Restart All**

The Rolling Restart All allows you to sequentially restart all the available pods in that application resource.

1. Click the **Rolling Restart All** button.

<Image alt="Rolling Restart All navigation" width="700px" border={true} src="https://files.readme.io/d4ed9a1-image.png">
  Rolling Restart All navigation
</Image>

2. In the pop-up that appears, click **Confirm.**

<Image alt="Confirm Rolling Restart All pop-up" width="350px" border={true} src="https://files.readme.io/0c0b496-image.png">
  Confirm Rolling Restart All pop-up
</Image>

You have successfully restarted the pods. 

### Ingress Rules

This widget displays all the Ingress rules configured with this resource.

<Image alt="Ingress Rules widget" width="350px" border={true} src="https://files.readme.io/5224862-image.png">
  Ingress Rules widget
</Image>

## Configuration

This page displays the configurations effective in this environment. You will also find the **Override** and **Version History** buttons. 

<Image alt="Configuration tab" width="700px" border={true} src="https://files.readme.io/7fb8445-image.png">
  Configuration tab
</Image>

### Override

This allows users to override any defined key-value pairs for this resource without making any changes to the blueprint.

1. Click the **Override** button to view the Container Configurations and user-defined variables if any.
2. Using the **Container Configurations** form, you will be able to make the necessary changes to the application.
3. To have access to the complete blueprint of the application, click **JSON Mode** from the top right corner of the screen. 

<Image alt="Override Configuration Form mode" width="700px" border={true} src="https://files.readme.io/8ed1af0-image.png">
  Override Configuration Form mode
</Image>

4. On the **JSON Mode** page, you will find two columns. The left column consists of the defined blueprint and the right column contains the override command. 
5. Enter the override command in the right column and click **Submit** to save the changes. 

<Image alt="Override Configuration JSON mode" width="700px" border={true} src="https://files.readme.io/69a1723-image.png">
  Override Configuration JSON mode
</Image>

> 📘 Note
>
> Any changes made to the blueprint using override from this page is specific to this particular application for this environment only.

You have successfully overridden the blueprint for this application. 

### Version History

This page displays all the configured versions of this resource.

1. Click the **View changes** icon beside the desired version to view the changes made to this version with the previous version.  

<Image alt="Resource Configuration Version History Screen" width="700px" border={true} src="https://files.readme.io/f5d806e-image.png">
  Resource Configuration Version History Screen
</Image>

2. Click the **Compare with current version** icon beside the desired version to compare the older versions to the current version. This icon is only available under the **Previous Versions** widget.

<Image alt="Comparing versions pop-up" width="700px" border={true} src="https://files.readme.io/b794fee-image.png">
  Comparing versions pop-up
</Image>

## Diff

On this page, you will be able to compare this environment with any other environment. Note that you will be able to select up to 2 environments to compare.

1. **Select environment(s)** and click **Compare.**

> 📘 Note
>
> You will only be able to select between the environments in which this application resource is defined.

<Image alt="Compare Environments navigation" border={true} src="https://files.readme.io/44d38ca-image.png">
  Compare Environments navigation
</Image>

2. Now a screen comparing the selected environment appears. This compares and displays any differences between the application in the selected environments.

<Image alt="Compare Environments screen" width="700px" border={true} src="https://files.readme.io/98e3461-image.png">
  Compare Environments screen
</Image>

## Grafana Dashboard

This page displays the application details in a dashboard.

<Image alt="Grafana Dashboard" width="700px" border={true} src="https://files.readme.io/b3f5e87-image.png">
  Grafana Dashboard
</Image>

If the status of the application is in the failed state, click the **Manage your Environment** button. This navigates you to the Releases page where you can plan and deploy a release. 

To know more about releases, refer to the [Releases](doc:releases-concept) documentation.

## Related Guides

* [Resource Center](doc:resource-center)
* [Resource Details](doc:resource-details)
