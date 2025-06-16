---
title: Use VPN on Facets
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
# VPN Integration in Facets

Facets integrates with WireGuard VPN to provide secure access to cluster resources. This integration enables teams to safely connect to private resources within their environments while maintaining security best practices.

## Key Features

* Built-in WireGuard VPN server configuration
* User-specific VPN profiles
* Custom IP range definition for VPN access
* Permission-based access control
* One-click VPN profile download
* Simple client setup process

## Common Use Cases

### Development Access

Securely access development environments and internal services while working remotely.

### Database Management

Connect to private database instances for maintenance and troubleshooting.

### Monitoring Tools

Access internal monitoring dashboards and debugging tools securely.

## How to Configure VPN

1. Enable VPN Server:
   * Navigate to **Projects** → Select your project
   * Go to **Environments** → Choose environment
   * Open **Environment Settings** → **Virtual Private Network**
   * Toggle **Enable VPN Server**
   * Enter IP range(s) accessible via VPN
   * Click **Save Changes**

2. Confirm VPN Status:
   * Perform a release to activate VPN server
   * Verify VPN server status in environment

3. Set Up Client Access:
   * Download WireGuard Client from [WireGuard website](https://www.wireguard.com/install/)
   * Click environment menu (⋮) → **Download VPN Profile**
   * Import profile into WireGuard Client
   * Connect to start using Facets VPN

Your team can now securely access cluster resources through the configured VPN connection.
