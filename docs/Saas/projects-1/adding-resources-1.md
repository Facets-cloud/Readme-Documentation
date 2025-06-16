---
title: Adding Resources
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
Follow these steps to efficiently add resources to your project's blueprint. The blueprint serves as the architecture for your project, defining all the necessary resources.  [Learn more about resources](docs:facets-core-concepts-verify) 

## Steps to Add a Resource

1. Navigate to the Blueprint Tab: Go to the "Blueprint" tab in your project. The blueprint contains the resources that form the architecture of your project.
2. Select Resources from the Right Panel: Focus on the right panel, which lists all available resources.
3. Choose a Resource: Click on the resource you want to add.
4. Select the Resource Flavor: A popup will appear, allowing you to select a flavor for the resource. These flavors represent different implementations of the resource across various clouds.
   1. Choose the flavor based on your desired cloud provider.
5. Configure the Resource: After selecting a flavor, a modal will open to input the Resource Name. In this modal, you can create multiple instances of the resource at once by clicking on "Add More".
   1. You can also add Add-ons, which provide additional capabilities for the resource. For example, selecting the "Monitoring" add-on enables status monitoring through a Grafana dashboard without requiring extra configurations.
6. Add the Resource: Click the "Add" button to finalize and add the resource to the blueprint.

## Adding Resource Templates

Facets.cloud also allows you to add resource templates, which are predefined implementations of resources for different cloud providers. For example:

Loki templates for AWS S3.

Loki templates for Azure Blob.

### Steps to Add a Resource Template:

1. Select a Template: Click on the desired template to open the "Add Resource" modal.
2. Input Template Name: Provide a name for the template. This name will be prefixed when added to the blueprint.
3. Add the Template:
4. Click the "Add" button to include the template in your blueprint.

## Connecting Resources

Once resources are added to the blueprint, you can connect them to define relationships and dependencies as per your architecture. Connections can be established by referencing resources together. Follow the steps in the "[Linking/Reference Resources](docs:linking-resources-1)" documentation to set up these connections.

### Additional Resources

To explore related tasks, refer to the following documentation:

1. Link Resources
2. Link Resources Using Dollar References
3. Editing a Resource
4. Overriding a Resource

***

## FAQs

1. How do I handle dependencies between resources when adding them?  
   Use the Reference Resources functionality to define dependencies. You can reference other resources dynamically using dollar references in JSON Mode or predefined options in Form Mode.