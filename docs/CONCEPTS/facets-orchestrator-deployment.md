---
title: Facets Orchestrator Deployment
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
## Introduction

Facets Orchestrator is a platform engineering orchestration tool designed to streamline cloud infrastructure management for developers and Platform Engineering teams (formerly DevOps teams). It automates the entire process of provisioning infrastructure, deploying applications, and configuring environments, reducing complexity and enabling both teams to focus on their core tasks.

> Control Plane provides a centralized control center for managing infrastructure and applications.

## Deployment Options

There are two versions of Control Plane:

1. **Enterprise Plan:** Deployed in the customer's cloud environment, making it a completely isolated deployment. This ensures full ownership and control over the infrastructure and applications.

2. **Growth Plan (SaaS Model):** Hosted on Facets' cloud, this version provides the same DevOps capabilities but is managed by Facets. Currently, we are in the Beta phase for the SaaS control plane. You can request a trial [here](https://www.facets.cloud/quick-cloud-deployments).

## AWS Architecture

Control Plane is built as a microservices architecture and runs within a Kubernetes cluster. It can manage resources on AWS, Azure, and GCP. The following diagram illustrates its architecture. Additionally, it is self-deployable and can be easily set up on the customer's AWS account with a single click through an automated process.

<Image align="center" className="border" border={true} src="https://files.readme.io/e7610b50522f171508aa9f29158b7a65bd835ee15dd5971398e4a84bb835a52e-Dataflow_Diagram.png" />

<Image align="center" src="https://files.readme.io/a379fc4af7044c7fe85b78ea64ca78ef199b871735e6b914a51ffc1f8670c933-AWS_FTR_-_Rohit_2.png" />

## Overview of AWS Resources

The deployment involves the following AWS resources:

### 1. Virtual Private Cloud (VPC)

#### Dedicated VPC

* A dedicated VPC is created for the Facets control plane.
* Optionally, an existing VPC can be used.

### 2. Subnets

#### Private Subnets

* One in each of the two Availability Zones (AZs).
* Each private subnet is connected to a NAT Gateway for internet access.

#### Public Subnets

* One in each of the two AZs.
* All public subnets are connected to a single Internet Gateway (IGW).

### 3. Amazon Elastic Kubernetes Service (EKS)

#### EKS Cluster

* An Amazon EKS cluster is deployed with Secret encryption using AWS Key Management Service (KMS).

#### EKS Nodes

* Nodes configured with the following specifications:
  * 8 vCPUs
  * 32 GB RAM
  * 100 GB root volume

### 4. Elastic Load Balancers (ELBs)

* Two Internet-facing Elastic Load Balancers are provisioned to handle traffic.

### 5. Certificates

* Two AWS Certificate Manager (ACM) certificates are used for secure communication.

### 6. Storage

#### S3 Buckets

* Three AES-encrypted S3 buckets are created:
  * Logging (No public access)
  * Internal Artifacts Storage (No public access)
  * Infrastructure as Code (IAC) State storage (No public access)

#### EBS Volumes

* KMS-encrypted EBS volumes are used for:
  * Metadata
  * Metrics
  * Hot-tier logs

### 7. DynamoDB

* A DynamoDB table is used for IAC state locking.

### 8. Secrets Manager

* Sensitive data submitted to the control plane is securely stored in AWS Secrets Manager.
