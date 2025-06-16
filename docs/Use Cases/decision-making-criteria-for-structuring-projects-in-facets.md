---
title: Structuring Projects in Facets
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
Facets enables the organization of resources into **Projects**, representing groups of interconnected resources deployed together to deliver business value. This guide provides clear decision-making criteria for when to create new projects, why to avoid splitting a single product unnecessarily, and how to manage projects effectively within Facets.

***

## When to Think of a New Project

Creating a new project is a strategic decision that should be based on clear functional or operational requirements. Consider the following scenarios:

1. **Distinct Business Capabilities:**
   * Projects should align with specific business functionalities. For example, an organization managing a **Recommendation Engine** and an **E-Commerce Platform** might structure these as separate projects since they serve different purposes and operate independently.

2. **Operational Independence:**
   * Systems that function in silos or have minimal interaction are ideal candidates for separate projects.

***

## Why Not Split a Single Product Into Multiple Projects?

While it may seem intuitive to split a complex product into multiple projects, it often introduces unnecessary complexity. Instead, consider the following:

### 1. Use Resource Groups for Access Control

* If **RBAC (Role-Based Access Control)** is the reason for splitting, leverage **Resource Groups** instead. They provide logical separation and fine-grained access control without requiring a project split.
* More information: [Resource Groups Documentation](https://readme.facets.cloud/docs/user-management-2#resource-groups).

### 2. Facets Handles Large Terraform Projects

* If the concern is the size of the Terraform project, Facets abstracts Terraform state management and optimizes it for scalability and performance. There is no need to split projects solely due to size considerations.

***

## Features That Enable Large-Scale Project Management

### Abstracted State Management

* Automates Terraform state management, enabling scalability and reducing operational overhead.

### Performance Optimizations

* Enhances deployment efficiency, ensuring smooth operations even for large-scale environments.

### Unified Project Knowledge

* Offers a consolidated view of all resources and dependencies, improving transparency and eliminating redundant configurations.

### Key Benefits

* Simplified management of complex projects.
* Streamlined configuration management.
* Clear insights into resource relationships and dependencies.

***

By adhering to these criteria and leveraging Facets' capabilities, organizations can manage projects effectively without over-complicating their structure. Facets allows teams to focus on delivering business value while maintaining scalability and security.
