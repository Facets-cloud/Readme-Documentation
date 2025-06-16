---
title: 'Resource: Live Insights & Operations'
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
The **Live** tab offers real-time insights and management capabilities for your cloud resources. It provides a comprehensive view of pipeline activities, Kubernetes workloads, Terraform outputs, and monitoring dashboards.

## Use Cases

- **Real-Time Monitoring**: Observe live deployment statuses and resource metrics to ensure system health and performance.
- **Deployment Management**: Oversee and control deployment pipelines, including version rollbacks and promotions.
- **Kubernetes Operations**: Manage Kubernetes workloads with actions like rolling restarts and scaling adjustments.
- **Infrastructure Outputs Access**: Retrieve and utilise Terraform outputs for seamless integration and configuration.
- **Resource Monitoring**: Utilise Grafana-powered dashboards to monitor CPU usage, memory consumption, and pod restarts.

***

## Functionalities

### 1. Pipeline Activity

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fbhfqttv3j2bs&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fbhfqttv3j2bs&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_3ca51d9a-52b5-4e78-9481-f4710a5ac106%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"431\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/bhfqttv3j2bs",
  "title": "Pipeline Activity (copy)",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_3ca51d9a-52b5-4e78-9481-f4710a5ac106/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/bhfqttv3j2bs",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

This section displays the current state and version history segmented into:

- **Build Registered**: Tracks the changes to the artifact being deployed.
- **Blueprint Activity**: Monitors changes and deployments related to the blueprint configurations.
- **Override Activity**: Logs modifications applied to the resources as overrides.

Each category presents:

- **Live Version**: The version currently deployed.
- **Release Pending Version**: The version queued for deployment.
- **Version History**: An expandable table detailing past versions with timestamps and statuses.

The Version History table includes a **rollback** feature, allowing you to revert to a specific version if necessary.

***

### 2. Kubernetes Dashboard

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d19af88888ded9c216726464e0d25c961f3c06a386057084b932dce176538256-Screenshot_2025-02-18_at_2.26.05_PM.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "500px",
      "border": true
    }
  ]
}
[/block]


This dashboard offers a live overview of your Kubernetes cluster, covering:

- **Workloads**:
  - **Pods**: Displays status, age, restarts, readiness, and available actions.
  - **Deployments, DaemonSets, StatefulSets, CronJobs, Jobs**: Provides insights into the state and performance of various controllers and jobs.

- **Storage**:
  - **Persistent Volume Claims (PVCs) and Persistent Volumes (PVs)**: Shows storage allocations, statuses, and capacities.

- **Autoscaling**:
  - **Horizontal Pod Autoscalers (HPAs)**: Monitors scaling activities and metrics.

For **Pods**, the following actions are available:

- **Rolling Restart**: Gracefully restarts pods to apply updates or recover from issues.
- **Refresh**: Updates the pod list to reflect the current state.
- **Promote**: Advances a pod to a stable release, particularly useful in blue-green or canary deployments.
- **Abort**: Terminates a deployment in progress, applicable during blue-green or canary strategies.

***

### 3. Terraform Outputs

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2e23068f229b97e1fd5ded6220043dbbe097d08c2e2a99d3cba3de17e194e70-Screenshot_2025-02-18_at_2.27.47_PM.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "450px",
      "border": true
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/abef680180ce1f18d848461ee70ba344f75fe22f4cea37be5bf744b9b2051440-Screenshot_2025-02-18_at_2.27.56_PM.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "450px",
      "border": true
    }
  ]
}
[/block]


This section displays the outputs from your Terraform configurations, including:

- **Interfaces**: Endpoints or connection details exposed by your resources.
- **Attributes**: Key-value pairs representing resource properties.

Each output offers action buttons to copy names and dollar references (`$refs`) for seamless integration into your configurations.

***

### 4. Monitoring Dashboards

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf143d170d4a1a97620c33c651f6831ce99a3b30094977dabc62006316400260-MixCollage-18-Feb-2025-02-37-PM-3020.jpg",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Real-time monitoring is facilitated through Grafana-powered dashboards, featuring:

- **CPU Usage**: Visualizes CPU consumption across your resources.
- **Memory Usage**: Tracks memory allocation and usage patterns.
- **Pod Restarts**: Monitors the frequency and reasons for pod restarts, aiding in troubleshooting.

***

### 5. Additional Dashboards

Depending on the selected resource type, additional dashboards may include:

- **Ingress Overview**: Details traffic routing, load balancing, and external access points.
- **Historical Logs**: Provides access to past logs for auditing and debugging purposes.

These dashboards adapt based on the resource type selected, ensuring relevant information is presented for effective management.

***

## FAQs

**Q1: How can I perform a rollback to a previous version?**

Navigate to the **Pipeline Activity** section, expand the **Version History** table, and select the desired version to revert to using the rollback mechanism.

**Q2: What actions are available for managing pods?**

In the **Kubernetes Dashboard**, you can perform actions such as **Rolling Restart**, **Refresh**, **Promote**, and **Abort**.

**Q3: What monitoring metrics are available?**

The **Monitoring Dashboards** provide metrics on **CPU Usage**, **Memory Usage**, and **Pod Restarts**, visualized through Grafana dashboards.

**Q4: Are the dashboards customizable?**

Dashboards are tailored based on the selected resource type, ensuring relevant information is displayed for effective management.

***

## Troubleshooting

**Issue: Changes are not reflecting in the Kubernetes Dashboard.**

- **Solution**: Ensure you have clicked the **Refresh** action to update the pod list. If the issue persists, verify your Kubernetes cluster's connectivity and health.

**Issue: Unable to perform a rollback to a previous version.**

- **Solution**: Confirm that the desired version is listed in the **Version History**. If it's unavailable, the version may not be eligible for rollback.

**Issue: Terraform outputs are not displaying correctly.**

- **Solution**: Check that your Terraform configurations have been applied successfully. Re-run the Terraform apply process if necessary and refresh the **Live** tab.