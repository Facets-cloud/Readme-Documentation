---
title: Kubernetes Upgrade to v1.21
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
> ⚠️ This document is applicable only if you are using AWS infrastructure.

Facets provides you the capability to perform an upgrade on your Kubernetes Components to version 1.21 directly from your Control Plane. 

You can read more about what is included in this version in the [Kubernetes 1.21 release notes](https://kubernetes.io/blog/2021/04/08/kubernetes-1-21-release-announcement/). 

## Step by Step Instructions

1. Update the EKS version in your blueprint definition.  
   Sample code:
   ```json stack.json
    "componentVersions": {
       "KUBERNETES": "1.21"
      }			
   ```

> 📘 
> 
> Environments created **after** this change in your blueprint definition will have v1.21 by default.

2. Login to your **Control Plane**.
3. Select the **Environment** in your defined **Blueprint** where you want to perform this upgrade.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0add705-2f75e47-select_env.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]

4. In the **Environment Overview** page, you should be able to see a **Component Upgrade** section that looks like this: 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71ffdf3-k8s_upgrade.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]

5. Click on the **Upgrade** button, and you should see a popup window that asks for confirmation to proceed with the upgrade. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/30c36e9-k8s_upgrade_2.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]

6. To ensure that upgrade is executed, you need to perform a **Release** with `Refresh` flag enabled in this environment. 
7. For more information on how to perform a **Release** with `Refresh` flag enabled, refer this API Reference document to [Trigger a Release](https://readme.facets.cloud/reference/trigger-a-release).  
   Alternatively, you can do it from your **Control Plane** in the **Releases** page with the **Force refresh** tickbox checked.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a861c4-force_refresh.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]