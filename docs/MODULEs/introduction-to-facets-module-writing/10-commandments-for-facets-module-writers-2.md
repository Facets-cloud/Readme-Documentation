---
title: 10 Commandments for Facets Module Writers
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
# 1\. You’re Not Just Writing a Terraform Module—You’re Building a LEGO Block

Think of your module as a **LEGO block**, not just a Terraform module. It should be **self-contained, reusable, and designed for easy composition** rather than built as a **monolithic deployment**.

## What Makes a Great LEGO Block?

✅ **Plug-and-Play** – Your module should **snap into place effortlessly** with other modules.  
✅ **Independent Testability** – Each module should be **tested in isolation**, even if it depends on others.  
✅ **Validated Interactions** – Ensure **test setups include necessary input modules** to verify dependencies.

## Build for Modularity, Not Just Functionality

A well-designed LEGO brick **works in multiple builds**—similarly, your module should be **composable**, flexible, and easy to integrate **without unnecessary complexity**.

By treating modules as **interchangeable building blocks**, you **reduce maintenance, improve scalability, and enable seamless infrastructure assembly.**

# 2\. LEGO Bricks Connect at Specific Points – So Do Your Modules

A **LEGO brick has defined studs and sockets**, ensuring it connects seamlessly with other bricks. Similarly, **your module must have well-structured inputs and outputs** to integrate smoothly within Facets.

## Modules Function Like Well-Designed LEGO Bricks

- **Inputs** → These are the required parameters that dictate how your module operates.  
  - In Facets, **inputs come from typed outputs of other modules** (e.g., `@output/vpc`).  
- **Outputs** → These are the return values that other modules or users will consume.  
  - Outputs follow **Facets conventions** (e.g., `@output/databricks-workspace`).

Each module also has a **standard input** called `spec`, which contains **user-defined parameters**.

- This schema is **defined in `facets.yaml`**.  
- These inputs should be **abstracted appropriately** to ensure flexibility while maintaining simplicity.

## When Designing a Module, Ask:

✅ **Should my module consume outputs from another module?** (e.g., `@output/vpc` for networking dependencies)  
✅ **Should it expose outputs for other modules to consume?** (e.g., `@output/iam-policy` for permissions)  
✅ **Instead of defining providers in Terraform code, should it expose required configurations as outputs?**

By following this pattern, modules remain **flexible, composable, and reusable**—just like LEGO bricks that fit together effortlessly, no matter how the user chooses to build.

# 3\. Not All LEGO Bricks Belong in Every Kit – Design for the Right Audience

Not every user needs access to every configuration. Your module should be like a **LEGO brick designed for a specific kit**—some bricks belong in a **developer’s kit**, while others fit into a **platform engineer’s toolkit**.

- **Developers** shouldn’t have to configure infrastructure details like VPCs.  
- **Platform engineers** might need access to networking, IAM roles, or security settings.

## Reduce Cognitive Load Without Sacrificing Flexibility

✅ **Expose only what’s relevant** to the user’s role.  
✅ **Minimize required inputs**—users should provide only what’s necessary.  
✅ **Use sensible defaults** to reduce unnecessary configuration.

By designing modules **with the right audience in mind**, you ensure that each user gets **just the right LEGO bricks for their kit**—not more, not less.

# 4\. Oversized LEGO Bricks Limit Creativity – Keep Modules Small and Flexible

A **module that tries to do too much** becomes difficult to use and limits flexibility—just like an oversized LEGO block that doesn’t fit well with others.

Instead of building **one large, rigid module**, focus on creating **smaller, reusable blocks** that can be easily combined.

- **Smaller modules** allow users to compose infrastructure in a way that best suits their needs.  
- **Large, monolithic modules** force users to work around unnecessary complexity.

## Prioritize Usability Over Convenience

✅ **Design for composition**—modules should snap together seamlessly.  
✅ **Don’t optimize for ease of writing**—optimize for **ease of use** instead.  
✅ **Think like a builder**—users should be able to mix and match modules to create their ideal setup.

By keeping modules **small, focused, and reusable**, you ensure that users have the **right building blocks** to construct infrastructure **without unnecessary constraints**.

# 5\. LEGO Bricks Don’t Decide the Playground – Make Modules Adapt to Environments

In Facets, **users define environments**, not modules. Your module must be designed to work **without modification**, even when users add new environments.

- **Do not assume or hardcode environments in Terraform code.**  
- **Your module should generate resources dynamically** based on the environment provided by the user.

## Design for Environment Flexibility

✅ **Use environment-aware naming conventions** – e.g., include the environment name in resource identifiers when required.  
✅ **Allow per-environment customization** – Let users configure parameters like instance size, scaling, or security settings.  
✅ **Ensure consistent outputs** – Keep module outputs structured and predictable, regardless of the environment.

## Think of Modules as Adaptable Building Blocks

Your module is part of a **larger, reusable blueprint** that must work across multiple environments **without modification**. Users should be able to **instantiate new environments** by providing different inputs—without needing to change your module’s code.

# 6\. LEGO Bricks Need Studs and Sockets – Model Outputs for Seamless Connections

Just like LEGO bricks have **studs and sockets** to snap together, **your module must expose well-defined outputs** so other modules can integrate effortlessly.

- **If your module provisions a provider-like resource** (e.g., AWS IAM roles, Kubernetes clusters), expose them as outputs explicitly.  
- **Think from the perspective of the consuming module** – what does it need to integrate smoothly?

## Designing Outputs for Maximum Reusability

✅ **Expose only meaningful outputs** – Avoid dumping raw internal details; provide structured, useful outputs.  
✅ **Ensure consistency in output formats** – Keep naming predictable to make composition easier.  
✅ **Model dependencies explicitly** – If another module depends on an IAM role, expose it clearly instead of forcing assumptions.

By **defining outputs with clarity and purpose**, you enable **modular, flexible architectures**, where **modules snap together seamlessly**

# 7\. LEGO Manuals Include Labels – Outputs Should Guide Application Configuration

Just like a LEGO manual provides **clear labels for each piece**, your module’s outputs should serve as **structured references** not just for other modules, but also for users configuring their applications.

- Some outputs are for **module-to-module integration** (e.g., IAM roles, cluster IDs).  
- Other outputs are for **application configuration** (e.g., Postgres connection URLs, Redis ports).

### **Design Outputs for Configuration Usability**

✅ **Expose all outputs that users need for application configuration** – Even if they aren’t required by other modules.  
✅ **Keep outputs structured and predictable** – Users should be able to reference them logically in their app configs.  
✅ **Ensure outputs match real-world usage** – Example: If an application needs a database connection string, output it in a ready-to-use format.

**Not all outputs are for modules—some are for humans.** Your module should **act as a reliable reference** for users configuring their applications, just like a LEGO manual ensures every piece fits in the right place.

# 8\. Interchangeable LEGO Bricks – Use Intents for Flexible Implementations

Just like LEGO bricks can be used to build **a castle or a spaceship** with different colors or materials, **intents allow users to switch between different implementations while keeping the same structure.**

- **If your module is always used the same way, you don’t need an intent.**  
- **Intents become necessary when users need flexibility**—choosing between AWS RDS, Aurora, or PostgreSQL on Kubernetes, for example.

## When to Use Intents

✅ **If multiple implementations share a common interface** – The user should be able to swap implementations without changing their configuration.  
✅ **If execution details vary but the intent remains the same** – Example: A database module that supports both managed cloud databases and self-hosted options.  
✅ **If users need to choose between providers or platforms dynamically** – Ensuring consistency while enabling flexibility.

**Intents define what the module should do, while implementations handle how it’s done—just like LEGO bricks can be made from plastic, metal, or wood but still fit together.**

# 9\. A Strong LEGO Brick Supports Every Build – Design for Stability and Best Practices

Just like a **single weak LEGO brick** can compromise an entire structure, a **poorly designed module** can introduce **security risks, inefficiencies, and blind spots** in infrastructure.

A well-designed module ensures **stability, security, and efficiency** in every instance that uses it—**best practices should be built into the module itself, not left to users.**

## Key Principles of a Stable Module:

✅ **Security** – Follow the **least privilege principle** by default to minimize access risks.  
✅ **Observability** – Provide **built-in metrics, logs, and alerts** to help users monitor health and performance.  
✅ **Cost Efficiency** – Optimize resource usage to prevent unnecessary costs.

A **solid LEGO brick ensures structural integrity**—similarly, a **well-architected module** enforces **secure, observable, and cost-efficient** deployments **by design**.

# 10\. Designing a LEGO Brick Takes Engineering – Model It Carefully

Just like crafting a **LEGO brick that fits seamlessly into multiple builds**, designing a module **requires thoughtful engineering** to ensure it works across **various environments and use cases.**

## Why Careful Modeling Matters

✅ **A well-designed module eliminates thousands of lines of Terraform code** that users would otherwise write and maintain.  
✅ **Investing time upfront** reduces rework, debugging, and unexpected failures later.  
✅ **Consider different use cases, dependencies, and integration points** before finalizing the design.

## Build for Scalability, Not Just for Now

It’s okay to **pause and refine your design** rather than rushing into implementation. A **well-structured module ensures long-term stability, easier adoption, and a scalable infrastructure**—saving effort in the future.

**Engineering a LEGO brick takes precision—so does modeling a reusable, future-proof module.**