---
title: Facets Architecture
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
## Overview

Facets is a self-serve infrastructure platform that fundamentally transforms how organizations deploy and manage cloud resources. Unlike traditional Infrastructure as Code approaches that require maintaining countless Terraform files across environments, Facets enables users to define their infrastructure once through a blueprint and deploy it consistently across multiple environments.

### The Blueprint Approach

In traditional infrastructure management, with n resources across m environments, teams must maintain n×m configuration files. Facets eliminates this complexity through blueprints:

* Blueprint serves as a single source of truth
* Resources are defined as JSON files (like Lego pieces)
* Environment-specific configurations are handled through overrides
* All definitions are stored in version-controlled repositories

### What Makes Facets Architecture Unique

The main control plane (root) that powers Facets for all our customers is deployed and managed through Facets itself. The standout feature of our architecture is its modular design. Instead of creating automations for each customer, we use a capability-based approach. This means we build reusable components that make managing infrastructure simpler, consistent, and more efficient.

***

### Benefits of Facets Architecture

Facets automates the complex machinery of infrastructure management:

**Simplified User Experience**

* Users provide only the essential configuration, not detailed Terraform
* Standardised Architecture: Facets modules ensure consistent, best-practice implementations
* Automated Upgrades: Backend handles Kubernetes and module upgrades without user intervention
* Multi-Environment Consistency: Same blueprint works across development, staging, and production
* Reduced Maintenance: No need to manage numerous Terraform files and CI/CD pipelines

**In Practice**, for DevOps teams, this means:

* Defining infrastructure once rather than per environment
* Focusing on business requirements instead of Terraform syntax
* Standardising infrastructure across teams and projects
* Eliminating configuration drift between environments
* Reducing the risk of deployment failures

***

### Conclusion

Facets abstracts infrastructure complexity, allowing DevOps engineers to focus on defining intent rather than managing execution. By automating JSON-to-Terraform conversion, handling environment-specific overrides, and executing deployments in a controlled manner, Facets enables reliable, scalable, and consistent infrastructure provisioning.
