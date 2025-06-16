---
title: Project Level Secrets and Variables in Facets
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
## The Traditional Challenge

Traditionally, managing environment variables and secrets across different environments has been a major pain point:

* Multiple environment-specific files to maintain
* Risk of secrets exposure in version control
* Complex secret rotation processes
* Difficulty in maintaining consistency across environments
* No clear separation between configuration and sensitive data

***

## Facets' Approach: Project-Level Source of Truth

<Image align="center" className="border" border={true} src="https://files.readme.io/0be3145bd079a346565e3b49745b85139c094ea772f3f1b3f664c4795d5b052c-Screenshot_2025-02-12_at_11.32.33_AM.png" />

### Variables Management

* **Project-Level Definition:** Define variables once at the project level as your source of truth
* **Key-Value Storage:** Each variable has a key and value defined at the blueprint level
* **Auto-Injection:** Mark variables for automatic injection across all resources
* **Resource-Level Flexibility:** Create aliases for specific resource usage when needed
* **Environment Overrides:** Override any variable at environment level without changing the source

***

### Secrets Management

* **Secure by Design:** Only secret keys are stored at project level
* **Environment-Level Values:** Secret values are stored securely in the environment's secret manager
* **Flexible Access:** Choose between auto-injection or selective usage through aliases
* **Safe Storage:** No sensitive data in version control
* **Easy Rotation:** Update secret values at environment level without touching the blueprint

***

### Benefits

* **Single Source of Truth:** One place to define and manage all configurations
* **Environment Flexibility:** Override values as needed for different environments
* **Security First:** Proper separation of configuration and sensitive data
* **Simplified Management:** No need to maintain multiple environment-specific files
* **Developer Friendly:** Clear visibility of available variables and secrets

This approach transforms what was once a complex, risky process into a streamlined, secure system that scales with your needs.
