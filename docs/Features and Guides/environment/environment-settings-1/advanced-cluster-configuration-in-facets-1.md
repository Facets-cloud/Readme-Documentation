---
title: Advanced Cluster Configuration in Facets
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
Advanced Environment Configuration provides granular control over your cluster's behavior, performance, and security settings. These configurations can be customized based on your specific cloud provider and requirements.

## Key Features

### Common Settings (All Clouds)

- Node pool management (default and dedicated)
- Configurable instance types and disk volumes
- Scalability controls with maximum node limits
- Secure boot options for enhanced security
- Advanced node lifecycle management

### Cloud-Specific Features

- **GCP**
  - Private node configuration
  - Workload logging integration
  - Node auto-provisioning
  - Legacy node management support

- **AWS**
  - CIDR whitelist configuration
  - Custom instance type selection
  - Fallback node configuration

- **Azure**
  - Disk type selection (managed vs ephemeral)
  - Custom instance type configuration
  - Multi-AZ deployment options

## Common Use Cases

### High-Performance Computing

Configure dedicated node pools with specific instance types for compute-intensive workloads.

### Cost Optimization

Implement spot/preemptible instances with fallback options for non-critical workloads.

### Enhanced Security

Enable secure boot and private nodes for regulated or security-sensitive environments.

## How to Configure Advanced Settings

1. Access Advanced Settings:
   - Navigate to **Projects** → Select project
   - Go to **Environments** → Choose environment
   - Select **Environment Settings** → **Advanced**

2. Configure Node Management:
   - Toggle **Enable default node pool**
   - Select **Node Plan** (SPOT/On-Demand)
   - Set **Root Volume** size (default: 100GB)
   - Configure **Max Nodes** (default: 200)

3. Set Security Options:
   - Enable/disable **Secure Boot**
   - Configure **Private Nodes** (GCP)
   - Set **CIDR Whitelist** (AWS)

4. Configure Additional Features:
   - Enable **Workload Logging** (GCP)
   - Set up **Node Auto-provisioning**
   - Configure **Multi-AZ Deployment**

5. Save your configuration:
   - Review settings
   - Click **Save Changes**
   - Perform a release to apply changes

Your cluster will now operate with the specified advanced configurations tailored to your requirements.