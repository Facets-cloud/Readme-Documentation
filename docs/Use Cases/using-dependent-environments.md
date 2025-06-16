---
title: Using Dependent Environments
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
Dependent Environments in Facets allow multiple projects or environments to share resources, offering flexibility and cost efficiency. This guide explains the primary use cases for dependent environments and the benefits they provide.

***

## Key Scenarios for Using Dependent Environments

The two primary scenarios for using dependent environments are **feature or non-production environments within the same project** and **shared non-production environments across projects**. Both scenarios optimize cost and simplify infrastructure management.

### 1. Feature or Non-Production Environments Within a Project

Dependent environments are useful for creating temporary or specialized environments within a project. These environments leverage shared infrastructure to:

- Reduce the setup time for new environments.
- Maintain consistency by reusing the same underlying resources.
- Facilitate the testing of new features without duplicating infrastructure.

Dependent environments can also utilize dedicated namespaces, allowing multiple non-production environments to coexist on shared infrastructure without interference.

#### Example

- A development team creates multiple feature branches for testing. These branches share the same Kubernetes cluster and database but operate in isolated namespaces to avoid conflicts.

### 2. Shared Non-Production Environments Across Projects

Different projects can share infrastructure for non-production environments to reduce costs. This is particularly useful when:

- Development and testing environments span multiple projects that require similar infrastructure components like networking and Kubernetes clusters.
- Production environments are isolated in separate infrastructure or accounts, but development environments benefit from shared resources.

#### Example

- Two projects, `ProjectA` and `ProjectB`, share a common VPC and Kubernetes cluster for their development environments while maintaining separate production setups. This reduces redundancy and lowers operational expenses.

***

## Benefits of Using Dependent Environments

1. **Cost Optimization:**
   - Shared resources improve utilization and reduce the need for redundant infrastructure.

2. **Simplified Management:**
   - The centralized infrastructure reduces the overhead of managing separate environments.

> 📘 Plan Resource Sharing Early
> 
> - Identify resources that can be shared during the planning phase to avoid future rework.

***

Dependent Environments in Facets provide an approach to managing shared infrastructure for feature and non-production environments. By leveraging this feature strategically, teams can achieve significant cost savings and operational efficiency.