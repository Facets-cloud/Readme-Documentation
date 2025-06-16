---
title: IaC Streams and Versions in Facets
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
You can use Infrastructure as Code (IaC) Streams and Versions to enable teams to manage and automate infrastructure deployments.

## IaC Streams

In the Facets Control Plane, all changes made to the IaC are versioned and separated into different streams to ensure that development teams can stay on top of the changes that are about to come and keep their production environment stable. The streams available in the Facets Control Plane are Production, Stage, and tfdev.

### Production Stream

The Production Stream is the Generally Available (GA) version of the IaC, which is recommended for use in production infrastructure deployments. This stream ensures that customers can deploy their infrastructure with the confidence that it has been thoroughly tested and is ready for production use.

### Stage Stream

The Stage Stream is used for all new changes in the IaC for a minimum of two weeks. Customers are encouraged to map their development environments to this stream to catch any issues or regressions early in the pipeline. This stream provides a way to test new changes before deploying them in production.

### tfdev Stream

The tfdev Stream is the Development branch used by Facets engineers. This stream is unstable and should only be mapped for experimental features and testing. Customers should avoid using this stream in production environments.

## Major and minor versions

Facets Control Plane supports both major and minor versions for each IaC stream.

### Major Versions

Major versions are used for significant updates and changes to the infrastructure, which may require downtime. A new major version availability comes as a notification in the product and release notes. Users are required to coordinate with their DevOps team to test the changes in non-production environments before deploying them in production.

### Minor Versions

Minor versions are used for non-breaking enhancements, security patches, and bug fixes. These updates are automatically upgraded. Customers should only pin minor versions in case of specific issues or requirements.

In conclusion, Facets Control Plane provides a flexible and reliable platform for managing infrastructure deployments using Infrastructure as Code technology. With version control and separate streams, customers can confidently manage their infrastructure changes and ensure smooth deployments across all their environments.
