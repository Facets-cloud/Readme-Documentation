---
title: Basic Concepts
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
# Projects

A 'Project' in Facets is a comprehensive workspace that provisions the infrastructure and streamlines software development. It houses a Blueprint, which acts as your application's visual roadmap provisioning all the resources required for your Project, and Environments that are practical implementations of the Blueprint for software deployment on your selected cloud platform. For detailed instructions on setting up a Project, refer to the [Creating a Project](doc:creating-a-project) documentation.

<Image align="center" className="border" width="650px" border={true} src="https://files.readme.io/afdaca93df99481898bbb14a8d634ad6c47bccf809f59f395eadb2485d6d9a02-image.png" />

***

# Blueprint

Blueprints are declarative representations of your overall application's architecture. They serve as a comprehensive plan, enabling you to design every aspect of your product without deploying resources to the cloud. 

They encapsulate all configurations required to create and manage cloud environments, including resource definitions, service discovery, and secrets. Stored as files in a Git repository, blueprints provide a single source of truth for infrastructure design and deployment.

<Image alt="A sample blueprint in Facets" align="center" width="650px" border={true} src="https://files.readme.io/76b55224992469ea3c9dc728431d9ba9ebfcf833a78b6d50701f177dd186d042-image.png">
  A sample blueprint in Facets
</Image>

## Benefits of using Blueprints

### Consistency and Zero Drift

Blueprints ensure that all your environments follow the defined architecture unless explicitly overridden. You can always compare an environment against the blueprint defaults, maintaining consistency across deployments.

### Default Configurations

Blueprints let you set default configurations. For example, if you set your production configuration as the default, you can launch a performance environment identical to production whenever needed.

### Single Source of Truth

Blueprints act as a single source of truth for your infrastructure. They help you tag resources correctly for billing and cost tracking. Since blueprints capture everything needed to run an environment, including resource configurations, service discovery, and secrets, you can launch environments with a single click.

### Efficient Resource Management

Blueprints help you manage resources by defining and tagging them correctly. This ensures your cloud infrastructure is organized and costs are tracked accurately.

## Version Control with Git

Every Blueprints reside in a Git repository, so all infrastructure changes are versioned and under your control. This approach offers several advantages:

* **Versioning:** Fine-grained versions in resource configurations are beneficial as your team grows. You can use PR raise and merge flows similar to your code for infrastructure, observability, and application configuration changes.
* **Innovation:** Infra-as-Code files in JSON allow internal teams to be innovative. Some customers have written Slack bots for resourcse creation, policies to scan before each release, and automation to rightsize resources based on feedback from observability platforms.

***

# Resources

A resource in Facets refers to any cloud infrastructure component included in a Blueprint and deployed to an environment. This can range from fundamental elements like VPCs and Kubernetes clusters to application-specific components like databases, caches, and load balancers. For detailed instructions on provisioning resources within Facets, refer to the [Adding Resources ](doc:adding-resources)documentation.

## Understanding Intents

An Intent represents a high-level infrastructure requirement. When you're building an application, you think in terms of capabilities: "I need a database" or "I need a cache." You shouldn't need to worry about whether it's AWS RDS, GCP Cloud SQL, or which specific configuration parameters to set.

<Image align="center" className="border" width="350px" border={true} src="https://files.readme.io/d8fffcc0f9f3715207bad98d47d27b5b321ba3b63e319ca678c409534c996135-image.png" />

Here's how an Intent works in practice:

```yaml JSON
# Example Database Intent
{
  "kind": "postgres",
  "version": "0.1",
  "disabled": true,
  "metadata": {
    "tags": {
      "name": "postgres"
    }
  },
  "spec": { }
}
```

The Intent above declares a postgres intent what you need without specifying implementation details. It focuses on the essential characteristics your application requires. This abstraction allows you to maintain the same Intent across different environments or cloud providers.

## Working with Flavors

While Intents declare what you need, Flavors define how to provide it. A Flavor is a concrete implementation of an Intent, packaged as a Terraform module. Think of Flavors as the bridge between your high-level requirements and actual cloud resources. Each Flavor implements the same Intent differently, but they all satisfy the core requirements.

<Image align="center" className="border" width="350px" border={true} src="https://files.readme.io/093deca4a02ace682f79c63ff0e552c62caf502a957c834d93f4caf4f1e1ea2f-image.png" />

Here's how to assign a flavor:

```hcl JSON
# Example Database Flavor
{
  "kind": "postgres",
  "flavor": "k8s",
  "version": "0.1",
  "disabled": true,
  "metadata": {
    "tags": {
      "name": "postgres"
    }
  },
  "spec": { }
}
```

In the above, the Flavor we assign—"k8s" in this case—specifies how this database will be provisioned, packaged as a Terraform module tailored for Kubernetes deployment. This allows the Intent for PostgreSQL to be fulfilled in a way that’s consistent across different cloud environments, leveraging Kubernetes as a common infrastructure layer.

With an understanding of resources, intents, and flavors, you can define infrastructure components in Facets. By structuring these components, you can create an infrastructure blueprint tailored to your project’s needs.

***

# Environment

An Environment in Facets is a concrete implementation of a **Blueprint designed for a particular cloud infrastructure**. It contains all necessary resources, configurations, and services to run the software. 

<Image align="center" className="border" width="650px" border={true} src="https://files.readme.io/c4e61d475e3391f7a90d43fdf5871a4a0304ffd95c15c53a01a2c47a5a0ac686-image.png" />

## Base Environment

The term "Base Environment" is often referred with "Environment" when referring to a standalone environment that is created independently and operates without dependencies on other environments. Both terms refer to the same concept when there is no need for environment-specific dependencies. For detailed instructions on creating an Environment, refer to the [Creating an Environment](creating-an-environment) documentation.

## Dependent Environment

The Dependent Environment in Facets enables environments to inherit infrastructure, tools, and deployed resources from a specified Base Environment. This approach ensures consistency, minimizes duplication, and simplifies maintenance by allowing updates made to the base environment to propagate to dependent environments as needed. For detailed instructions on creating a Dependent Environment, refer to the [Dependent Environments](dependent-environments) documentation.

## Time-Sensitive Environments

Time-sensitive environments support temporary setups for testing or short-term projects. These environments are configured within a normal environment to be used for specific purposes and can be easily discarded once they are no longer required. For detailed instructions on configuring an environment as time-sensitive, refer to the [Availability Rules for Environments](availability-rules-for-environments) documentation.

The next step is learning how to customize and adjust resources within these environments through [overriding](overrides), allowing for tailored configurations and flexibility in deployment.

***

# Releases

A release in Facets is a streamlined process for deploying changes to a cloud environment.  Any modifications in a running environment, such as adding a new Redis instance or deploying an application build, happens through a Release.

<Image align="center" className="border" width="650px" border={true} src="https://files.readme.io/9a0e2801f05cfd4f56e2f6b784d2fbe47048ba2709e78ddee7cfa34ede35079a-image.png" />

## Three-Way Comparison

* Releases are executed using Terraform apply commands, which perform a three-way comparison to determine and deploy the necessary changes. 
* This comparison involves checking the current state of the environment, the state defined in the generated Terraform configuration files from the blueprint, and the desired end state. 
* Based on this comparison, the required changes are deployed to align the environment with the desired configuration.

## Releases Execution

For any environment, Releases can be scheduled to run periodically, with an option to do Manual release anytime you need. Any changes (disk expansion, new build, changed alert definitions) during the period are accumulated and executed in the next scheduled or manual release. To learn how to perform and manage releases in Facets, refer to the [Performing Releases](doc:performing-releases) documentation.

<Image align="center" width="450px" src="https://files.readme.io/c6f187a6392a3bb1c60e6c6953b4f0dd1bbb669e61238e3b4e12c8903a06b9bf-napkin-selection_1.png" />

In addition, Terraform logs are available for power users to view detailed information about the changes made during each release. By using releases in Facets, organizations can have a well-defined and automated process for deploying changes to their cloud environments, which helps reduce the risk of errors and makes it easier to roll back if necessary.

***

# Overrides

Facets Overrides allow developers to customize infrastructure configurations on a per-environment basis (e.g., development, staging, production) without altering the core Blueprint and its configurations. 

This method provides flexibility by enabling environment-specific adjustments while maintaining Blueprint integrity, ensuring consistency, and reducing code duplication. Learn how to customise configurations for specific environments in the [Overriding Resources in an Environment](doc:overriding-resources-in-a-cluster) documentation.

## Types of Overrides

* **Resource Configurations:** Modify resource settings, such as instance types, database sizes, or scaling parameters, to allocate resources based on the specific needs of each environment (e.g., 2 cores for production and 0.5 cores for testing).

<Image align="center" className="border" width="450px" border={true} src="https://files.readme.io/b6f0cea7d8624565d213646980017bcce194099a815a612dc150412777cef41b-image.png" />

* **Secrets and Sensitive Data:** Manage secrets (e.g., passwords, access tokens) securely for each environment without hardcoding them in the Blueprint.
* **Variables:** Define environment-specific variables, such as API keys, URLs, or other configuration values that differ across environments.

<Image align="center" className="border" width="450px" border={true} src="https://files.readme.io/c6646ca88b8c94eb1ddf99d10d7e80e32dd90c362241afaf99729dc6e368651d-image.png" />

In summary, Facets Overrides provide a flexible way to customize configurations for different environments while maintaining Blueprint integrity.
