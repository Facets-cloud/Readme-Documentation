---
title: Environment Settings
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
Below is the end-user documentation for the Environment Settings sections **other than Advanced**. This guide is intended to help you configure and manage your environment through an easy-to-understand interface. For information on Advanced settings, please refer to the separate Advanced Settings page.

***

# Environment Settings Overview

The Environment Settings section in Facets allows you to manage key aspects of your cloud environment. This includes setting basic details, managing time-sensitive operations, scheduling releases, configuring your infrastructure as code (IaC), setting up VPN access, and handling critical configurations in the Danger Zone.

Use the left-hand menu on the Environment Settings page to navigate between these sections:

* **General**
* **Time Sensitive**
* **Releases**
* **Infrastructure as Code (IaC)**
* **Virtual Private Network (VPN)**
* [Advanced](https://readme.facets.cloud/docs/advanced-settings-in-facets)
* **Danger Zone**

***

# General Settings

In the **General** section, you can update the basic details of your environment.

### Environment Details

* **Edit Environment Name:** Update the name of your environment.\
  **Note:** The environment name can only be changed if the environment has not yet been launched.
* **Release Stream:** Specify or update the release stream associated with this environment.

### Instance Type

* **Modify Instance Type:** Choose a different instance type or adjust cloud-specific settings.\
  **Note:** Changing the instance type while your environment is running will trigger a release to apply the update.

### Saving Changes

* **Save Changes Button:** After making modifications, click this button to save your settings.\
  **Tip:** If your environment is running, saving changes may trigger a release process.

***

# Time Sensitive Settings

The **Time Sensitive** section lets you manage the availability schedule of your environment.

### Availability Schedule

* **Configure Schedule:** Set up daily or weekly schedules by specifying start and stop times.\
  **Best Practice:** Ensure that the stop time is set later than the start time to avoid configuration errors.
* **Manage Updates:** Modify the schedule anytime to adjust the periods when your environment is available.

<br />

### Short-lived Environment Configuration

The **Short-lived Environment** section lets you configure automated teardown behavior for environments that are manually launched or scaled up. This is especially useful for managing **ephemeral workloads** such as testing, QA, or short-term experiments.

#### Configuration Options

* **Teardown Action**\*: Choose the action to execute automatically after a manual operation:
  * **Scale Down**: Reduce resource usage by scaling down the environment.
  * **Destroy**: Completely tear down the environment.

* **Trigger Delay**\*: Set the time delay before the teardown action executes. This can be defined in **hours**, **minutes**, or **seconds**.

#### Use Cases

* Prevent resource waste from forgotten environments
* Automate cleanup for ad-hoc or temporary environments
* Improve cost control and operational hygiene

#### How to Configure

1. Navigate to the **Time Sensitive Settings** in the environment settings panel.
2. Scroll to **Short-lived Environment**.
3. Select the **Teardown Action** (`Scale Down` or `Destroy`).
4. Set the **Trigger Delay**.
5. Click **Save Changes** to apply the configuration.

***

# Releases

The **Releases** section allows you to manage when updates and changes are applied to your environment.

### Release Schedule

* **Manage Releases:** Create, update, or delete release schedules according to your deployment needs.
* **Redirect for Status:** Changing the release schedule may redirect you to the Releases page where you can verify the status of your scheduled releases.

### Cluster Settings for Releases

* **Update Cluster Settings:** Configure settings that affect cluster releases.\
  **Note:** Changes here may also trigger a release if your environment is currently running.

### Navigation Tip

* **Quick Access:** Use the provided navigation links to jump directly to the Releases page and review the status of your releases.

***

# Infrastructure as Code (IaC)

The **Infrastructure as Code (IaC)** section enables you to manage your environment’s infrastructure using code-based configurations.

### Terraform Version

* **Select Terraform Version:** Choose the appropriate Terraform version that is compatible with your setup.\
  **Note:** Ensure compatibility to avoid deployment issues.

### Maintenance Window

* **Configure Maintenance:** Define maintenance windows for updates and regular tasks.\
  **Best Practice:** Schedule maintenance during off-peak hours to minimize impact.

### Saving Changes

* **Save Changes Button:** Click to apply any changes made in the IaC section, which may trigger updates as needed.

***

# Virtual Private Network (VPN)

The **VPN** section lets you control VPN access for your environment.

### Enable/Disable VPN

* **Toggle VPN:** Turn the VPN server on or off based on your security needs.\
  **Important:** Changes here may trigger a selective release if your environment is running.

### Saving Changes

* **Save Changes Button:** After adjusting the VPN settings, save your changes to apply them.

***

# Danger Zone

The **Danger Zone** is where you can access critical settings that have a significant impact on your environment. These settings should be used with caution.

### Critical Settings

* **Access with Caution:** Changes in the Danger Zone can alter key operational aspects of your environment.\
  **Recommendation:** Only modify these settings if you fully understand the impact, or if you have been advised by Facets support.

***

# Notifications and Error Handling

* **Success Messages:** When changes are saved successfully, you will receive a confirmation message.
* **Error Messages:** If there is an issue, detailed error messages will appear to help you resolve any problems.

***

# Best Practices

* **Review Before Saving:** Always double-check your changes before saving, especially if your environment is live.
* **Test in Staging:** Consider testing significant changes in a staging environment before applying them to production.
* **Monitor Releases:** After changes that trigger a release, monitor your release dashboard to ensure that updates are applied correctly.
* **Documentation:** Keep a log of the changes you make. This is particularly useful for troubleshooting or rolling back to previous settings if needed.

***

For additional support or more detailed information, please refer to our help section within the application or contact the Facets support team. This guide is designed to help you navigate and use the non-advanced settings in your environment with confidence.