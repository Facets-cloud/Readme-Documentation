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
In Facets, Version Control Systems (VCS) are essential for managing Projects, Blueprints, and environment-specific configurations. Facets integrates with popular **VCS providers like GitHub, GitLab, and Bitbucket**, enabling developers to track infrastructure configurations, manage changes, and automate deployment.

By leveraging a VCS, Facets ensures that projects and resource definitions are consistently stored, versioned, and accessible across teams.

## How VCS is used in Facets

In Facets, the VCS stores all Project-related files, including Blueprints, resource definitions, and environment-specific overrides. This setup ensures that configurations are centrally managed and easily updated.

1. **Project and Blueprint Management**
   * **Blueprint Storage:** Each Blueprint—essentially the design of the infrastructure and its configurations—is stored in the VCS. This blueprint includes resources defined as JSON files, specifying the desired infrastructure setup.
   * **Centralised Versioning:** Storing the blueprint in the VCS enables version control, allowing developers to track changes, collaborate on updates, and roll back to previous configurations if necessary.
2. **Resource Definitions and Overrides**
   * **Resource JSON Files:** The resource JSON files define various infrastructure components, such as databases, compute instances, or networking resources.
   * **Overrides for Environment-Specific Customization:** To customize a blueprint for specific environments (e.g., development, staging, production), Facets supports overrides, stored as separate JSON files in the VCS. These overrides allow environment-specific adjustments without modifying the base blueprint, maintaining consistency and flexibility.
3. **Deployment Synchronization**
   * **Automated Deployments:** Facets integrates with the VCS to monitor changes to the blueprints and resources. When a change is committed to the repository, Facets can trigger an automated deployment process, ensuring that the live environment reflects the latest configuration in the VCS.
   * **Controlled Updates:** Facets only deploys changes once they are committed and merged in the VCS, promoting a CI/CD (Continuous Integration/Continuous Deployment) workflow. This setup supports collaborative, controlled updates and reduces the risk of misconfigurations in production environments.

## Working with VCS in Facets

1. **Connecting Repositories**: To link a project in Facets with a VCS repository, users provide access permissions for specific branches. Facets requires minimal permissions, enough to read, track, and manage the project files stored in the repository.
2. **Blueprint Tracking and Change Management:** Any modifications to blueprint JSON files or environment overrides are tracked in the VCS. This allows for:
   * **Audit Trails:** Tracking who made changes, what was changed, and when, providing a history that helps with troubleshooting and compliance.
   * **Collaboration and Review:** Developers can use pull requests or code reviews within the VCS to ensure configuration updates meet quality standards before deployment
3. **Resource Synchronisation:** Facets maintains synchronization with the repository, so that any update to the blueprints or overrides is reflected across environments. This feature simplifies management and supports consistent configurations across cloud providers.

<Embed url="https://app.storylane.io/demo/2l8yptqxiro5" href="https://app.storylane.io/demo/2l8yptqxiro5" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F2l8yptqxiro5%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252F2l8yptqxiro5%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_8ff9cbed-aefb-4bd7-8cb0-0c52eeb6d058%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Key Considerations for Developers

* **Branch Management:** Facets supports the use of branches, enabling separate configurations for development, staging, or production. Use protected branches and structured merge strategies to ensure only validated changes are deployed.
* **Environment Overrides:** By storing environment-specific overrides as JSON files in the VCS, Facets allows users to create custom configurations for each environment without altering the main blueprint, providing flexibility and control.
* **Minimal Permissions:** For security, Facets only requires read access to the repository where blueprints and resource definitions are stored. Restricting access to these minimal permissions limits exposure to sensitive information.