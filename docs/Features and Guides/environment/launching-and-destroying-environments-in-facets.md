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

* Multiple cloud providers with account-level isolation
* Custom VPC configurations for network security
* Region and availability zone selection for global deployment
* Flexible CIDR range definition for network planning

## Kubernetes Configuration

Tailor your Kubernetes cluster to your workload requirements with options for:

* Cost optimization through Spot instances for development and testing
* High availability with On-Demand instances for production workloads
* Customizable node configurations for different workload types
* Auto-scaling capabilities with configurable node limits

## Resource Management

During launch, you have complete control over your environment's resources:

* Enable or disable specific resources based on your needs
* Configure resource-specific parameters for optimal performance
* Set up environment variables and secrets for secure configuration
* Review and adjust resource dependencies before deployment

## How to Launch an Environment in Facets?

1. From the Projects menu, select your project and navigate to the Environment tab
2. Click Launch on your chosen environment to start the Launch Wizard
3. Configure your environment through the wizard's steps:
   * Connect your cloud provider and select account
   * Set up networking with VPC configuration
   * Configure Kubernetes cluster settings
   * Review and set secrets & variables, you can override/fullfill them based on your setup.
   * Enable required resources

***Note:** The launch wizard flow and steps can be customisable if needed. [Read more here](https://readme.facets.cloud/docs/modular-launch-wizard).*

### Interactive Demo of 'How to Launch an environment on Facets'

<Embed url="https://app.storylane.io/demo/ds4gji0c7rai" title="Environments | Feb 17 2:33 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_4632974e-54c6-46b2-892b-f855b23ef7d1/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/ds4gji0c7rai" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fds4gji0c7rai%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fds4gji0c7rai%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_4632974e-54c6-46b2-892b-f855b23ef7d1%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

Your environment will begin provisioning once launched, and you can monitor its progress through the Control Plane.

# Destroying Environments in Facets

When you destroy an environment in Facets, you remove all provisioned infrastructure while preserving the environment configuration in the Control Plane. This allows you to later relaunch the environment with the same configuration if needed.

## What Happens During Destruction

When you destroy an environment:

* The Kubernetes cluster is terminated
* All dependent infrastructure resources are removed
* Environment configuration remains preserved in the Control Plane
* Environment state changes to STOPPED
* Billing for cloud resources stops

## Environment States and Destruction

Environments can only be destroyed when they are in a stable state:

* Must be in RUNNING state for destruction
* Cannot destroy environments that are LAUNCHING
* Cannot destroy environments that are SCALED DOWN

The Control Plane will manage the orderly shutdown and removal of all provisioned resources.

## How to Destroy an Environment

Destroying an environment removes all provisioned infrastructure while keeping the configuration in the Control Plane for future use.

1. Open **Projects** tab and choose the Project that contains the environment
2. Select the **Environments** tab and select the Environment you intend to destroy
3. Click the **Destroy** button in the top right corner
4. In the pop-up, enter 'Confirm' and click **Confirm**

**Note:** This action will delete the Kubernetes cluster and its dependent infrastructure resources.

### Interactive Demo on 'How to Destroy an environment on Facets'

<Embed url="https://app.storylane.io/tbx2cbihq7ii" title="Overview | Feb 17 2:51 PM" favicon="https://assets.storylane.io/apps/prod/97/icons/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_07d0ac33-3a5a-4434-a300-f995887bb1db/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/tbx2cbihq7ii" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ftbx2cbihq7ii%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Ftbx2cbihq7ii%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_07d0ac33-3a5a-4434-a300-f995887bb1db%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## How to Delete an Environment

To permanently remove an environment from the Control Plane:

1. Open **Projects** tab and choose the Project that contains the environment
2. Select the **Environments** tab and select the Environment you intend to delete
3. Select the **Environment Settings** tab and click on **Danger Zone**
4. Click Delete Environment
5. In the pop-up, enter 'Confirm' and click **Confirm**

**Important:** An environment can only be deleted after it has been destroyed.

### Interactive Demo on 'How to Delete an environment on Facets'

<Embed url="https://app.storylane.io/demos/nrqmtsxjcxtg" title="Overview | Feb 17 3:04 PM" favicon="https://assets.storylane.io/apps/prod/97/icons/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_1b304c3a-24c8-4836-a232-86d7708f1dda/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demos/nrqmtsxjcxtg" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fnrqmtsxjcxtg%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemos%252Fnrqmtsxjcxtg%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_1b304c3a-24c8-4836-a232-86d7708f1dda%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
