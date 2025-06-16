---
title: Custom Terraform Modules
excerpt: >-
  Custom modules in Facets.cloud offer an approach for managing cloud resources,
  utilizing 'intent' and 'flavor' for specific module selection and
  configuration.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Custom Modules in Facets.cloud

Custom modules in Facets.cloud offer streamlined cloud resource management, utilizing 'intent' and 'flavor' for module selection and configuration. This approach enables users without in-depth IaC knowledge to effectively use infrastructure as code by simply providing input specifications, while the module implementer decides the level of abstraction.

Blueprints in Facets.cloud are composed of a collection of JSON objects, where each object specifies a part of the infrastructure:

- **`kind`**: Specifies the general category or type of the module (e.g., `database`, `network`, `compute`).
- **`flavor`**: Provides a more specific variation within the `kind`, allowing for the selection of a particular implementation or version of the module.

### Module Wiring

Based on the specified intent (kind) and flavor, Facets.cloud automatically wires the selected module into your Terraform configuration, ensuring correct module integration.

### Democratization of IaC Usage

This setup democratizes the use of standard IaC codes. It enables users to leverage IaC without understanding its detailed implementation, making the process more accessible. The module implementer defines the JSON inputs required to configure the module, thus setting the abstraction level.

#### Example: Aurora Module Configuration

A user can configure an Aurora instance by simply providing specifications in the JSON format. For instance, to deploy a Postgres Aurora database, the user would specify:

```json
{
  "kind": "postgres",
  "flavor": "aurora",
  "version": "0.2",
  "lifecycle": "ENVIRONMENT",
  "disabled": false,
  "provided": false,
  "depends_on": [],
  "metadata": {
    "name": "test-aurora-postgres",
    "tags": {
      "name": "something"
    }
  },
  "spec": {
    "postgres_version": "12.11",
    "size": {
      "writer": {
        "instance": "db.t3.medium",
        "replica_count": 1
      },
      "reader": {
        "instance": "db.t3.medium",
        "replica_count": 1
      }
    }
  }
}
```

In this example, the user defines the desired Postgres version, instance types, and the number of replicas for the writer and reader nodes, without needing to understand the underlying Terraform code.

## Creating Your First Module in Facets.cloud

### Generate Module Structure

#### Install Copier

First, install Copier, a tool for generating the module's skeleton:

- Use the command: `pip3 install copier`.

#### Create Your Module

Generate your module's structure using Copier:

1. Navigate to the `iac` folder in your Blueprint repository.
2. Run Copier with the command: `copier copy git@github.com:Facets-cloud/module-template.git ./`
   - Note: Integration with a separate IaC repository is coming soon.

![](https://user-images.githubusercontent.com/108784231/234993721-511e0397-8407-43a9-b262-6df22475a283.gif)

### Understanding Generated Files

Copier will create several files, each serving a specific purpose in your module:

- `main.tf`: Your main Terraform configuration file.
- `variables.tf`: Defines variables for `main.tf`.
- `output.tf`: Outlines the outputs from your module.
- `versions.tf`: Manages Terraform and provider version requirements.

### The Role of `module.json`

`module.json` is a key file in your module, specifying critical attributes:

- Intent and Flavor (`kind` and `flavor`).
- Supported Clouds: Lists compatible cloud environments.
- Dependencies: Any dependent modules.
- Lifecycle Phases: The operational phase of your module.
- Input Type: Indicates if your module is Configurable or Instantiable.
- Variables: Identifies variables injected during wiring.

### Wiring the Module

Facets.cloud automates the wiring of variables and providers as defined in `module.json`.

### Outputs and Resource Wiring

- Outputs in `output.tf` facilitate data sharing between modules.
- Facets.cloud uses these outputs for integrating modules in your blueprint.

This guide outlines the steps to create and integrate a custom module in Facets.cloud, simplifying cloud infrastructure management.

## Coming Soon: Advanced Features and UI Management in Facets.cloud

Facets.cloud is continuously evolving, and several exciting features are on the horizon. These upcoming enhancements are designed to streamline the management of Infrastructure as Code (IaC) and provide deeper insights into module usage.

### Integration of IaC Repositories

Shortly, Facets.cloud will offer the ability to integrate separate IaC repositories directly within the platform. This feature will:

- Allow users to manage their Terraform modules in dedicated repositories.
- Simplify the process of adding and updating modules.

### Enhanced Module Generation and Validation

With the integration of IaC repositories, Facets.cloud will enhance the module generation and validation process:

- **Module Generation:** Users will be able to generate modules directly from the UI, leveraging templates and guided workflows.
- **Validation Tools:** Built-in tools for validating the structure and functionality of your modules will ensure they meet best practices and are ready for deployment.

### Usage Statistics for Modules

Understanding how modules are utilized is crucial for continuous improvement and decision-making. The upcoming features will include:

- **Usage Tracking:** Track how often and in what ways your modules are being used within the platform.
- **Insightful Analytics:** Gain valuable insights from usage data to understand popular modules, common configurations, and more.
- **Optimization Opportunities:** Use these analytics to optimize module offerings, addressing the most common user needs and trends.

### Conclusion

The feature to manage and use custom TF modules in Facets.cloud is set to revolutionize the way users interact with and manage IaC. By integrating IaC repositories, enhancing module generation and validation, and providing comprehensive usage statistics, Facets.cloud will offer an even more powerful and user-friendly platform for cloud infrastructure management.