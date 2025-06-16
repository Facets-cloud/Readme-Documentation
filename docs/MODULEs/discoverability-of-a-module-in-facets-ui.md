---
title: Discoverability of a Module
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

The Module Registry acts as a centralized interface for discovering, managing, and consuming Terraform modules across your organization. It brings both **system-provided modules **(maintained by Facets) and **custom modules **(developed by your teams) into a single, searchable registry. 

This registry enables platform teams to standardize infrastructure deployment through reusable components, reducing duplication of effort and ensuring consistency across environments.

***

## Key Concepts

### Intent, Flavor & Version (IFV)

Each module in Facets is defined by an Intent-Flavor-Version (IFV) tuple:

- Intent – What infrastructure capability the module provides (e.g., Redis, VPC)
- Flavor – The implementation choice for that intent (e.g., memorystore, GKE)
- Version – The specific revision of the implementation

This structure ensures clarity in module purpose, flexibility in implementation, and traceability across versions.

### Module States

Custom modules exist in two possible states:

- Preview – In development or testing; not available for production
- Published – Validated and ready for organization-wide use

***

## Using the Module Registry

The Module Registry interface is divided into two main tabs, where users can search and filter modules by Intent, Flavor, Version, and supported cloud providers to quickly find the modules they need.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fjvelwei4ptci&display_name=Storylane&url=http%3A%2F%2Fapp.storylane.io%2Fshare%2Fjvelwei4ptci&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_53b7f481-7852-4388-9e68-1ed5255ad7c0%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"449\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "http://app.storylane.io/share/jvelwei4ptci",
  "title": "System Modules | Apr 7 3:32 PM",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_53b7f481-7852-4388-9e68-1ed5255ad7c0/preview.gif",
  "provider": "app.storylane.io",
  "href": "http://app.storylane.io/share/jvelwei4ptci",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

1. **System Modules**, which are pre-configured Terraform modules provided by Facets. These modules:

- Are maintained and updated by the Facets team
- Cannot be modified directly by users
- Provide standardized implementations for common infrastructure needs

2. **Custom Modules**, which are created and maintained by your organization. These modules:

- Can be in either Preview or Published state
- Are owned by specific users or teams within your organization
- Support versioning to track changes over time
- Can be published to make them available organization-wide or kept in preview state during development and testing phases.

***

## Viewing Module Details

When you select a specific module from either the System Modules or Custom Modules tab, you'll be taken to a detailed view that provides comprehensive information about the module. 

The module details page includes several type of details:

1. **ReadME**: Documentation explaining the module's purpose, requirements, and usage instructions
2. **Spec & Sample**: Contains two sub-sections:
   - **Spec**: JSON schema defining the module's configuration parameters
   - **Sample**: Example configuration demonstrating proper module usage
3. **Output**: Displays the module's output variables that can be referenced by other resources
4. **History**: Version control information showing changes over time of any custom published module.