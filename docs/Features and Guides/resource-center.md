---
title: Resource Center
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
The **Resource Center** serves as a centralised hub for managing and monitoring resources at **environment level**. It provides environment specific visibility into resource list and for each resource its states, monitoring metrics, configurations, and deployment history through three primary interfaces:

* **Live Monitoring**: View the live monitoring metrics for resources in the selected environment.
* **Resource Overrides**: Manage configuration overrides applied to resources.
* **Release History**: Track release-wise changes to resources .

This functionality streamlines resource management, ensuring consistency and efficiency in cloud infrastructure operations.

## Use Cases

### 1. Centralized Resource Management

* Gain a unified view of all resources within an environment.
* Filter resources by type, name, group, version, and status.
* Identify overridden configurations and their impact.

### 2. Configuring, Debugging and Troubleshooting for a resource

* Check the **Live** tab to get real-time information for deployed resource and investigate resource issues.
* Review the **Release History** tab to trace release-wise changes.
* Check the **Overrides** tab to configure resource at environment level.

### 3. Compliance and Audit Tracking

* Maintain visibility into configuration changes and override history.
* Ensure infrastructure adheres to security and operational guidelines.

## Functionality

### 1. Resource Center

This resource listing page provides a consolidated view of resources within an environment. Key features include:

* **Filtering**: Sort resources by type, name, resource groups, version, and status.
* **Status Indicators**:
  * **Enabled**: Resource is active and functioning.
  * **Disabled**: Resource is currently not in use.
  * **Overridden**: Custom configurations have been applied and overridden configuration details.
* **Sync with Git**: Pull the latest resource state from version control.

### 2. Live Overview

The Live tab provides real-time insights and control over cloud resources, helping DevOps engineers and developers monitor deployments, manage Kubernetes workloads, access Terraform outputs, and visualize key metrics.

* **Pipeline Activity:** Track build history, blueprint changes, and overrides with rollback support.\
  Kubernetes Dashboard: Manage workloads, monitor pod statuses, and perform actions like rolling restarts and scaling.
* **Terraform Outputs:** View and copy resource attributes and connection details for seamless integration.
* **Monitoring Dashboards:** Utilize Grafana-powered insights on CPU, memory, and pod restarts for system health tracking.
* **Additional Dashboards:** Access ingress traffic details, historical logs, and other relevant metrics based on the resource type.

### 3. Resource Overrides

This tab allows users to manage resource-level configuration overrides. Key actions include:

* **View Overrides**: See resources with customized configurations.
* **Apply or Remove Overrides**: Modify settings to enforce environment-specific changes.
* **Impact Analysis**: Assess the effect of overrides on the system.

### 4. Release History

This tab provides a historical log of resource deployments. Key features include:

* **Deployment Logs**: Track when and how a resource was modified.
* **Version Comparisons**: Identify differences between releases.
* **Rollback Support**: Revert to previous configurations if necessary.

## User-flow

<Embed url="https://app.storylane.io/demo/8kfmjpyr63tx" title="Resource Center" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_380d520f-671c-4bb7-8a35-79bdf77e71b5/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/8kfmjpyr63tx" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F8kfmjpyr63tx%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F8kfmjpyr63tx%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_380d520f-671c-4bb7-8a35-79bdf77e71b5%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

## Frequently Asked Questions (FAQs)

* **What external tools can I integrate with Facets for monitoring and management?**\
  Facets allows integration with tools such as Prometheus, Alertmanager, Grafana, and Wetty for advanced monitoring and management.
* **How can I modify resource configurations for different environments?**\
  The Resource Overrides interface enables environment-specific configuration management, allowing customization of resource settings for different environments.
* **Where can I find a record of all changes made to a resource?**\
  The Release History interface maintains a comprehensive chronological record of all changes made to a resource within a specific environment. 
* **How do I access the Resource Details page?**\
  Navigate to Environment > Resources, then click on the resource name from the list of resources to view the details.
* **Can I make modifications in the environment that will deviate from the Blueprint?**\
  Yes, by using Resource Overrides, you can directly modify resource configurations in an environment from the Control Plane, which is useful when there is a need to deviate from the Blueprint.
* **What views are available within Resource Overrides?**\
  Overrides can be done in Form or JSON mode.
* **Why are the base resources not visible in the resource center?**\
  There's a toggle on the top right corner of the resource table to control the base resource visibility.
* **How can I see the resources of some other environment page?**\
  Resource center is an environment-specific page. There's an environment switcher present on all such pages to change the environment.
* **What are the bulk operations available in the resource center?**\
  Multiple resources can be selected to perform bulk enable and disable operations.
* **What is the difference between resource type and type column in resource center?**\
  The resource type column shows the intent of a resource where as the type column shows wether the resource is Normal, Provided or Inherited.
