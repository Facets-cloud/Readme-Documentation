---
title: Editing Resources
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
This guide provides a clear, step-by-step process for editing a resource within the Blueprint section of Facets.cloud.

## Steps to Edit a Resource

1. Access the Project: Navigate to the Projects section and select the project you want to modify.
2. Open the Blueprint Tab: Click on the Blueprint tab to view the Resources graph.
3. Locate the Resource: Identify the resource you wish to edit.
   1. In Graph Mode: Click on the resource in the graph and select Configure from the dropdown menu.
   2. In Table Mode: Locate the resource name in the table view and open the Configurations tab to access the resource’s JSON settings.
4. Edit the Configuration: On the configuration page, update the required settings for the resource. Resources offer two modes for editing configurations:
   1. Form Mode: A user-friendly, structured form interface allows for easy field editing and provides direct referencing of other resources using dropdowns or pre-populated options. For instance, when configuring ingress rules, you can select a valid service name directly from the dropdown to reference a resource seamlessly.\
      The form includes built-in validations to ensure all configurations are correct and error-free, simplifying the process for standard use cases.
   2. JSON Mode:\
      This mode provides direct access to the resource’s configuration JSON, ideal for making advanced edits.\
      Switch to JSON mode if you need to write advanced configurations based on the resource’s schema. This mode allows you to use relevant advanced variable keys as defined by the schema.\
      The Resource Referencing section is available exclusively in JSON mode. It dynamically displays references to other resources and their attributes, providing you with copy-ready details for seamless integration.
5. Save the Changes: After making the necessary modifications, click Save Changes to update the resource’s configuration.

You have successfully edited the resource within the project’s Blueprint. The changes will be applied to the resource, ensuring it aligns with your updated project requirements.
