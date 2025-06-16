---
title: What is Facets?
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
## What is Facets.cloud?

Facets.cloud is a **platform engineering orchestration tool** designed to streamline cloud infrastructure management for **developers** and **Platform Engineering teams** (formerly DevOps teams). It automates the entire process of provisioning infrastructure, deploying applications, and configuring environments, reducing complexity and enabling both teams to focus on their core tasks.

**Note:** In Facets.cloud, **automations** refer to **Infrastructure as Code (IaC)** and scripts (such as Terraform, Helm, and other custom scripts) used to create and manage fully functioning cloud environments. These automations cover infrastructure provisioning, monitoring setup, alerting, logging, and more.

***

## Why Facets.cloud?

In traditional workflows, managing cloud environments involves significant manual effort, requiring both developers and DevOps teams to work across multiple tools and runbooks. Developers often face tool overload, while DevOps teams manually handle infrastructure scripts, monitoring, cost management, and governance enforcement.

Facets.cloud solves this by providing a self-service platform where developers request the infrastructure and services they need, and Platform Engineering teams define automations and policies that ensure standardized, secure, and scalable environments. This model reduces the manual intervention and cognitive load for both teams.

### Key Features

- **Fully Automated Environments**: Facets.cloud handles everything from infrastructure provisioning to monitoring, logging, and scaling based on predefined automations.

- **Developer Self-Service**: Developers can manage and deploy their applications without needing manual intervention from the Platform Engineering team.

- **Multi-Cloud Support**: The platform supports AWS, GCP, Azure, and Kubernetes, enabling teams to manage environments across multiple cloud providers with the same automation.

- **Built-in Governance**: Platform Engineering teams can define policies and guardrails that enforce best practices, ensuring only approved configurations are used.

- **Reusable Automations**: Automations, written once, can be reused across multiple projects and environments, reducing the need for custom scripts.

***

## Typical workflow in  Facets.cloud

1. **Developers Define Intents**: Developers specify their needs (e.g., a MySQL database or Redis cache) through a simple interface.

2. **Platform Engineering Team Defines Automations**: The Platform Engineering team creates automations to provision and manage infrastructure. These automations are IaC (e.g., Terraform) and other scripts, ensuring environments are created consistently and efficiently.

3. **Facets.cloud Automates Provisioning**: Facets.cloud automatically provisions and configures environments based on developer intents and Platform Engineering automations, ensuring compliance with predefined policies.

4. **Governance and Guardrails: **The governance team defines security, compliance, and operational guardrails, ensuring that all environments adhere to organizational standards and best practices.

5. **Environments as a Service**: Whether it's a development, QA, or production environment, Facets.cloud automates the entire process, allowing you to spin up fully managed environments quickly and consistently.

The diagram below illustrates how Facets.cloud integrates the different teams, automations, and workflows to create a unified cloud management experience:

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


***

## Benefits of Using Facets.cloud

### For Platform Engineers (formerly DevOps teams)

- **Standardized Automation**: Create and reuse automations across projects, reducing manual effort and improving consistency.
- **Reduced Operational Overhead**: Automations reduce the number of support tickets and manual tasks, freeing up time for strategic work.
- **Governance and Compliance**: Ensure compliance with organizational policies by defining guardrails and enforcing best practices automatically.
- **Multi-Cloud Flexibility**: Manage environments across AWS, GCP, Azure, and Kubernetes without needing custom scripts for each platform.
- **Infrastructure as Code**: Automations dynamically generate Terraform, Helm, and other infrastructure code, reducing the need to write and maintain code manually.

### For Developers

- **Self-Service Environment Management**: Request and manage environments without relying on Platform Engineering teams for day-to-day tasks.
- **Focus on Application Logic**: With infrastructure handled automatically, developers can focus on writing code and deploying applications.
- **Consistent and Reliable Environments**: Environments are provisioned with consistent configurations, reducing the risk of errors or misconfigurations.
- **Faster Time to Deployment**: Spin up environments quickly, enabling faster testing and deployment cycles.
- **Visibility and Control**: Integrated monitoring and logging allow developers to track the health of their services without additional setup.

***

## Conclusion

Facets.cloud enables organizations to adopt a **Platform Engineering** approach, where automation and governance are key to scaling cloud environments efficiently. By providing a self-service platform for developers and automated workflows for Platform Engineering teams, Facets.cloud reduces manual effort, improves consistency, and accelerates delivery. With support for multiple cloud providers and reusable automation, Facets.cloud ensures that cloud infrastructure is managed efficiently and reliably, no matter how complex the environment.