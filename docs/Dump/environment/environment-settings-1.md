---
title: Environment Settings
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
The Environment Settings section allows you to configure and manage various aspects of your deployment environments. This document outlines the key settings and options available, helping you to customize and optimize your environments effectively.

Please refer to the following sample use cases:

* [Mirroring Production Setup for UAT](https://readme.facets.cloud/docs/environment-settings-use-cases#mirroring-production-setup-for-uat)
* [Creating Secure Development Environment](https://readme.facets.cloud/docs/environment-settings-use-cases#creating-secure-development-environment)

## General Settings

* **Environment Name:** Assign clear and descriptive names such as "Production", "Staging", or "Development" to easily distinguish between environments.
* **Release Stream:** Select the appropriate release stream to ensure that the environment receives the correct updates and features.
* **Request Limit Ratio:** Set the request limit ratio to manage the maximum number of requests the environment can handle relative to its capacity.
* **Instance Type:** Choose an instance type that matches the workload and performance needs of the environment.

## Time Sensitive

* **Environment Type:** Select 'Time-Sensitive' for ephemeral environments, which are temporary and short-lived, created for specific purposes and discarded once they are no longer needed.\
  To know more about setting up Availability Rules for your ephemeral environments, refer to the [Availability Rules for Environments](https://readme.facets.cloud/docs/availability-rules-for-environments) documentation.

## Releases Settings

* **Release Schedule:** Define a release schedule to ensure updates are rolled out without disrupting users. Refer to the [Scheduling Releases](https://readme.facets.cloud/docs/scheduling-releases) documentation to know more about it.
* **IAC Version:** Specify the version of Infrastructure as Code (IAC) to ensure all environments are using the same configuration scripts.

## Advanced Settings

* **Node Plan:** Select a node plan that matches the environment's resource needs.
* **Root Volume:** Set the root volume size to ensure sufficient storage for the operating system and applications.
* **Max Nodes:** Define the maximum number of nodes to manage resource allocation efficiently.

## Virtual Private Network (VPN)

* **VPN Configuration:** Configure a VPN to secure data transmission and access within the environment. Refer to the [VPN in Facets](https://readme.facets.cloud/docs/vpn-in-facets) documentation to know more about it.

## Danger Zone

* **Destroy Environment:** Use this option to permanently destroy the environment and all associated resources.
* **Delete Environment:** Permanently delete the environment configuration when it is no longer required.

Refer to the [Destroying and Deleting an Environment](https://readme.facets.cloud/docs/destroying-and-deleting-an-environment) documentation to know more about it.
