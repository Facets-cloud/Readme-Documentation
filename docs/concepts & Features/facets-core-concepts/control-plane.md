---
title: Facets Control Plane
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

Control Plane is a self-serve DevOps platform that allows organizations to manage all aspects of their software development lifecycle in one place. It enables organizations to streamline their Software Delivery Life Cycle (SDLC), manage multiple environments, and collaborate more effectively, all while maintaining a high level of security and compliance.

> Control Plane is a comprehensive DevOps platform that provides a centralized control center for managing infrastructure and applications.

## Architecture

The Control Plane is designed as a microservices architecture and operates within a customer's cloud environment, offering full ownership. It requires a Kubernetes cluster to function and is currently only deployable on AWS. However, it has the capability to manage resources on all three major cloud platforms, including AWS, Azure, and GCP. The following diagram provides a simple illustration of its architecture. Additionally, it is self-deployable and can be easily set up on the customer's AWS account with a single click, through a fully automated process.

<Image align="center" className="border" width="700px" border={true} src="https://files.readme.io/d599bf3-image.png" />

## FAQs

### What is Control Plane?

Control Plane is a self-serve DevOps platform that enables organizations to manage all aspects of their software development lifecycle in one centralized location.

### How is Control Plane deployed?

For Enterprise Customers, Control Plane is set up on the customer's cloud provider account with a single click, through a fully automated process.

Growth customers can get their Control Plane hosted on Facets' cloud (SaaS model). Currently we are in Beta phase for SaaS control plane. 

### Can Control Plane manage resources on other cloud platforms?

Yes, Control Plane has the capability to manage resources on all major cloud platforms, including AWS, Azure, and GCP.

### Can Control Plane be deployed in Azure or GCP?

Yes, Control Plane can be deployed in AWS, Azure and GCP.
