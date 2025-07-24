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

### How to use Secrets/Variables at Project Level?

<Embed typeOfEmbed="jsfiddle" url="https://app.storylane.io/demo/epex9h9k9ron" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fepex9h9k9ron%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fepex9h9k9ron%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_8bf28898-41bc-4163-a750-38004076e36d%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" href="https://app.storylane.io/demo/epex9h9k9ron" providerUrl="https://www.storylane.io" providerName="Storylane" />

> *Note: Select the**Auto Inject** checkbox to automatically add (auto-inject) the key-value pair to all the resources in the Blueprint.*

***

### Benefits

* **Single Source of Truth:** One place to define and manage all configurations
* **Environment Flexibility:** Override values as needed for different environments
* **Security First:** Proper separation of configuration and sensitive data
* **Simplified Management:** No need to maintain multiple environment-specific files
* **Developer Friendly:** Clear visibility of available variables and secrets

This approach transforms what was once a complex, risky process into a streamlined, secure system that scales with your needs.