---
title: Uptime Dashboard
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
Facets Uptime Status Dashboard is a comprehensive, real-time solution designed to monitor the uptime of resources across various Blueprints and Environments. 

This feature offers a centralized solution, integrating with Grafana for comprehensive analytics, that effectively monitors and distinguishes the uptime and downtime of resources. This aims to reduce resource downtime by comparing existing downtime to downtime after alerts.

## Key Features

- **Uptime Dashboard:** The Status check Monitoring dashboard in Grafana lists all configured resources, providing detailed information such as name, uptime percentage, and current ping status.
- **Alerts:** Real-time notifications are provided for resources that become inactive and when previously inactive resources return to an active state. Users can manage specific 'Health status' alerts in the **Alert Manager** section and view alert details.
- **Resource Status Display:** The status of resources, represented as either 'healthy' or 'unhealthy' and indicating their uptime and downtime. A 'healthy' status signifies that the resource is operational, implying uptime, while an 'unhealthy' status suggests the resource is not functioning as expected, denoting downtime.

## FAQ

### 1. How will I be notified when a resource's status changes?

The system will send you alerts when a resource becomes unhealthy or returns to a healthy state. This enables you to address potential issues or inform your team of changes quickly.

### 2. What is uptime and downtime?

Uptime refers to the period when a service or resource is operational and running as expected.  
Downtime refers to the period during which a service or resource is unavailable or not functioning as intended.

### 3. Does accessing the Uptime Dashboard require any specific permissions?

No, accessing the Uptime Dashboard does not require any specific permissions.

## Related Guides

- [Configuring the Uptime Dashboard](https://readme.facets.cloud/docs/configuring-the-uptime-dashboard)