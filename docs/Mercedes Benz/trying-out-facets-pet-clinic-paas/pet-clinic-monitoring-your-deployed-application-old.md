---
title: Monitoring your Deployed Application
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
## How to monitor the deployed application?

Monitoring your deployed application is simple and can be done in multiple ways:

### Using the Resource Center

To access this, navigate to the **Resource Center.**

#### For the Ingress Resource:

1. Overview
   - In the Overview tab, you will find the **Blueprint**, **Configuration**, and **Interfaces** widgets.
     - Blueprint: This section displays any change you have made at the Blueprint level.
     - Configuration: This section displays modifications you have made at the environment level.
     - Interfaces: This section lists all key-value pairs you've set up as part of the ingress rules.
2. Ingress Overview
   - In the **Ingress Overview** tab, you will find the **Ingress Overview** dashboard. This dashboard provides details regarding **Total Request Volume, Percentile Response Time, Status Code Count, Services Health,** and **SSL Expiry.**
     - Total Request Volume: This is the total number of requests received by your application in a specific time frame.
     - Percentile Response Time: This is a measurement of how quickly the application responds to requests.
     - Status Code Count: This is the count of HTTP status codes returned by your application.
     - Services Health: This indicates the operational status of your application.
     - SSL Expiry: This refers to the expiration date of your Ingress’s SSL certificate

**For the Postgres Resource: **

1. Overview
   - In the Overview tab, you will find the **Blueprint**, **Configuration**, and **Interfaces and Attributes** widgets.
     - Blueprint: This section displays any change you have made at the Blueprint level.
     - Configuration: This section displays modifications you have made at the environment level.
     - Interfaces and Attributes: This section lists all key-value pairs you've set up as part of the ingress rules.

**For the Service Resource:**

1. Overview
   - In the Overview tab, you will find the **Blueprint**, **Configuration**, and **Interfaces** widgets.
     - Blueprint: This section displays any change you have made at the Blueprint level.
     - Configuration: This section displays modifications you have made at the environment level.
     - Interfaces: This section lists all key-value pairs you've set up as part of the ingress rules.
2. Monitor
   - In the Monitor tab, you will find the graphs for **Container CPU Cores Used, Container GBytes of Memory Used,** and **Active Pods by Deployment.**
     - Container CPU Cores Used: This refers to the amount of CPU cores that a container is using in a Kubernetes (k8s) environment.
     - Container GBytes of Memory Used: This indicates the amount of memory in gigabytes that a container is utilizing in a Kubernetes environment.
     - Active Pods by Deployment: This represents the number of active pods for each deployment within a Kubernetes environment.
3. Ingress Overview
   - In the **Ingress Overview** tab, you will find the **Ingress Overview** dashboard. This dashboard provides details regarding **Total Request Volume, Percentile Response Time, Status Code Count, Services Health,** and **SSL Expiry.**
     - Total Request Volume: This is the total number of requests received by your application in a specific time frame.
     - Percentile Response Time: This is a measure of how quickly the application responds to requests.
     - Status Code Count: This is the count of HTTP status codes returned by your application.
     - Services Health: This indicates the operational status of your application.
     - SSL Expiry: This refers to the expiration date of your Ingress’s SSL certificate

By utilizing these tools and resources, you can effectively monitor the status and performance of your deployed application.

### Using the Tools tab

To access this, navigate to **Environment > Tools.** Here, you'll find two dashboards:

- The **Kubernetes Dashboard**: This is a general-purpose web-based UI for Kubernetes clusters. It allows users to manage and troubleshoot applications running in the cluster.
- The **Grafana Dashboard**: This is an open-source analytics application that helps visualize data through charts and graphs, and provides alerts and logs when linked to compatible data sources.