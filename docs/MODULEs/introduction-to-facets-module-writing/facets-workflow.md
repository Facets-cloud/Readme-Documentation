---
title: Facets Workflow
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
Facets.cloud redefines how Ops and Dev teams collaborate by introducing a seamless workflow that integrates capability creation and project-specific automation. This chapter explores the roles of both teams, key concepts like Intents and Flavors, Bundles, and highlights the benefits of adopting the Facets workflow.

## How Facets Integrates Ops and Dev Workflows

Facets.cloud bridges Operations (Ops) and Development (Dev) teams to simplify infrastructure management and enhance collaboration. This aligns with the shift toward platform engineering, focusing on accelerating development while ensuring operational efficiency.

- **Ops Team's Contribution**: Creates reusable Terraform modules based on Intents and Flavors, embedding policies and logic to standardise and streamline processes, reducing the need for custom scripts.
- **Dev Team's Role**: Utilises these modules via declarative JSON configurations, focusing on project needs without dealing with Terraform complexities, speeding up time-to-market.
- **Unified Platform**: Provides a centralised interface for both teams to work independently yet cohesively, minimising handoff delays, bottlenecks, and conflicts while boosting efficiency.

***

## Intents and Flavors

Intents and Flavors are abstractions in Facets that decouple infrastructure requirements from their implementations.

**Intents**: High-level declarations of what a product needs, such as MySQL or Postgres, allowing developers to specify infrastructure requirements without detailing specific cloud resources or configurations.

- **Example**: An Intent might be "Database," indicating the need for data storage capabilities.

**Flavors**: Specific implementations that fulfill the Intents, represented by Terraform modules, providing the actual infrastructure setup that satisfies the requirements specified by Intents.

- **Customization**: Flavors can be configured within the Facets UI to meet various requirements.
- **Example**: Flavors for a "MySQL" Intent could include AWS RDS, GCP Cloud SQL, or Azure Database services.

**How They Work Together**

- **Requirement Specification**: Developers select an Intent to express a need (e.g., "I need a Database").
- **Implementation Mapping**: The Intent is linked to a Flavor that provides the specific implementation in the chosen cloud environment.
- **Code Generation**: The Orchestrator uses the Intent-Flavor combination to generate Terraform code for deployment.

***

## Ops Team's Role: Building Capabilities

The Ops team’s primary responsibility is to build modular capabilities that can be consumed across multiple projects. This involves:

1. **Defining Intents and Flavors**

2. **Embedding Operational Logic and Policies**:

   - Ops teams bake governance, security, and operational best practices directly into Terraform modules (as discussed in the Intents and Flavors section).
   - This ensures compliance and eliminates the need for developers to manually implement these standards.

3. **Centralized Module Management**:

   - All modules are centrally managed, ensuring version control and preventing inconsistencies across projects.

***

## Dev Team's Role: Consuming Capabilities

The Dev team focuses on leveraging the capabilities provided by the Ops team to meet project-specific needs. Key responsibilities include:

1. **Declarative Configuration**:

   - Developers specify their infrastructure requirements in declarative configurations (e.g., YAML or JSON formats).
   - These configurations are mapped to the predefined Intents and Flavors.

2. **Project-Specific Automation**:

   - Dev teams build and deploy infrastructure using Facets.blueprints, combining multiple capabilities into a cohesive architecture.
   - This approach minimizes the need for deep Terraform knowledge while allowing for rapid iterations.

***

## Benefits for Both Teams

Facets.cloud simplifies workflows for both Ops and Dev teams, delivering several key benefits like **reduced complexity**, **faster provisioning**, **consistent practices**, and **enhanced collaboration**.

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


By integrating Ops and Dev workflows, Facets.cloud enables teams to achieve operational excellence while empowering developers to focus on innovation. The next chapter will delve into the step-by-step process of creating, testing, and registering Terraform modules in Facets.cloud.