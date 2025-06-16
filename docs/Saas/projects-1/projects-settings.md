---
title: Projects Settings
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
This guide explains how to configure and manage project settings within Facets.cloud. Each section of this document corresponds to a specific feature or configuration option available in the Project Settings UI. Follow the guide sequentially or navigate to the section relevant to your current task for quick assistance.

## General Settings

Define basic details about the project and specify the allowed cloud providers for hosting.

1. Edit Project Name: The "Project Name" is unique and cannot be changed after creation.
2. Add/Update Description: Describe the purpose or scope of the project in a few words for clarity.
3. Allowed Clouds: Select the cloud providers where your project can be hosted. Available options include AWS, Azure, GCP, and Kubernetes.
4. Click on the "Save Changes" button to confirm updates.

## GitOps Settings for Project Overrides

Integrate version control and manage project overrides through GitOps.

1. Choose Account: Select the Git account to connect with Facets.
2. Repository URL: Add the Git repository URL. This can only be set once.
3. Branch: Specify the branch you want the project to sync with (e.g., master).
4. Relative Path: Provide the relative path to project files within the repository.
5. GitOps for Overrides: Enable this option to centralize override management in Git. Once activated, this setting cannot be disabled. 
   1. Use the "Restrict Changes from UI" toggle to ensure changes can only be made via Git.
6. Save changes to finalize the configuration.

## CI/CD Settings for the Project

Manage the project's CI/CD flow and map Git branches to environments.

1. Select CI/CD Strategy:
2. Choose from the following strategies:
   1. Branch Per Environment: Separate branches for each environment.
   2. Single Branch Promotion: A single branch is promoted across environments.
   3. Advanced: Complex workflows where branches map to multiple environments.
3. Map Git Branch to Environment: Define how Git branches relate to environments using rules like:
   1. Contains: Match branches containing a specific string.
   2. Starts With: Match branches starting with a prefix.
   3. Ends With: Match branches ending with a suffix.
4. Set Promotion Workflow: Define the hierarchy for promoting artifacts across environments (e.g., from aws-infra-test to aws-infra-dev).
5. Save Changes: Ensure all settings are saved to apply updates.

## Delete a Project

1. Click Delete in the Danger Zone section.
2. In the confirmation pop-up, type Confirm to verify your intent.
3. Click Delete again to complete the process.

Note: Deleting a project will permanently remove all associated data. Ensure you have backups or no longer need the data before proceeding.
