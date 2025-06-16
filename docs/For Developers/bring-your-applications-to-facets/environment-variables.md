---
title: Environment Variables
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
Managing environment variables in Facets.cloud provides a structured way to handle application configurations across different environments. Whether you're migrating from a .env file or a cloud provider's parameter store, here's how to set up your environment variables effectively.

To know more about what are secrets and variables in Facets, [Secrets & Variables](doc:secrets-variables-1)

## Setting Up Your Variables

### Migrating Existing Variables

* Review your current .env files or configuration management
* Identify variables that should be project-wide vs resource-specific
* Determine which values need environment-specific overrides

### Configuring in Facets

* Add project-wide secrets and variables from "Secrets and Variables" tab in your project. Configure auto-injection for commonly used variables to be used across all resources. 
* Navigate to your Service Configuration Tab and add resource-specific variables in "Environment Variables" section or in JSON configuration. Non-auto-injected variables if needed can be aliased in the resource as well.

### Managing Sensitive Data

* Use Secrets for sensitive values
* Only define secret keys in the blueprint
* Set actual values at environment level
* Utilise secret manager integration for enhanced security
