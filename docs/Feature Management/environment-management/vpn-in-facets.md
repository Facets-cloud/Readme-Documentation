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

## How to Enable VPN Server in Facets?

1. Open **Blueprints**, select the required Blueprint.
2. Select the **Environments** tab and select the desired Environment.
3. Now, select the **Overview** tab.
4. To enable the VPN Profile for this Environment, click on the ellipsis icon from the top right corner and select **Environment Settings.**
5. Toggle **Enable VPN Server** and click **Save Changes.**

   [block:image]{"images":[{"image":["https://files.readme.io/bb750b6-image.png",null,null],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]
6. Now, perform a release to confirm the status of the VPN server in the environment.
7. From the **Overview** tab. Click on the ellipsis icon from the top right corner, and select **Download VPN Profile**

   [block:image]{"images":[{"image":["https://files.readme.io/9112265-image.png",null,null],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]

## How to Set up the WireGuard Client?

1. [Download](https://www.wireguard.com/install/) and install WireGuard Client on your machine.
2. Open WireGuard VPN and import the downloaded **VPN Profile** and start using Facets VPN.

You have successfully configured the VPN in your Facets Environment.