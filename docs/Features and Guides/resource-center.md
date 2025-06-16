---
title: Resource Center
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
The **Resource Center** serves as a centralised hub for managing and monitoring resources at **environment level**. It provides environment specific visibility into resource list and for each resource its states, monitoring metrics, configurations, and deployment history through three primary interfaces:

- **Live Monitoring**: View the live monitoring metrics for resources in the selected environment.
- **Resource Overrides**: Manage configuration overrides applied to resources.
- **Release History**: Track release-wise changes to resources .

This functionality streamlines resource management, ensuring consistency and efficiency in cloud infrastructure operations.

## Use Cases

### 1. Centralized Resource Management

- Gain a unified view of all resources within an environment.
- Filter resources by type, name, group, version, and status.
- Identify overridden configurations and their impact.

### 2. Configuring, Debugging and Troubleshooting for a resource

- Check the **Live** tab to get real-time information for deployed resource and investigate resource issues.
- Review the **Release History** tab to trace release-wise changes.
- Check the **Overrides** tab to configure resource at environment level.

### 3. Compliance and Audit Tracking

- Maintain visibility into configuration changes and override history.
- Ensure infrastructure adheres to security and operational guidelines.

## Functionality

### 1. Resource Center

This resource listing page provides a consolidated view of resources within an environment. Key features include:

- **Filtering**: Sort resources by type, name, resource groups, version, and status.
- **Status Indicators**:
  - **Enabled**: Resource is active and functioning.
  - **Disabled**: Resource is currently not in use.
  - **Overridden**: Custom configurations have been applied and overridden configuration details.
- **Sync with Git**: Pull the latest resource state from version control.

### 2. Live Overview

The Live tab provides real-time insights and control over cloud resources, helping DevOps engineers and developers monitor deployments, manage Kubernetes workloads, access Terraform outputs, and visualize key metrics.

- **Pipeline Activity:** Track build history, blueprint changes, and overrides with rollback support.  
  Kubernetes Dashboard: Manage workloads, monitor pod statuses, and perform actions like rolling restarts and scaling.
- **Terraform Outputs:** View and copy resource attributes and connection details for seamless integration.
- **Monitoring Dashboards:** Utilize Grafana-powered insights on CPU, memory, and pod restarts for system health tracking.
- **Additional Dashboards:** Access ingress traffic details, historical logs, and other relevant metrics based on the resource type.

### 3. Resource Overrides

This tab allows users to manage resource-level configuration overrides. Key actions include:

- **View Overrides**: See resources with customized configurations.
- **Apply or Remove Overrides**: Modify settings to enforce environment-specific changes.
- **Impact Analysis**: Assess the effect of overrides on the system.

### 4. Release History

This tab provides a historical log of resource deployments. Key features include:

- **Deployment Logs**: Track when and how a resource was modified.
- **Version Comparisons**: Identify differences between releases.
- **Rollback Support**: Revert to previous configurations if necessary.

## User-flow

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2F8kfmjpyr63tx&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2F8kfmjpyr63tx&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_380d520f-671c-4bb7-8a35-79bdf77e71b5%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"431\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/8kfmjpyr63tx",
  "title": "Resource Center",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_380d520f-671c-4bb7-8a35-79bdf77e71b5/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/8kfmjpyr63tx",
  "typeOfEmbed": "jsfiddle"
}
[/block]


## Frequently Asked Questions (FAQs)

- **What external tools can I integrate with Facets for monitoring and management?**  
  Facets allows integration with tools such as Prometheus, Alertmanager, Grafana, and Wetty for advanced monitoring and management.
- **How can I modify resource configurations for different environments?**  
  The Resource Overrides interface enables environment-specific configuration management, allowing customization of resource settings for different environments.
- **Where can I find a record of all changes made to a resource?**  
  The Release History interface maintains a comprehensive chronological record of all changes made to a resource within a specific environment. 
- **How do I access the Resource Details page?**  
  Navigate to Environment > Resources, then click on the resource name from the list of resources to view the details.
- **Can I make modifications in the environment that will deviate from the Blueprint?**  
  Yes, by using Resource Overrides, you can directly modify resource configurations in an environment from the Control Plane, which is useful when there is a need to deviate from the Blueprint.
- **What views are available within Resource Overrides?**  
  Overrides can be done in Form or JSON mode.
- **Why are the base resources not visible in the resource center?**  
  There's a toggle on the top right corner of the resource table to control the base resource visibility.
- **How can I see the resources of some other environment page?**  
  Resource center is an environment-specific page. There's an environment switcher present on all such pages to change the environment.
- **What are the bulk operations available in the resource center?**  
  Multiple resources can be selected to perform bulk enable and disable operations.
- **What is the difference between resource type and type column in resource center?**  
  The resource type column shows the intent of a resource where as the type column shows wether the resource is Normal, Provided or Inherited.