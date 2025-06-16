---
title: Why Use Guardrails
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
# What Are Guardrails?

Guardrails in Facets are policy-based controls implemented through Rego code that help organizations establish and enforce standards across their cloud infrastructure. They act as protective barriers that prevent deployments from violating organizational policies, security requirements, and best practices.

## Why Use Guardrails?

As organizations scale their cloud infrastructure, the complexity of blueprints increases, creating potential for configuration drift, security gaps, and compliance issues. Guardrails provide several critical benefits

1. **Standardization: **Ensure all blueprints follow organizational standards, preventing configuration drift across environments and teams.
2. **Security:** Block deployments with insecure configurations, enforcing proper access controls and network security policies.
3. **Cost Control: \*\***Prevent resource overprovisioning by setting limits on compute resources and enforcing cost-efficient scaling parameters.
4. **Compliance:** Automate enforcement of regulatory requirements and internal policies, keeping infrastructure audit-ready.
5. **Error Prevention:** Catch configuration mistakes early in the deployment process, reducing failures and eliminating time-consuming manual reviews.

# Common Use Cases for Guardrails

Guardrails provide policy enforcement capabilities for your Facets resource specifications, these can be specific to the entire environment or blueprint: 

## Compliance Validation

- Enforce data residency by ensuring resources are only deployed in approved regions
- Implement required logging and monitoring configurations to meet regulatory standards
- Verify that data retention policies match compliance requirements

## Security Enforcement

- Require encryption for all data storage resources, both at rest and in transit
- Enforce secure network configurations with appropriate VPC settings and security groups
- Prevent public exposure of sensitive services and databases

## Infrastructure Governance

- Require consistent naming conventions across all resources and environments
- Enforce standardized tagging strategies for resource ownership and cost allocation
- Implement backup and disaster recovery configurations for critical resources
- Standardize monitoring and alerting configurations across teams

## Resource Optimization

- Prevent over-provisioning by enforcing resource limits by environment type
- Ensure cost-effective instance types and sizes based on workload requirements
- Require auto-scaling configurations to have appropriate minimum and maximum values