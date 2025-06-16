---
title: Connect your Cloud Accounts
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
In Facets, cloud accounts are the foundation for managing and provisioning infrastructure in multi-cloud environments. Facets integrates with major cloud providers, including AWS, Azure, and GCP, enabling users to launch, manage, and oversee cloud resources directly from the platform.

## Linking Cloud Accounts to Facets

To deploy resources in any particular environment, users must link their cloud accounts to Facets. This linking process establishes the necessary permissions, allowing Facets to manage resources within a specified cloud environment. Typically, users grant Facets access by providing cloud credentials or using IAM roles, depending on cloud provider requirements.

## Using Cloud Accounts in Facets

Once accounts are linked, Facets simplifies infrastructure management across cloud environments, providing a unified interface for deployment and monitoring:

1. **Environment Provisioning**\
   Facets provisions infrastructure in the linked cloud accounts, such as virtual private clouds (VPCs), Kubernetes clusters, and other resources. Users select the cloud provider and region, and Facets then utilizes account credentials to create and configure resources as specified.
2. **Unified Infrastructure Management**\
   Regardless of the cloud provider, users gain a consolidated view of all cloud resources. Facets acts as a control plane, enabling multi-cloud resource monitoring and management from a single dashboard.
3. **IAM Role Management and Secrets**\
   Facets integrates with each provider's IAM (Identity and Access Management) and secret management services to securely handle access and sensitive data. It leverages tools like AWS Secrets Manager and Azure Key Vault to store and retrieve secrets, and it uses IAM roles for permission control, aligning with cloud provider best practices.
4. **Multi-Cloud Flexibility**\
   With support for multiple cloud accounts, Facets offers flexibility in selecting providers for different use cases and simplifies the process of migrating resources across providers or regions.

## Cloud Account-Specific Considerations

Each cloud provider brings its own nuances when integrated with Facets. Notable examples include:

* **ECR Permissions**\
  When connecting an Amazon ECR (Elastic Container Registry) with Facets, users may configure specific IAM roles for Facets to access the registry. To limit permissions, it’s recommended to create a dedicated user with read-only access specifically for Facets interactions.
* **Security Configurations for Facets Control Plane**\
  Resources created by Facets during control plane configuration might generate security alerts. For instance, some components may run with elevated privileges, requiring teams to document these resources for auditing and future modification.
* **CloudFormation Region Selection**\
  When using CloudFormation templates, deployment regions can be selected in line with Facets' control plane location to minimize latency.
* **Migrating Terraform Modules**\
  For existing Terraform setups, Facets recommends importing modules directly rather than adapting them into open-source structures, ensuring smoother transitions and compatibility.
