---
title: Project Settings
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
## Settings specific to a Project

## **1. Accessing Project Settings**

To access the project settings:  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/781f8ebc0f7a44484e4a061eb48dc6aff859cf8e687537f24dd01b027bf61217-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


1. Open the **Projects** tab and select the relevant project.  
2. Click the **Project Settings** tab, which contains the following sections: **General, GitOps, CI/CD,** and **Danger Zone**.

***

## **2. General Settings**

In the **General** section, you can:  

- **Project Name**: View the uneditable project name.  
- **Description**: Edit the project summary.  
- **Allowed Clouds**: View the selected cloud service provider.  

**Note:** After making any changes, click **Save Changes** to apply them.

***

## **3. GitOps Settings**

The **GitOps** section allows you to manage and modify the blueprint through your GitHub repository.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b5a3cbb34fe22c215d960861ee745615d5c2704c29d5f54a8f617bc71ec787d0-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### **Key Options:**

1. **Choose Account**: Displays the GitOps account added during project creation. 
2. **Repository URL**: Displays the URL of the repository added during project setup. 
3. **Branch**: Shows the branch containing the blueprint. 
4. **Relative Path**: Displays the directory path containing the blueprint, relative to the repository URL. 

### **GitOps for Overrides:**

- **Purpose**: Manage environment-specific configuration overrides directly from the Git repository.  
- **Enabling GitOps for Overrides**: Once enabled, overrides are migrated to the Git repository, and you can no longer make changes through the UI.  
- **Restrict UI Changes**: When enabled, Git takes precedence, and any concurrent changes must be made from the repository. 
  - **Important:** This setting is irreversible once activated. Ensure all overrides are properly migrated before enabling it.

**Reminder:** After making any changes, click **Save Changes**.

***

## **4. CI/CD Settings**

The **CI/CD** section allows you to automate your deployments by setting up rules and workflows:  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dab0b5d5838077c5c7a63787289ba9418a8b6fe8ec043ad3cb378daeb54148e8-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### **Deployment Options:**

- **Branch Per Environment**: Map each Git branch to its corresponding environment for efficient testing.  
- **Single Branch Promotion**: Link one branch to an environment and automatically promote changes to other environments.  
- **Advanced**: Create custom Git rules for mapping branches and setting up flexible promotion workflows.

To know more about CI/CD Settings, refer to 

***

## **5. Danger Zone**

The **Danger Zone** section contains options for deleting the project:  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/66359127e5d1de00933df045824de46709e864fe0a3e00aad4db0230e5e5f451-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


1. Click **Delete**. 
2. Type **Confirm** in the pop-up window.  
3. Click **Delete** again to finalize the deletion.