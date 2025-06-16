---
title: Core Concepts
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
This section introduces the foundational constructs that define how modules work in Facets. These concepts make it easier to build modular, composable infrastructure by standardizing how configuration and connections are defined.

We’ll start with the most fundamental building block: **types**, and then explore how they apply to inputs, outputs, and wiring.

***

### 🧭 Module Anatomy Overview

```text
╭────────────────────────╮        ╭────────────────────────────╮        ╭────────────────────────────╮
│ Module A (VPC)         │        │ Type System                │        │ Module B (GKE)             │
│ ─ Outputs:             │        │ - @outputs/vpc             │        │ ─ Inputs:                  │
│   - default            │──────▶ │ - Declared in facets.yaml  │◀────── │   - network: @outputs/vpc  │
╰────────────────────────╯        ╰────────────────────────────╯        ╰────────────────────────────╯
           ▲                                                              │
           │                                                              ▼
 Written by module author                                 Consumed by another module

╭────────────────────────╮
│     Developer View     │
│ ─ spec:                │
│   - region             │
│   - node_count         │
│   - schedule           │
╰────────────────────────╯
            ▲
            │
Consumed via Facets UI/API
```

This diagram shows how modules define and consume inputs and outputs using a shared type system. Types enable compatibility across independently authored modules, while the `spec` defines the user-facing configuration shown to developers.

This diagram shows how modules define what they expose and what they expect — using a type-driven model. These types are declared in the `facets.yaml`, and the system uses them to wire modules together safely.

***

### 🧬 Types

Types define the shape and purpose of values that flow between modules. They follow a common pattern: `@outputs/xyz`, where `xyz` is the type name — like:

* `@outputs/vpc`
* `@outputs/project`
* `@outputs/cluster`

Types are:

* Defined by module authors or organizations
* Stored and versioned in the Facets registry
* Reused across modules to ensure compatibility

> Think of types as shared contracts. They let modules snap together, even if they were developed independently.

***

### 📊 Developer Inputs (spec)

Each module defines a `spec`, which represents the set of inputs that a developer is allowed to configure. These inputs map to familiar concepts in your organization such as `region`, `node_count`, or `project_id`.

These values:

* Are structured and validated
* Power the form-based UI and JSON input options
* Allow developers to focus only on what they need to configure

> The `spec` defines the developer-facing contract. It is used in the Facets UI and API to provide a clean configuration experience.

***

### 🧩 Inputs from Other Modules

Modules can also accept values that come from the outputs of other modules. These are defined in the `inputs:` section of the module's definition.

Each entry in the `inputs:` section defines:

* A key name (e.g., `network`)
* The expected type (e.g., `@outputs/vpc`)

At deployment time, Facets connects these inputs to outputs from upstream modules of the same type.

**Example:**

* A Kubernetes cluster module may require a VPC with `@outputs/vpc`
* That input could be fulfilled by any module exposing that type — such as a VPC module or a landing zone setup

> This model allows modules to be reused flexibly across environments and use cases.

***

### 📤 Outputs

Modules expose one or more outputs that can be consumed by other modules. Each output has:

* A key (e.g., `default`, `attributes.project_id`)
* A type (e.g., `@outputs/project`, `@outputs/project_id`)

These outputs are referenced by other modules using the type system — ensuring compatibility and discoverability.

**Example:**\
A GCP project module might expose:

* `default`: of type `@outputs/project`
* `attributes.project_id`: of type `@outputs/project_id`

> Outputs make a module usable by others. Types make that usage safe and predictable.

***

In the next section, we’ll walk through how to structure and build a Facets module using these principles. Coding specifics will be covered separately.
