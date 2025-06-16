---
title: Secrets and Variables
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
## How to add Secrets and Variables in a Project?

1. Open the **Projects** tab and select the desired project. 
2. Select the **Secrets and Variables** tab and click **Add Secrets and Variables.**
3. In the pop-up that appears, select if it is a **Secret** or a **Variable.**
4. Following this, enter the key and the corresponding value.
5. Enable **Auto Inject** to automatically add the key-value pair to all the resources in the Blueprint.\
   Note that if auto inject is enabled for a secret/variable, the key-value pair cannot be edited.
6. To add multiple entries, click **Add New Entry.**
7. Once you are done adding the Secrets and Variables, click **Save.**

You have successfully added Secrets and Variables to your project.

## How to Override Secrets and Variables for an Environment?

1. Open the **Projects** tab and select your desired project. 
2. Select the **Secrets and Variables** tab.\
   You will find a list of all the secrets and variables associated with this project.
3. Click **Overrides.**
4. In the window that appears, select the environment where the values need to be updated.
5. Find the entry you wish to modify and click on the **edit** icon beside it.
6. Update the **Environment Value** and confirm your changes by clicking on the **tick** icon.

You have successfully overridden the value of Secrets and Variables for the environment.
