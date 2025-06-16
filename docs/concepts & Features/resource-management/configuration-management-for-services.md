---
title: Secrets and Variables
excerpt: Managing Secrets and Variables in Services Using Environment Variables
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Introduction

This document outlines best practices for managing secrets and variables within Facets services, specifically focusing on the use of environment variables. Facets allow for the secure and flexible handling of configurations, enabling services to access secrets and variables through various methods.

## Direct Addition of Variables to Service Blueprint

### Overview

Variables can be directly added to the service's blueprint file in JSON format, with the capability for environment-specific overrides.

#### How to Add Variables

1. **Access Blueprint File**: Open your service's JSON blueprint file.
2. **Insert Variables**: Add your variables in the `env` section of the blueprint.
3. **Override Per Environment**: Customize variable values for each environment as required.

#### References

* Blueprint Structure: [Facets Service Schema](https://facets-cloud.github.io/facets-schemas/schemas/service/service.schema.md)
* Blueprint Context: [Facets Resource JSON Documentation](https://readme.facets.cloud/docs/resource-json)

## Utilizing Secrets and Variables

### Overview

In Facets, you can define secrets and variables, then link these to environment variables using dynamic referencing.

#### Implementing Secrets and Variables

1. **Define Secrets and Variables**: Set up your secrets and variables in the Facets interface.
2. **Dynamic Referencing**: Connect these to your service's environment variables using the dollar referencing method.

#### Example

* **Dollar Referencing**: Implement references such as `${blueprint.self.variables.xyz}` in your blueprint file.

#### Documentation

* Blueprint Customization: Dynamic Referencing Guide

## Reading Secrets and Configurations from External Resources

### Overview

Services can access secrets and configurations from external resources in Facets, employing dynamic referencing for integration.

#### Steps for Implementation

1. **Utilize Resource Referencing**: Apply the dollar referencing syntax to link external resources' secrets and configurations.
2. **Example Use Case**: Reference external database credentials in environment variables.

#### Example

* **External Database Reference**: Use syntax like `${postgres.default-db.out.interfaces.writer.host}` to link external database host information.

## Conclusion

Understanding and utilizing the capabilities of Facets for managing secrets and variables through environment variables is crucial for enhancing the security and flexibility of your applications. This guide aims to provide you with the foundational knowledge to implement these practices effectively.

# Frequently Asked Questions (FAQs)

## Managing Secrets and Variables in Facets

### Q1: How do I add a variable directly to a service blueprint?

**A:** Variables can be added directly in the JSON blueprint file of the service. Insert the variables in the `env` section of the blueprint. These can be customized per environment as needed.

### Q2: What is dynamic referencing in Facets, and how is it used?

**A:** Dynamic referencing in Facets is a method to link secrets and variables to environment variables. It uses a dollar referencing syntax (e.g., `${blueprint.self.variables.xyz}`) to connect defined secrets and variables in the Facets interface to your service's environment variables.

### Q3: Can I use secrets and variables from other resources in my service?

**A:** Yes, you can use secrets and configurations from other resources. This is done by employing the dollar referencing syntax to link these external resources' secrets and configurations to your service's environment variables (e.g., `${postgres.default-db.out.interfaces.writer.host}`).

### Q4: How do I override variable values for different environments?

**A:** Variable values can be overridden per environment by specifying different values for the variables in the respective environment sections of the Service JSON  file.

### Q5: Where can I find more information on the structure of a service blueprint?

**A:** Detailed information on the structure of a service blueprint can be found in the Facets Service Schema at [Facets Service Schema](https://facets-cloud.github.io/facets-schemas/schemas/service/service.schema.md).

### Q6: Are there any best practices for managing sensitive information like passwords in Facets?

**A:** For managing sensitive information such as passwords, it is recommended to use the secrets management feature of Facets. Define these as secrets rather than plain variables and reference them using dynamic referencing to ensure they are securely handled.

### Q7: Can I reference variables and secrets defined in one service from another service?

**A:** No, if more than one service refers to the variable declare it globally.
