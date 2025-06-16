---
title: Environment
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
In Facets, environments are the specific deployment destinations for your cloud architecture blueprints. They represent the actual clusters where your applications and services are deployed. Think of them as the distinct spaces where your applications run, such as development, testing, or production .

## Key characteristics of environments in Facets:

**Deployment Target:** When you deploy a blueprint, you deploy it into a specific environment. This allows you to have different versions of your infrastructure running in different environments]. For example, you might have a development environment for testing new features and a production environment for your live application.

**Dynamic Configuration**: Each environment can have its own specific configuration. This allows you to customize the behavior of your application based on the specific environment it is running in. Facets injects environment variables at runtime, determining their values for each environment. This means that the same application can behave differently in different environments.

**Overriding Defaults:** You can set default values for variables at the project or service level and then override them at the environment level. This provides a hierarchical approach to configuration management, ensuring that each environment is tailored to its specific needs.

## Why Environments are Important in Facets:

**Isolation**: Environments allow you to isolate changes to your infrastructure. For example, you can test new features in a development environment before deploying them to a production environment.

**Consistency**: By using the same blueprint for different environments, you ensure consistent deployments across your application's lifecycle. Differences in configuration can be handled by environment variables.

**Centralized Management**: Facets manages all configurations using environment variables which are injected at runtime. This means you are managing all your configurations in a central place, and you aren't relying on scattered environment variables, secrets, or configuration files.

In summary, environments are the deployment locations for your Facets blueprints, enabling customization and isolation of your applications. They utilize environment variables to manage configurations, ensuring consistency, flexibility, and control over your deployments.