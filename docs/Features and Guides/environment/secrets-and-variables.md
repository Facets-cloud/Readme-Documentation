---
title: Secrets and Variables
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
Facets provides a secure and flexible way to manage secrets and variables by allowing them to be defined and dynamically referenced within resources. This enables resources to securely access and utilize sensitive information, such as passwords and configurations, across different environments.

## How to add Secrets and Variables in a Project?

1. Open the **Projects** tab and select the desired project. 
2. Select the **Secrets and Variables** tab and click **Define New**
3. In the pop-up that appears, select if it is a **Secret **or a** Variable.**
   1. If you choose to add a **Secret,** mention the **Name.** It is advised that the values are set at the Environment Level.
   2. If you choose to add a **Variable,** enter the **Name** and the **Default Value.**
4. Select the **Auto Inject** checkbox to automatically add the key-value pair to all the resources in the Blueprint.
5. To add multiple entries, click **Add More.**
6. Once you are done adding the Secrets and Variables, click **Save.**

You have successfully added Secrets and Variables to your project.

## How to Override Secrets and Variables for an Environment?

1. Open the **Projects** tab and select your desired project. 
2. Select the **Secrets and Variables** tab.  
   You will find a list of all the secrets and variables associated with this project.
3. Click **Edit Env. Variables.**
4. In the window that appears, select the environment where the values need to be updated.
5. Find the entry you wish to modify and click on the **edit** icon beside it.
6. Update the **Environment Value** and confirm your changes by clicking on the **tick** icon.
7. Click **Save Changes** to apply the changes.

You have successfully overridden the value of Secrets and Variables for the environment.