---
title: Types of Resources
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

Facets supports flexible resource management through different resource types and environment dependencies, enabling efficient infrastructure reuse and cost optimisation. This comprehensive guide covers the three resource types and their benefits.

## Resource Types

### Normal Resources

Standard resources defined in the project blueprint that are deployed independently for each environment.

**Behavior**

* Deployed separately for every environment through the releases mechanism
* Each environment maintains its own instance of the resource
* Full lifecycle management (create, update, delete) handled by Facets
* Complete isolation between environments

**Use Cases**

* Application-specific databases
* Environment-specific load balancers
* Dedicated storage volumes
* Production-critical resources requiring isolation

### Inherited Resources

Resources that are shared between base (parent) and child environments, where the child environment uses the same instance deployed in its parent environment.

**Key Characteristics**

* **Definition Configuration:** Resources can be marked as inherited at the project blueprint level as well as at the child environment level.
* **Multi-Parent Support:** If multiple parent environments exist, each child inherits from its designated parent is the resource is marked as inherited at the project blueprint level.
* **Parent-Child Relationship:** Child environments automatically inherit the resource instance from their respective parent environment
* **No Separate Deployment:** Inherited resources are not deployed separately for child environments

**Example Scenario:**

> **Production Environment (Parent)**\
> ├── Shared Database (Inherited)
> ├── Monitoring Stack (Inherited)
> └── **Child Environments**
> ├── Staging → Inherits Database & Monitoring from Production
> └── Testing → Inherits Database & Monitoring from Production

### Provided Resources

External resources managed outside of Facets that are referenced within the blueprint for configuration and dependency purposes.

**Characteristics**

* **External Management:** All lifecycle operations (provisioning, updates, deletion) handled outside Facets
* **Reference Only:** Facets maintains resource definitions for dependency mapping and configuration reference
* **No Direct Control:** Facets does not perform any direct operations on these resources
* **Blueprint Integration:** Can be included in blueprints for documentation and dependency visualization