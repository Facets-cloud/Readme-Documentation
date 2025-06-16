---
title: Project - kirti
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

A 'Project' in Facets is a comprehensive workspace that provisions the infrastructure and streamlines software development. It houses a Blueprint, which acts as your application's visual roadmap provisioning all the resources required for your Project, and Environments that are practical implementations of the Blueprint for software deployment on your selected cloud platform.

## Fixed and Environment-Specific Architecture

Every software architecture consists of two elements: fixed architecture and environment-specific architecture. The Blueprint in Facets represents the fixed architecture and provides sensible defaults for each environment. This implies that the Blueprint can be utilized as a starting point for setting up the software in any environment, with the flexibility to make modifications as necessary to meet specific requirements. The Blueprint acts as the source of truth for the software architecture and is an indispensable tool for both development and operations teams.

## Secrets and Variables

Secrets and Variables in Facets are key components for managing reusable configuration data. Secrets refer to encrypted data used for storing sensitive information, such as passwords or API keys, ensuring they remain secure and confidential. Variables, displayed in plain text, are used for non-sensitive data, encompassing system settings or configuration preferences.

## Resource Types/Intents

In Facets, a Project is made up of resource types, also known as intents. Each intent represents a specific component or resource within the software architecture, such as a database or cache, and adheres to a [defined schema.](https://github.com/Facets-cloud/facets-schemas#supported-services) This schema outlines the properties and attributes of each resource. It ensures consistency in the structure and format across all instances of a particular resource within the project.

## Resource

In a Project, each resource is defined using an Intent and adheres to the schema specified for that Intent. The resource types and their corresponding schemas offer a clear and concise overview of the resources required to operate the software. This approach ensures a consistent implementation of the system across all environments.

> The Project is stored in a Git repository and comprises a collection of JSON files. Each JSON file represents a resource or a configuration, providing a transparent representation of the software architecture.

## Flavors

Each resource in a Project can have an implementation, known as a "flavor". The Project describes the default flavor for each resource, but the flavor can be changed based on the needs of the environment. This allows for a high degree of customization and flexibility while still maintaining the structure and design of the overall system.

## FAQs

### What is a Project in Facets?

A Project in Facets is a comprehensive description of the architectural design of a software product, providing a clear picture of the overall system design.

### What are resource types/intents in Facets?

Resource types, also known as intents, represent distinct components or resources within the software architecture such as databases, caches, queues, and configurations. Each resource type has a defined schema to ensure consistent implementation.

### What is a resource in the Project?

A resource in the Project is defined using an Intent and follows the schema for that Intent, providing a clear representation of the resources required to run the software.

### What is the Project stored in?

The Project is stored in a Git repository and consists of a collection of JSON files depicting a resource or configuration.

### What are flavors in a Project?

Each resource in a Project can have an implementation, known as a flavor. The Project describes the default flavor for each resource, but it can be changed based on the needs of the environment.
