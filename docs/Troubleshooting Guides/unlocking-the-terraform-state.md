---
title: Unlocking the Terraform State
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
The purpose of this guide is to assist you in unlocking the Terraform state in instances where a previous release did not complete successfully, resulting in a locked state.

## When do you unlock the Terraform State?

The Terraform state should be unlocked when Releases fail with the following error message:

* error: error acquiring state lock

## How to unlock the Terraform State?

1. Click **View details** on the error message. This will reveal additional details about the failed release.
2. Look for the **lock info** in the expanded details.
3. Copy the **id** listed under the **lock info** for future use.
4. Now, go back to the **Releases** page, click on the ellipsis icon, and select **Unlock State.**
5. In the Unlock State pop-up, paste the previously copied **id** into the **Terraform Lock id** field, then click **Unlock.**
6. Trigger a new release.

You have now successfully unlocked the Terraform lock state.
