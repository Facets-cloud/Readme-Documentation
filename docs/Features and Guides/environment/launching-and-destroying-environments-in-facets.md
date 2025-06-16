---
title: Launching and Destroying Environments
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
# Launching Environments in Facets

Launching an environment in Facets initiates the creation of a cluster and provisions the required resources. Through the Environment Launch Wizard, you can configure your infrastructure to match your specific needs, from development environments to production-grade deployments.

## Cloud Infrastructure Setup

The launch process begins with connecting your cloud provider and configuring your network infrastructure. Facets supports:

- Multiple cloud providers with account-level isolation
- Custom VPC configurations for network security
- Region and availability zone selection for global deployment
- Flexible CIDR range definition for network planning

## Kubernetes Configuration

Tailor your Kubernetes cluster to your workload requirements with options for:

- Cost optimization through Spot instances for development and testing
- High availability with On-Demand instances for production workloads
- Customizable node configurations for different workload types
- Auto-scaling capabilities with configurable node limits

## Resource Management

During launch, you have complete control over your environment's resources:

- Enable or disable specific resources based on your needs
- Configure resource-specific parameters for optimal performance
- Set up environment variables and secrets for secure configuration
- Review and adjust resource dependencies before deployment

## How to Launch an Environment in Facets?

1. From the Projects menu, select your project and navigate to the Environment tab
2. Click Launch on your chosen environment to start the Launch Wizard
3. Configure your environment through the wizard's steps:
   - Connect your cloud provider and select account
   - Set up networking with VPC configuration
   - Configure Kubernetes cluster settings
   - Review and set secrets & variables, you can override/fullfill them based on your setup.
   - Enable required resources

_**Note:** The launch wizard flow and steps can be customisable if needed. [Read more here](https://readme.facets.cloud/docs/modular-launch-wizard)._

### Interactive Demo of 'How to Launch an environment on Facets'

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fds4gji0c7rai&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fds4gji0c7rai&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_4632974e-54c6-46b2-892b-f855b23ef7d1%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/ds4gji0c7rai",
  "title": "Environments | Feb 17 2:33 PM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_4632974e-54c6-46b2-892b-f855b23ef7d1/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/ds4gji0c7rai",
  "typeOfEmbed": "jsfiddle"
}
[/block]


Your environment will begin provisioning once launched, and you can monitor its progress through the Control Plane.

# Destroying Environments in Facets

When you destroy an environment in Facets, you remove all provisioned infrastructure while preserving the environment configuration in the Control Plane. This allows you to later relaunch the environment with the same configuration if needed.

## What Happens During Destruction

When you destroy an environment:

- The Kubernetes cluster is terminated
- All dependent infrastructure resources are removed
- Environment configuration remains preserved in the Control Plane
- Environment state changes to STOPPED
- Billing for cloud resources stops

## Environment States and Destruction

Environments can only be destroyed when they are in a stable state:

- Must be in RUNNING state for destruction
- Cannot destroy environments that are LAUNCHING
- Cannot destroy environments that are SCALED DOWN

The Control Plane will manage the orderly shutdown and removal of all provisioned resources.

## How to Destroy an Environment

Destroying an environment removes all provisioned infrastructure while keeping the configuration in the Control Plane for future use.

1. Open **Projects** tab and choose the Project that contains the environment
2. Select the **Environments** tab and select the Environment you intend to destroy
3. Click the **Destroy** button in the top right corner
4. In the pop-up, enter 'Confirm' and click **Confirm**

**Note:** This action will delete the Kubernetes cluster and its dependent infrastructure resources.

### Interactive Demo on 'How to Destroy an environment on Facets'

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Ftbx2cbihq7ii&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Ftbx2cbihq7ii&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_07d0ac33-3a5a-4434-a300-f995887bb1db%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/tbx2cbihq7ii",
  "title": "Overview | Feb 17 2:51 PM",
  "favicon": "https://assets.storylane.io/apps/prod/97/icons/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_07d0ac33-3a5a-4434-a300-f995887bb1db/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/tbx2cbihq7ii",
  "typeOfEmbed": "jsfiddle"
}
[/block]


## How to Delete an Environment

To permanently remove an environment from the Control Plane:

1. Open **Projects** tab and choose the Project that contains the environment
2. Select the **Environments** tab and select the Environment you intend to delete
3. Select the **Environment Settings** tab and click on **Danger Zone**
4. Click Delete Environment
5. In the pop-up, enter 'Confirm' and click **Confirm**

**Important:** An environment can only be deleted after it has been destroyed.

### Interactive Demo on 'How to Delete an environment on Facets'

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fnrqmtsxjcxtg&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemos%2Fnrqmtsxjcxtg&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_1b304c3a-24c8-4836-a232-86d7708f1dda%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demos/nrqmtsxjcxtg",
  "title": "Overview | Feb 17 3:04 PM",
  "favicon": "https://assets.storylane.io/apps/prod/97/icons/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_1b304c3a-24c8-4836-a232-86d7708f1dda/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demos/nrqmtsxjcxtg",
  "typeOfEmbed": "jsfiddle"
}
[/block]