---
title: Facets CLI
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: Install FacetsCLI and integration with your CI pipeline.
  pages:
    - type: basic
      slug: integration
      title: Installing FacetsCLI
    - type: basic
      slug: commands
      title: Commands
    - type: basic
      slug: integrating-with-cicd-pipelines
      title: Integrating with CI/CD Pipelines
---
**Facets CLI (facetsctl)** is a command-line tool that allows users to interact with the Facets Control Plane. It offers a user-friendly alternative to Facets APIs, enabling DevOps engineers to manage artifacts, synchronize application releases, and perform other essential tasks efficiently. 

### Use Cases

The facetsctlv3 CLI is designed for several key use cases:

* **Artifact Management**: Push, register, and upload Docker images or other artifacts to the Facets Control Plane.
* **Application Synchronisation**: Ensure that applications are in sync with their desired states across different environments.

### Installation

You can view and download the latest `facetsctlv3` package from its <a href="https://www.npmjs.com/package/@facets-cloud/facetsctlv3" target="_blank">Facets Cloud NPM package</a>. To know more about installation refer to [Installing Facets CLI](https://readme.facets.cloud/v1.4/docs/integration).

**Note**: This documentation focuses on the latest version of the Facets CLI (`facetsctlv3`). The previous version (`facetsctl` version 1.0.9) is deprecated and no longer supported. Please upgrade to the latest version for optimal performance and compatibility.

### Upgrading to `facetsctlv3`

1. Download the latest `facetsctlv3` release from the official [Facets GitHub repository](github.com/facets-cloud/facetsctl) or [package manager](https://readme.facets.cloud/v1.4/docs/integration#1-install-using-npm).
2. Replace the old `facetsctl` binary with the new `facetsctlv3` binary.
3. Update any scripts or automation workflows that use `facetsctl` to reference `facetsctlv3`commands.

**Key Changes in`facetsctlv3`** :

* Enhanced command structure and output formatting for improved readability.
* Support for new features and APIs introduced in recent Control Plane versions.
* Bug fixes and performance improvements.
