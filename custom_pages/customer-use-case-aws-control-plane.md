---
title: Leveraging AWS for our Customers
fullscreen: false
hidden: false
metadata:
  title: ''
  description: ''
---
Facets Control Plane is deployed in the customer's AWS account, ensuring full control, security, and compliance with local or compliance-based data governance policies.

## Architecture Diagram

![](https://files.readme.io/d7ae728ec0a245c5ed83212b644c24e0c5ea5eef0fa5bc3bf096df594a2ea6f4-image.png)

## AWS Components

### Virtual Private Cloud (VPC)

**Network Isolation**: The VPC provides a logically isolated network environment where all your cloud resources can operate securely and privately.\
**Subnets**: It includes both public and private subnets to organize and control the accessibility of cloud resources.

### Elastic Load Balancer

**Traffic Management**: The Elastic Load Balancer directs incoming traffic to the appropriate services within your cloud infrastructure, ensuring high availability and reliability.

### Elastic Kubernetes Services (EKS)

**Service Hosting**: The EKS cluster hosts the Control Plane Frontend and Backend pods, providing a scalable and robust environment for running the Facets platform.

### NAT Gateways

**Internet Access**: NAT Gateways in the public subnets allow resources in the private subnets to access the Internet securely when needed.

### AWS Services

**State S3 Bucket**: Stores application state data.\
**State Lock DynamoDB**: Maintains state locks for consistency.\
**Artifacts S3 Bucket**: Stores application artifacts.\
**Secrets Manager**: Manages sensitive information like passwords and API keys.

### Facets IaC Agent

**Infrastructure Management**: The Facets IaC Agent manages the infrastructure within the AWS environment, ensuring that all components (e.g., Kubernetes clusters, databases, load balancers) are correctly provisioned, configured, and maintained according to the infrastructure code.

### MongoDB Replicaset

**Data Storage**: MongoDB stores all the necessary information required for the proper functioning of the Facets platform.

### Control Plane Frontend

**UI Hosting**: The Control Plane Frontend pod hosts the user interface (UI) of the Facets platform. This is where you interact with the platform to manage your cloud infrastructure.

### Control Plane Backend

**Terraform Execution**: The Control Plane Backend pod runs the Terraform code that automates the provisioning, configuration, and management of your cloud resources.\
**Orchestration**: This backend pod orchestrates all the necessary cloud operations, ensuring that your infrastructure is set up and maintained according to your specifications.
