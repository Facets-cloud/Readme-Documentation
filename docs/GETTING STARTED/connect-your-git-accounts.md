---
title: Connect your VCS Accounts
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
In Facets, Version Control Systems (VCS) are essential for managing Projects, Blueprints, and environment-specific configurations. Facets integrates with popular VCS providers like GitHub, GitLab, and Bitbucket, enabling developers to track infrastructure configurations, manage changes, and automate deployment. By leveraging a VCS, Facets ensures that projects and resource definitions are consistently stored, versioned, and accessible across teams.

## How VCS is used in Facets

In Facets, the VCS stores all Project-related files, including Blueprints, resource definitions, and environment-specific overrides. This setup ensures that configurations are centrally managed and easily updated.

1. **Project and Blueprint Management**
   - Blueprint Storage: Each Blueprint—essentially the design of the infrastructure and its configurations—is stored in the VCS. This blueprint includes resources defined as JSON files, specifying the desired infrastructure setup.
   - Centralized Versioning: Storing the blueprint in the VCS enables version control, allowing developers to track changes, collaborate on updates, and roll back to previous configurations if necessary.
2. **Resource Definitions and Overrides**
   - Resource JSON Files: The resource JSON files define various infrastructure components, such as databases, compute instances, or networking resources.
   - Overrides for Environment-Specific Customization: To customize a blueprint for specific environments (e.g., development, staging, production), Facets supports overrides, stored as separate JSON files in the VCS. These overrides allow environment-specific adjustments without modifying the base blueprint, maintaining consistency and flexibility.
3. **Deployment Synchronization**
   - Automated Deployments: Facets integrates with the VCS to monitor changes to the blueprints and resources. When a change is committed to the repository, Facets can trigger an automated deployment process, ensuring that the live environment reflects the latest configuration in the VCS.
   - Controlled Updates: Facets only deploys changes once they are committed and merged in the VCS, promoting a CI/CD (Continuous Integration/Continuous Deployment) workflow. This setup supports collaborative, controlled updates and reduces the risk of misconfigurations in production environments.

## Working with VCS in Facets

1. **Connecting Repositories**: To link a project in Facets with a VCS repository, users provide access permissions for specific branches. Facets requires minimal permissions, enough to read, track, and manage the project files stored in the repository.
2. **Blueprint Tracking and Change Management: **Any modifications to blueprint JSON files or environment overrides are tracked in the VCS. This allows for:
   - Audit Trails: Tracking who made changes, what was changed, and when, providing a history that helps with troubleshooting and compliance.
   - Collaboration and Review: Developers can use pull requests or code reviews within the VCS to ensure configuration updates meet quality standards before deployment
3. **Resource Synchronisation: **Facets maintains synchronization with the repository, so that any update to the blueprints or overrides is reflected across environments. This feature simplifies management and supports consistent configurations across cloud providers.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2F2l8yptqxiro5&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2F2l8yptqxiro5&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_8ff9cbed-aefb-4bd7-8cb0-0c52eeb6d058%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/2l8yptqxiro5",
  "title": "Account Management | Feb 5 12:29 PM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_8ff9cbed-aefb-4bd7-8cb0-0c52eeb6d058/preview.gif",
  "provider": "https://www.storylane.io",
  "href": "https://app.storylane.io/demo/2l8yptqxiro5",
  "typeOfEmbed": "jsfiddle"
}
[/block]


## Key Considerations for Developers

- **Branch Management: **Facets supports the use of branches, enabling separate configurations for development, staging, or production. Use protected branches and structured merge strategies to ensure only validated changes are deployed.
- **Environment Overrides:** By storing environment-specific overrides as JSON files in the VCS, Facets allows users to create custom configurations for each environment without altering the main blueprint, providing flexibility and control.
- **Minimal Permissions:** For security, Facets only requires read access to the repository where blueprints and resource definitions are stored. Restricting access to these minimal permissions limits exposure to sensitive information.