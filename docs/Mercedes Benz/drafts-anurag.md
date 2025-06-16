---
title: Drafts - Anurag
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
## [IaC in Facets](doc:iac-using-facets)

Facets harnesses Infrastructure as Code (IaC) to empower teams with self-service capabilities, automating infrastructure deployments with precision. Facets' version-controlled IaC streams ensures a stable production environment while allowing space for testing and experimentation. Major and minor versioning further enhance the platform's reliability, enabling significant updates and incremental improvements without disrupting your workflow.

## [Resource JSON](doc:resource-json)

Resource JSON serves as the backbone of Facets' infrastructure definition, encapsulating the details of each resource within your software architecture. This structured format, stored in Git, defines every aspect of a resource, from type to specific configurations, ensuring consistency across environments. By utilizing JSON files, Facets provides a clear, version-controlled blueprint of your infrastructure, allowing for precise management and customization of your cloud resources.

## [Custom Terraform Modules](doc:custom-terraform-modules)

Custom Terraform Modules in Facets bring simplicity to cloud resource management, allowing users to select and configure modules based on 'intent' and 'flavor'. This democratizes IaC usage, enabling those without deep IaC knowledge to deploy infrastructure with ease. By defining JSON inputs, module implementers set the abstraction level, allowing users to focus on specifications rather than intricate code details.