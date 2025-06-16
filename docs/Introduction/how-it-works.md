---
title: How it works?
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
### Core Components

1. **Intents**: High-level specifications of infrastructure requirements (e.g., database, cache).
2. **Flavors**: Specific implementations that fulfill the Intents, represented by Terraform modules.
3. **Packs**: Ops curated collections of Intents and Flavors to standardize infrastructure options.
4. **Blueprints**: Product architectures created by developers using Intents and Flavors, deployable across environments.

***

## 1. Facets Architecture Flow

The Facets architecture flow outlines the process from defining infrastructure requirements to deploying a product in the cloud, without including Packs.

### Steps in the Architecture Flow

1. **Building Blocks**: Terraform modules (Flavors) curated by Ops, serving as reusable modules for infrastructure definitions.
2. **Intents and Flavors**: Developers specify high-level requirements using Intents, linked to Flavors that provide the actual infrastructure implementations.
3. **Blueprints**: Developers construct Blueprints by selecting Intents and corresponding Flavors to define the architecture of their product.
4. **Orchestrator**: Transforms the Blueprint into deployable Terraform code.
5. **Managed Pipeline**: Executes the generated code, deploying the product to the cloud infrastructure.

### Diagram of the Architecture Flow

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3f0b209c5c2d1c296730b768fb91e81577f72db877edaafea419704e13be07f-mermaid-diagram-2024-11-08-003648.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


***

## 2. Intents and Flavors

Intents and Flavors are abstractions in Facets that decouple infrastructure requirements from their implementations.

### Intents

- **Definition**: High-level declarations of what a product needs, such as a database or a load balancer.
- **Purpose**: Allow developers to specify infrastructure requirements without detailing specific cloud resources or configurations.
- **Example**: An Intent might be "Database," indicating the need for data storage capabilities.

### Flavors

- **Definition**: Specific implementations that fulfill the Intents, represented by Terraform modules.
- **Purpose**: Provide the actual infrastructure setup that satisfies the requirements specified by Intents.
- **Customization**: Flavors can be configured within the Facets UI to meet various requirements.
- **Example**: Flavors for a "Database" Intent could include AWS RDS, GCP Cloud SQL, or Azure Database services.

### How They Work Together

1. **Requirement Specification**: Developers select an Intent to express a need (e.g., "I need a Database").
2. **Implementation Mapping**: The Intent is linked to a Flavor that provides the specific implementation in the chosen cloud environment.
3. **Code Generation**: The Orchestrator uses the Intent-Flavor combination to generate Terraform code for deployment.

***

## 3. Module Packs in Facets

Packs are collections of Intents and Flavors managed by Ops teams. They act as a registry of infrastructure capabilities, allowing developers to access reusable definitions for consistent infrastructure deployment.

### Types of Packs

- **Facets Module Packs**: These are provided by Facets, including pre-configured Intents and Flavors designed to cover standard infrastructure needs.
- **User-Created Packs**: Created by organizations to include custom Intents or additional Flavors for existing Intents, tailored to specific infrastructure needs.

### Function of Packs

1. **Ops Setup**: Ops teams create Module Packs by organizing relevant Intents and corresponding Flavors.
2. **Standardization and Flexibility**: Custom Packs allow organizations to define new infrastructure requirements or specify additional Flavors for existing requirements.
3. **Developer Use**: Developers select Intents from Packs to create their product architecture, a Blueprint.

Packs act as a centralized registry, simplifying access to reusable infrastructure definitions and promoting consistency across products and environments.

***

## 4. Blueprints

Blueprints represent the architecture of a product as defined by developers, enabling consistent and repeatable infrastructure deployments.

### Creating Blueprints

1. **Selecting Intents and Flavors**:
   - Developers choose Intents from Packs to specify the infrastructure requirements of their product.
   - For each Intent, a corresponding Flavor is selected based on the target cloud environment or implementation needs.

2. **Orchestration and Deployment**:
   - The Orchestrator translates the Blueprint into Terraform code.
   - The Managed Pipeline executes the code, deploying the infrastructure to the cloud.

### Diagram of the Blueprint Flow

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07798005642efa238bd19e817e2e5898070560e3b8f8a38896afe99876035ca6-mermaid-diagram-2024-11-08-011619.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Summary

Facets provides a structured approach to infrastructure management by introducing abstractions that separate high-level requirements from specific implementations. Through the use of Intents, Flavors, Packs, and Blueprints:

- **Ops Teams**:
  - Define and manage reusable infrastructure options via Intents and Flavors within Packs.
  - Ensure deployments comply with organizational standards and policies.

- **Developers**:
  - Create product architectures using Blueprints by selecting Intents from Packs and assigning Flavors.
  - Focus on the functionality and requirements of their applications without handling low-level infrastructure code.

By adopting Facets, organizations can achieve scalable, maintainable, and compliant infrastructure deployments, aligning technical operations with business objectives.