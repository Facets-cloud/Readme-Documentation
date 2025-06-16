---
title: Get your Control Plane (Azure)
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
Welcome to Facets! In this getting started guide, we will walk you through the process of getting your control plane. The first step is to get a demo and have a short discussion with the Facets team.

1. **Get a Demo **: To get started, simply request a [demo by contacting the Facets team](https://www.facets.cloud/demo). Our team will understand the requirements and will help you get started. 
2. **Submit Service Account Details**: You will receive a form to submit your service account details. It is important that the service account has Owner access to the Azure subscription. This step is crucial for the Facets team to set up and manage your control plane. It is recommended to use a dedicated subscription for setting up the Facets control plane.
3. **The Facets team launches the Control Plane**: After receiving your service account details, the Facets team will launch the control plane in Azure. The setup will be completed, and your control plane will be ready to use within approximately 60 minutes.
4. **Welcome Email with Control Plane URL**: You will receive a welcome email with your personal control plane URL, along with a username and password reset link. This will allow you to log into the control plane and start using Facets.

## Resources Deployed

The control plane in Azure will consist of the following resources:

1. **Virtual Network (VNet)**: A dedicated virtual network for the Facets control plane.
2. **Subnets**:
   1. Private Subnets: One in each of two Availability Zones (AZs) with a corresponding NAT Gateway for each.
   2. Public Subnets: One in each of two AZs
3. **Azure Kubernetes Service (AKS):**:
   1. Cluster: An AKS cluster with encryption at rest
   2. Nodes: AKS nodepool configured with 8 vCPUs, 32GB RAM, and a 100GB root volume.
4. **Load Balancer**: Two internet-facing Azure Load Balancers.

### Deployment Options

You can choose any Azure Region and Availability Zones for deploying the control plane. Communicate your preferences with the [Facets team](support@facets.cloud). Any changes in resource sizing can be requested via email to the [Facets team.](support@facets.cloud)

And that's it! You now have access to your control plane and are ready to start using Facets. Next, you can create your first blueprint and start exploring the different concepts and features of Facets.