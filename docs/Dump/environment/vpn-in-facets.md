---
title: VPN in Facets
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
Facets now integrates WireGuard VPN, simplifying secure access to cluster resources. Admins grant users the 'VPN Connect' permission, allowing them to configure VPN connections using WireGuard CLI. This provides a secure and efficient workflow for accessing and interacting with private resources within clusters.

## How to Enable VPN Server in Facets?

1. Open **Projects** tab and choose the Project that contains the environment.
2. Select the **Environments** tab and select the desired Environment.
3. Now, select the **Environment Settings** tab and select the **Virtual Private Network** tab.
4. Toggle **Enable VPN Server** and mention the **IP range(s) accessible via VPN.**
5. Click **Save Changes.**
6. Now, perform a release to confirm the status of the VPN server in the environment.
7. In the selected Environment, click on the ellipsis icon from the top right corner, and select **Download VPN Profile**

## How to Set up the WireGuard Client?

1. [Download](https://www.wireguard.com/install/) and install WireGuard Client on your machine.
2. Open WireGuard VPN and import the downloaded **VPN Profile** and start using Facets VPN.

You have successfully configured the VPN in your Facets Environment.
