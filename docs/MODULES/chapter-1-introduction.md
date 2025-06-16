---
title: Introduction
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
## 1.1 Overview of Facets.cloud

Facets.cloud is a modern platform engineering tool designed to simplify and streamline cloud infrastructure management. Unlike traditional Terraform scripts, which are often tied to specific projects, Facets.cloud focuses on creating modular, reusable capabilities that cater to various infrastructure needs. By providing a structured framework for Infrastructure as Code (IaC), it empowers teams to manage resources efficiently, with built-in governance, tool integrations, and automation.

Key features of Facets.cloud include:

- **Managed Delivery**: Automated deployment pipelines for consistent and reliable provisioning.
- **Dynamic Blueprints**: User-defined JSON configurations that abstract the complexities of Terraform.
- **Tool Integrations**: Seamless integration with monitoring, logging, and cost-optimization tools.
- **Governance and Policies**: Enforcing guardrails to ensure compliance and security.

With Facets.cloud, DevOps teams can transition from being task executors to strategic enablers, creating scalable solutions that developers can easily adopt.

***

## 1.2 The Role of DevOps in Modern Cloud Infrastructure

In traditional workflows, DevOps engineers often write Terraform scripts tailored to individual projects. While this approach works for small-scale setups, it presents significant challenges as organizations scale:

- **Complexity**: Managing multiple Terraform scripts across projects becomes cumbersome.
- **Lack of Standardization**: Inconsistent practices lead to errors and inefficiencies.
- **Slow Iterations**: Every project requires custom scripting, delaying delivery.

Facets.cloud addresses these pain points by shifting the focus from project-specific automation to capability building. Instead of writing Terraform code for each project, DevOps teams create reusable modules—representing high-level intents like "database" or "storage"—that developers can configure and deploy through simple JSON inputs. This paradigm ensures:

- **Reusability**: Modules can be adapted to multiple use cases.
- **Consistency**: Standardized outputs reduce integration issues.
- **Faster Delivery**: Developers can provision resources without needing deep Terraform expertise.

This shift aligns with the broader evolution of DevOps into platform engineering—enabling developers to build faster while maintaining operational control and governance.

***

## 1.3 Objective of the Tutorial

This tutorial is designed to equip DevOps engineers with the knowledge and skills to:

1. Understand the core concepts of Facets.cloud, including Intents and Flavors.
2. Transition from traditional Terraform workflows to Facets' modular approach.
3. Build custom Terraform modules that integrate seamlessly with Facets.
4. Empower development teams to use these modules effectively for their projects.

By the end of this guide, you will not only understand how to write and register custom modules but also appreciate how Facets.cloud transforms infrastructure management into a streamlined and collaborative process.

***

Next, we will explore the paradigm shift in depth and examine how Facets.cloud differs from the traditional approach to Terraform workflows.