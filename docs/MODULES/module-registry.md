---
title: Module Registry
deprecated: false
hidden: false
metadata:
  robots: index
---
The **Module Registry** in Facets provides a centralized, searchable **catalogue of all infrastructure modules** available within a Control Plane (CP). It includes both system-provided **Facets Modules** and Organisation-authored **Custom Modules**, enabling teams to discover, understand, and manage reusable building blocks across environments and projects.

As we know by now, in Facets, a module is defined by a unique combination of:

* **Intent**: the capability being provisioned (e.g., postgresql-db)
* **Flavor**: the implementation of that intent (e.g., rds, gke, etc.)
* **Version**: the iteration of the module (e.g., 1.0, 2.1)