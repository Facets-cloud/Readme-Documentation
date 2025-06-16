---
title: Control Plane in Shared VPC (GCP)
excerpt: >-
  This document provides a step-by-step guide to setting up and launching the
  Facets Control Plane in a GCP Shared VPC.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## 1. Pre-requisites

Before launching the Facets Control Plane, ensure the following GCP setup is complete: 

Note: To learn how to create a shared VPC [check this doc.](https://readme.facets.cloud/docs/control-plane-in-shared-vpc-gcp)

### A. Organizational Setup

* A GCP organizational account is required.
* A Host Project with the following IAM roles:\
  `Compute Network Admin`\
  `Compute Network User`\
  `Organization Administrator`\
  `Owner`
* Additional permissions:
  * `compute.organizations.disableXpnHost`
  * `compute.organizations.disableXpnResource`
  * `compute.organizations.enableXpnHost`
  * `compute.organizations.enableXpnResource`
  * `compute.projects.get`
  * `resourcemanager.projects.get`
  * `resourcemanager.projects.getIamPolicy`
  * `resourcemanager.projects.list`

### B. Networking Setup in the Host Project

* A VPC must be created in the host project, acting as the shared network for all attached service projects.
* Create at least two or three subnets with `/16` CIDR ranges.
* Add secondary CIDR ranges (`/16` each) for:
  * GKE pods
  * GKE services
* Reserve a subnet for Internal Load Balancers (ILBs) for Facets components.
* Enable Cloud NAT to allow outbound connections without exposing node IPs.
* Enable Private Google Access for GKE clusters to securely access Google services.
* Allocate a Private Service Access range (important if using managed services like AlloyDB).
* Establish a Private GCP Connection for secure access to Google services.\`

## 2. Configuring the Shared VPC

**Attach Service Projects:** Ensure that service projects are properly attached to the shared VPC with Kubernetes access enabled. This allows the service projects to utilize network resources from the host project.

### **Permissions:**

**Project-Level Permissions:**

Assign the role of Compute Security Admin to `service-\<SERVICE_PROJECT_NUMBER>@container-engine-robot.iam.gserviceaccount.com.`

Assign the role of Kubernetes Engine Host Service Agent User to the same service account.

**Subnet-Level Permissions:**

Assign the role of Compute Network User to the following service accounts:

* `\<SERVICE_PROJECT_NUMBER>[-compute@developer.gserviceaccount.com](mailto:-compute@developer.gserviceaccount.com)`
* `\<SERVICE_PROJECT_NUMBER>@cloudservices.gserviceaccount.com`
* `service-\<SERVICE_PROJECT_NUMBER>@container-engine-robot.iam.gserviceaccount.com`

## 3. Configuring Facets Service Account

**Create Facets Service Account:**

Within the service project, create a service account designated for Facets. This account will manage interactions and operations specific to the Facets application within the shared VPC.

**Assign Custom Role in Host Project:**

Create a custom role in the host project with the following permissions:

* `compute.firewalls.create`
* `compute.firewalls.update`
* `compute.firewalls.delete`
* `compute.firewalls.get`
* `compute.globalOperations.get`
* `compute.networks.updatePolicy`
* `compute.subnetworks.get`

Attach this custom role to the Facets service account created in the service project. This step is crucial for providing the necessary permissions for network management and configuration.
