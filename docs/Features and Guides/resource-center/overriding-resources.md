---
title: Overriding Resources
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
The Overrides tab within the Resource Center enables one to modify resource configurations at environment level. This capability is essential when adjustments are required that deviate from the predefined Blueprint, allowing for environment-specific customizations without altering the original Blueprint.

## Use Cases

- **Environment-Specific Configurations**: Tailor resources to meet the unique requirements of different environments (e.g., development, staging, production) without modifying the global Blueprint.

- **Hotfixes and Patches**: Implement immediate changes or fixes to resources in a live environment, ensuring minimal disruption and rapid response to issues.

- **Testing and Experimentation**: Experiment with new configurations or features in a controlled environment by overriding specific resource settings, facilitating testing without impacting the entire system.

***

## Functionality

The Overrides tab offers the following features:

1. **Form and JSON Modes for Resource Configuration**: Modify resource configurations using a user-friendly form interface or directly edit the JSON configuration for precise control.

2. **Blueprint vs. Override Comparison in JSON Mode**: Visually compare the current Blueprint configuration with the overridden settings to understand the differences and ensure accuracy.

3. **Environment Variables Management**: View and modify environment-specific variables, enabling dynamic value modifications as per the environment's needs.

4. **Override Version History**: Access a history of overrides with options to compare versions, view specific changes, and roll back to previous configurations if necessary.

***

## Accessing the Overrides Tab

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fmboqptugzcvq&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fmboqptugzcvq&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_66c5853b-0e42-4926-a420-c6d15af3e8c0%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"431\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/mboqptugzcvq",
  "title": "Project | Feb 19 1:51 PM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_66c5853b-0e42-4926-a420-c6d15af3e8c0/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/mboqptugzcvq",
  "typeOfEmbed": "jsfiddle"
}
[/block]


## Performing an Override

1. **Choose the Edit Mode**: Select either the Form mode for a guided interface or the JSON mode for direct configuration editing.

2. **Make Necessary Changes**: Adjust the configuration settings as required for your specific use case.

3. **Review Changes**: In JSON mode, utilize the Blueprint vs. Override comparison feature to review differences.

4. **Save and Apply**: Save the changes to apply the new configuration to the resource within the environment.

***

## Managing Environment Variables

Environment variables can be critical for environment-specific configurations. To manage them:

1. **Access Environment Variables**: Within the Overrides tab, navigate to the "Environment Variables" section.

2. **View Current Variables**: Review the list of existing environment-specific variables.

3. **Modify Variables**: Edit existing variables' values as per the environment's requirements.

4. **Save Changes**: Ensure all modifications are saved to update the environment's configuration.

***

## Version History and Rollback

The Overrides feature maintains a version history of all changes:

1. **View Version History**: Within the Overrides tab, access the "History" section to see a chronological list of changes.

2. **Compare Versions**: Select two versions to compare their configurations side by side, highlighting any differences.

3. **View Specific Changes**: Click on a specific version to view the detailed changes made in that iteration.

4. **Rollback to a Previous Version**: If necessary, select a prior version and initiate a rollback to revert the resource to that configuration.

***

## Troubleshooting

- **Override changes not live**: Ensure that the changes are saved and that there are no validation errors in the configuration. Verify that a release has been performed for this resource once the changes are made.

- **Configuration Conflicts**: Use the Blueprint vs. Override comparison feature to identify and resolve discrepancies between the global Blueprint and the overridden configuration.

- **Rollback Issues**: If a rollback does not reflect the expected state, check the version history for any intermediate changes that might affect the configuration. Ensure that the resource is released after a rollback.