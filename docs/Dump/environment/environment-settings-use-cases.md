---
title: Environment Settings - Use cases
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
## Mirroring Production Setup for UAT

**Scenario:** We need to configure a staging environment for our new application release that mirrors our production setup in GCP. Additionally, this environment will serve for load testing and must be able to automatically scale up and scale down based on a schedule. How do I configure these settings?

**Solution:** To configure the staging environment in the Facets Control Plane, follow these steps:

Assuming you already have an environment with GCP as the cloud provider, select the environment. 

Navigate to the **Environment Settings** page, and configure the following:

- **Time Sensitive:** Set this to **Time Sensitive** and select **Scale up/Scale down.** Refer to the [Availability Rules for Environments](https://readme.facets.cloud/docs/availability-rules-for-environments) documentation to know more about this feature.
- **Node Plan:** Select **ON_DEMAND.** This ensures high availability (HA) and fault tolerance, which are essential for effective load testing.
- **Enable Secure Boot for facets default node pool:** Toggle Enable Secure Boot on. 
- **Enable Node Auto-Provisioning:** Toggle node auto-provisioning on. This feature allows for automatic creation of node pools based on tolerations and labels, eliminating the need for manual node pool creation.
- For all other settings, use their default values to ensure a consistent and standard configuration.

By setting these values, you will establish a staging environment that mirrors your production setup, optimized for load testing, and easily managed for creation and destruction.

***

## Creating Secure Development Environment

**Scenario:** How can I configure a secure development environment using a VPN for developers to test applications, ensure my staging environment reflects the latest configurations and improvements, and automatically launch and destroy clusters based on a schedule?

**Solution:** To configure the staging environment in the Facets Control Plane, follow these steps:

Assuming you already have an environment, select the environment and navigate to the **Environment Settings** page, and configure the following:

- **Time Sensitive:**  Set this to **Time Sensitive** and select **Scale up/Scale down.** Refer to the [Availability Rules for Environments](https://readme.facets.cloud/docs/availability-rules-for-environments) documentation to know more about this.
- **Node Plan:** Select **SPOT.** This is a cost-saving, interruptible instance option.
- **IaC Configuration:** Select the **Releases** tab. 
  1. Under IaC Versions, select **stage** for **Stream.** 
  2. Ensure the latest **Major** and **Minor versions** are used to keep your staging environment up-to-date.
- **Virtual Private Network: ** Enable VPN Server. Refer to the [VPN in Facets](https://readme.facets.cloud/docs/vpn-in-facets) documentation to know how to configure the VPN. 
- For all other settings, use their default values to ensure a consistent and standard configuration.

By following these steps, you can create a secure development environment for your developers to test applications, keep your staging environment updated, and efficiently manage clusters with automated scheduling.