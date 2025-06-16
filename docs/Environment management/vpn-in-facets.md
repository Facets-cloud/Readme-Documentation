---
title: VPN in Facets
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
Facets now integrates WireGuard VPN, simplifying secure access to cluster resources. Admins grant users the 'VPN Connect' permission, allowing them to configure VPN connections using WireGuard CLI. This provides a secure and efficient workflow for accessing and interacting with private resources within clusters.

**Note:** You require `VPN_CONNECT` permission to download the VPN profile and connect to Kubernetes using the VPN.

## Enabling VPN Server in Facets

1. Navigate to **Blueprint > List,** select the required Blueprint, and select the desired Environment.  
   You will be redirected to the **Environments > Overview** page.
2. To enable the VPN Profile for this Environment, click on the ellipsis icon from the top right corner and select **Environment Settings.**
3. Toggle **Enable VPN Server** and click **Save Changes.**
4. Now, perform a release to confirm the status of the VPN server in the environment.
5. Navigate to **Environments > Overview.** Click on the ellipsis icon from the top right corner, and select **Download VPN Profile**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b933cb0-VPN.gif",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


## Setting up the WireGuard Client

1. [Download](https://www.wireguard.com/install/) and install WireGuard Client on your machine.
2. Open WireGuard VPN and import the downloaded **VPN Profile** and start using Facets VPN.

You have successfully configured the VPN in your Facets Environment.