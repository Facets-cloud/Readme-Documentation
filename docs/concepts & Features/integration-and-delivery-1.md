---
title: Integration and Delivery
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
## [Releases](doc:releases-concept)

Facets enhances the deployment process in cloud environments with a release management system that leverages Terraform's capabilities. By performing a meticulous three-way comparison, Facets ensures that only the necessary adjustments are made to reach the desired state of the environment. This approach minimizes the risk of deployment errors and facilitates a smoother rollback if needed. With Terraform logs available for review, users gain insight into each deployment's details, promoting a transparent and controlled update process within their cloud infrastructure.

## [CI Integration](doc:artifacts)

Facets integrates Continuous Integration (CI) to manage your build images across environments. It supports multiple container registries and offers two types of CI Integration—environment-specific or release-stream-based. Application images can be stored through direct push via Facets CLI or via promotion workflows, which provide controlled paths for moving builds between environments. The integration supports popular CI systems and includes auditing for transparency.

## [Facets CLI](doc:command-line-tool-for-facets)

Facets CLI an easy-to-use alternative to Facets APIs that allows you to push new docker artifacts to the Facets Control Plane, refresh Kubernetes credentials for the user in a specified environment and many other useful functionalities.

## [Delivery Pipeline](doc:pipeline)

Facets' delivery pipeline feature is essential for managing changes across multiple environments. It connects environments in a sequence, allowing you to define criteria for change propagation, such as successful releases or manual approvals. With delivery pipelines, organizations can ensure changes are validated and approved, maintaining system integrity while enabling efficient deployments.