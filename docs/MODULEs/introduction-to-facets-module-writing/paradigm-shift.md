---
title: Paradigm Shift
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
## Challenges with Traditional Terraform Workflows

DevOps engineers have traditionally relied on Terraform to provision and manage cloud infrastructure. While effective for small-scale setups, this approach becomes increasingly difficult to maintain as organizations scale their operations. Common challenges include:

- **Project-Specific Customization**: Terraform scripts are often tightly coupled to individual projects, making them difficult to reuse or adapt for other use cases.
- **Complexity in Scaling**: Managing multiple scripts across teams and environments introduces significant complexity, leading to errors and inefficiencies.
- **Lack of Standardization**: Inconsistent practices across teams can result in misconfigurations, vulnerabilities, and resource mismanagement.
- **Slow Iterations**: Writing and maintaining custom Terraform scripts for every project consumes valuable time, delaying delivery and innovation.

Even attempts to address these challenges by writing reusable Terraform modules and integrating them into project-specific automation can still fall short:

- **Developer Abstraction**: Developers still face the challenge of understanding Terraform logic and module inputs, which can lead to errors and slow adoption.
- **Versioning and Central Sourcing**: Without proper management, module updates can cause breaking changes, and there is no central source ensuring consistency across projects.
- **Complex Collaboration**: Code reviews for Terraform changes become bottlenecks, as teams have to carefully sequence updates, execute changes one at a time, and manually handle conflicts. This limits parallel work and slows down overall productivity.

These issues highlight the need for a more comprehensive solution that not only emphasizes reusability but also provides better abstraction, collaboration, and central management.

***

## The Facets.cloud Approach

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ca61990453d35be136b268a3dbd010f96e353b43f96451fd55958a336a1f85b9-Screenshot_2024-08-08_at_1.36.02_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Facets.cloud introduces a paradigm shift by focusing on **capability-based modularity** instead of project-specific automation. At its core, Facets.cloud emphasizes two key concepts:

- **Intents**: High-level abstractions that define a resource type—for example, "Database" or "Storage." These intents act as reusable blueprints, allowing developers to specify their infrastructure needs without delving into low-level details.
- **Flavors**: Concrete implementations of these intents tailored to specific cloud providers or configurations (e.g., AWS RDS for a "Database" intent).

Key features of the Facets.cloud approach include:

- **Declarative Configurations**: Developers interact with infrastructure by writing declarative configurations based on the schema defined by the Ops team. This abstracts away the complexity of Terraform while ensuring a consistent user experience.
- **Versioning and Central Module Sourcing**: Facets.cloud centrally manages modules, ensuring consistent usage and seamless updates without introducing breaking changes.
- **Simplified Collaboration**: Facets.cloud generates the stitching logic for Terraform modules, allowing multiple team members to independently modify and execute Terraform configurations without conflict. This eliminates the need for complex PR reviews and manual coordination.
- **Standardized Outputs**: Modules adhering to an intent provide uniform outputs, enabling part-replacement and modular flexibility.
- **Built-In Governance**: Operational logic, guardrails, and policies are baked into the Terraform modules, ensuring compliance and security without additional overhead.
- **Faster Delivery**: By reusing modules and simplifying configurations, both Ops and Dev teams can accelerate infrastructure provisioning.

***

## Comparison: Traditional vs. Facets.cloud

| Aspect                    | Traditional Terraform             | Facets.cloud            |
| ------------------------- | --------------------------------- | ----------------------- |
| **Scope**                 | Project-specific                  | Capability-based        |
| **Developer Abstraction** | Low                               | High (JSON-driven)      |
| **Versioning**            | Manual, inconsistent              | Centrally managed       |
| **Collaboration**         | Sequential, bottleneck-prone      | Parallel, conflict-free |
| **Complexity**            | High (custom scripts per project) | Low (reusable modules)  |
| **Governance**            | Manual                            | Built-in                |
| **Time-to-Delivery**      | Slow                              | Fast                    |

In next chapter, we will see how transitioning to Facets.cloud will be beneficial for Operations Team as well as the Development Team in any organization.