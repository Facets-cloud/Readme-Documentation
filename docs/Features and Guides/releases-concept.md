---
title: Releases-krishna
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
## Introduction

A release in Facets is a streamlined, process for deploying changes to a cloud environment. Releases are executed using Terraform apply commands, which perform a three-way comparison of state to determine and deploy the necessary changes to the corresponding cloud environment.

Any kind of changes in a running environment, be it a new Redis or a new application build happens through a **Release**.

### Releases Execution

For any environment, Releases can be scheduled to run periodically, with an option to do Manual release anytime you need. Any changes (disk expansion, new build, changed alert definitions) during the period are accumulated and executed in the next scheduled or manual release.

### Three-Way Comparison

Releases involve a three-way comparison that includes checking:

1. Current state of the environment
2. State defined in generated Terraform configuration files from blueprint
3. Desired end state. 

After comparison, the necessary changes to reach the desired state are deployed.

## Types of Releases in Facets

The following are the various types of releases available in Facets:

1. **Full Release:** The default release type, this is used for synchronizing all changes in an environment.
2. **Selective Release:** This release type allows for selective deployment of services or changes, commonly used for out-of-turn hotfixes in environments.
3. **Plan Release:** Provides a preview of all changes that will be made during the release, allowing for review and approval before applying changes.
4. **Custom Release: **This release type allows power users to issue direct Terraform commands, giving them greater control and flexibility in their deployments.
5. **Queued Release: **This feature allows the system to automatically add a new, manually triggered release to a queue while another release is already in progress. This allows you to initiate releases without the need to wait for the current one to complete.
6. **Launch Release:** Used for launching a new environment for the first time.
7. **Destroy Release:** Used to destroy all resources provisioned by Facets.

In addition, Terraform logs are available for power users to view detailed information about the changes made during each release. By using releases in Facets, organizations can have a well-defined and automated process for deploying changes to their cloud environments, which helps reduce the risk of errors and makes it easier to roll back if necessary.

## FAQs

### 1. What is a release in Facets?

Releases in Facets are a streamlined way of deploying changes to cloud environments. They are executed using Terraform apply commands and perform a three-way comparison of state to determine and deploy the necessary changes to the corresponding cloud environment.

### 2. What is a Full Release in Facets?

A Full Release in Facets is the default release type and is used for synchronizing all changes in an environment.

### 3. What is a Selective Release in Facets?

A Selective Release in Facets allows for selective deployment of services or changes, commonly used for out-of-turn hotfixes in production environments.

### 4. What happens to a scheduled release when there is a release already queued?

In such scenarios, the scheduled release gets skipped. It does not enter the queue or interrupt the current release process.