---
title: Installing Facets CLI
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: facetsctl-commands
      title: facetsctl Commands
    - type: basic
      slug: integrating-with-ci-pipelines
      title: Integrating with CI Pipelines
---
Facets CLI provides a command-line interface to manage and interact with your Facets projects. This guide outlines two methods to install Facets CLI: using **NPM** or **using binaries**.

## Prerequisites

- **Access to Facets environment**: You will need credentials or access permissions for your Facets setup.
- **Network access**: Ensure your system has internet access to download the required files.

***

## Installation Methods

### 1. Install Using NPM

Facets CLI is available as an NPM package. Follow these steps:

1. **Verify Node installation**:  
   Ensure you have Node.js v14.17.0 or later installed. You can check your version using:
   ```bash
   node -v
   ```
2. **Install the package**:
   ```bash
   npm install -g @facets-cloud/facetsctlv3
   ```
3. **Verify installation**:  
   Run the following command to ensure the CLI is installed correctly:
   ```bash
   facetsctl --version
   ```
4. **Login using FacetsCLI**:  
   After installation, log in to the Facets Control Plane. You will be prompted to enter your API token, organization ID, and other required details. 

   Example configuration command:

   ```bash
   $ facetsctl login -u <value> -t <value> -f <value>
   ```
5. **Available Commands**:  
   To see all available commands and their descriptions, use:

   ```bash
   facetsctl help
   ```

   For additional details, refer to the [Facetsctl Commands](https://readme.facets.cloud/docs/facetsctl-commands)

***

### 2. Install Using Binaries

If you prefer to use pre-built binaries, download Facets CLI directly from the provided links.

1. **Download the appropriate binary**:

   #### For Mac Os

   | Type | Architecture | Download link                                                                                                                                   |
   | :--- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------------- |
   | Gzip | 64-bit       | [facetsctl-darwin-x64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-x64.tar.gz)     |
   | XZ   | 64-bit       | [facetsctl-darwin-x64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-x64.tar.xz)     |
   | Gzip | ARM64        | [facetscti-darwin-arm64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-arm64.tar.gz) |
   | XZ   | ARM64        | [facetsctI-darwin-arm64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-arm64.tar.xz) |

   #### For Linux

   | Type | Architecture | Download link                                                                                                                                 |
   | :--- | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
   | Gzip | 64-bit       | [facetsctl-linux-x64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-x64.tar.gz)     |
   | XZ   | 64-bit       | [facetsctI-linux-×64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-x64.tar.xz)     |
   | Gzip | ARM          | [facetsctl-linux-arm.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm.tar.gz)     |
   | XZ   | ARM          | [facetsctl-linux-arm.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm.tar.xz)     |
   | Gzip | ARM64        | [facetsctl-linux-arm64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm64.tar.gz) |
   | XZ   | ARM64        | [facetsctl-linux-arm64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm64.tar.xz) |

   #### For Windows

   | Type | Architecture | Download link                                                                                                                             |
   | :--- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
   | Gzip | 64-bit       | [facetsctl-win32-x64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x64.tar.gz) |
   | XZ   | 64-bit       | [facetsctl-win32-x64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x64.tar.xz) |
   | Gzip | 32-bit       | [facetsctI-win32-x86.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x86.tar.gz) |
   | XZ   | 32-bit       | [facetsctI-win32-x86.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x86.tar.xz) |

2. **Make the binary executable**:  
   After downloading, make the binary executable (for Linux/macOS):
   ```bash
   chmod +x ./facetsctl
   ```

3. **Move the binary to your PATH**:  
   Move the executable file to a directory included in your system’s PATH. For example:
   ```bash
   sudo mv ./facetsctl /usr/local/bin/facetsctl
   ```

4. **Verify installation**:  
   Run the following command to ensure the CLI is installed correctly:
   ```bash
   facetsctl --version
   ```

5. **Log in using Facets CLI**:  
   Log in using Facets CLI with your username and token:
   ```bash
   $ facetsctl login -u <value> -t <value> -f <value>
   ```