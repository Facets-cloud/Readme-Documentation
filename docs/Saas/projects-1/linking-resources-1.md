---
title: Linking/Reference Resources
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
This guide provides step-by-step instructions for linking or referencing resources in the Blueprint within Facets.cloud. Establishing connections between resources ensures that your project architecture is cohesive and functional.

### Why Link Resources?

1. Define dependencies and relationships between resources.
2. Enable seamless integration and communication within the architecture.
3. Simplify management by dynamically referencing other resources and their attributes.

## Steps to Link or Reference Resources

1. Navigate to the Blueprint Tab: Open the Projects section and select the project you want to work on.
2. Click on the Blueprint tab to access the Resources graph or table view.

### Linking Resources from a Service:

1. In Graph Mode, click on the service module you want to link.
2. Select Connect with Other Resources from the dropdown menu.
3. A modal will open where you can: 
   1. Select the resource to link.
   2. Choose the variables and set their dollar reference values in the value field.  
      Start typing with ${ in the input field to see dropdown suggestions for available references.
   3. Confirm your selections and save the changes.

### Linking Resources for Ingress:

To link a service in ingress rules, use the form in the ingress configuration.

1. Access the ingress module in Graph View or Table View: Click on the ingress module to open the Configuration Section.
2. Navigate to the Ingress Rules section of the form.
3. Add rules by specifying the name of the service you want to link.
4. Save the changes to apply the updated ingress rules.

### Linking Any Other Resources:

For other resource types, follow these steps:

1. Click on the module in either Graph View or Table View to open the Configuration Section.
2. Switch to JSON Mode.
3. Use the Resource Reference section to select the resource you want to reference.
4. Once selected, the dollar references will appear dynamically in the Resource Reference section.
5. Add these dollar references to the appropriate key-value pairs in the JSON configuration.
6. Edit the JSON as needed, ensuring the variable keys are properly defined with the dollar references as their values.
7. Save the configuration to finalize the linkage.