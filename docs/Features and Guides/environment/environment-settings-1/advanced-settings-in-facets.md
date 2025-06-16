---
title: Advanced Settings in Facets
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
The Advanced Settings section provides deep control over your cluster and control plane configurations. These settings can significantly affect performance, scalability, and security. We have organized the options into three groups for clarity:

1. **Common Cluster Settings**  
2. **Cloud-Specific Settings**  

For each field, you will find contextual insights to help you decide when and why you might adjust it.

***

## 1. Common Cluster Settings

These settings impact your cluster regardless of your chosen cloud provider. They control node provisioning, management, and scalability.

### Node Configuration & Lifecycle

- **Node Plan**  
  **Label:** Node Plan  
  **What It Does:** Selects the type of compute instances used in your cluster. You can choose a cost-saving option with interruptible instances or a more stable option that offers continuous availability.  
  **When to Use:**  
  - **Cost-Saving Option:** Best for flexible, non-critical, or batch-processing workloads where interruptions are acceptable.  
  - **Stable Option:** Ideal for production environments or applications requiring consistent availability.  
    **Default:** The system uses the cost-saving option by default.

- **Fallback to On-Demand Nodes**  
  **Label:** Enable Fallback to On-Demand  
  **What It Does:** Automatically switches to a more stable instance type if the cost-saving option is temporarily unavailable.  
  **When to Use:**  
  - Use this setting if you have selected the cost-saving option but want a backup to maintain availability during potential interruptions.  
    **Tip:** Useful in mixed workload environments where uptime is critical without manual intervention.

- **Maximum Nodes**  
  **Label:** Maximum Nodes  
  **What It Does:** Sets an upper limit on the number of nodes in your cluster. This helps manage resource allocation and control costs.  
  **When to Use:**  
  - Adjust this value based on your expected workload—higher limits support scaling but may increase costs.  
    **Default:** 200 nodes.

- **Root Disk Volume**  
  **Label:** Root Disk Volume (GB)  
  **What It Does:** Specifies the primary storage allocated to each node.  
  **When to Use:**  
  - Increase the disk volume if your applications require more local storage for caching, logs, or temporary data.  
  - Use the minimum required for lightweight workloads to control costs.  
    **Default:** 100 GB (Range: 30–500 GB)

### Management & Automation

- **Advanced Node Management**  
  **Label:** Advanced Node Management  
  **What It Does:** Enables features for managing node lifecycle events, such as rolling updates and specialized maintenance routines.  
  **When to Use:**  
  - Enable this if you need granular control over node behavior and are comfortable with more complex configurations.  
    **Default:** Off

- **Node Auto-Provisioning**  
  **Label:** Node Auto-Provisioning  
  **What It Does:** Automatically scales node pools in response to real-time demand by adjusting CPU and memory allocations as needed.  
  **When to Use:**  
  - Particularly useful for dynamic workloads with fluctuating resource needs.  
  - **Note:** This feature is available only on GCP.  
    **Default:** Off

- **Default Node Pool**  
  **Label:** Enable Default Node Pool  
  **What It Does:** Activates the default node pool—a set of nodes managed automatically by the system—to simplify node management.  
  **When to Use:**  
  - Recommended for most users. Disable only if you plan to use custom node pools exclusively.  
    **Default:** On

- **Multi-AZ Default Node Pool**  
  **Label:** Deploy Default Node Pools in Multiple Availability Zones  
  **What It Does:** Distributes your default node pool across multiple availability zones, thereby improving fault tolerance.  
  **When to Use:**  
  - Enable this setting if your environment requires high availability and you want to reduce the risk associated with a single zone failure.  
    **Visibility:** Appears only if the default node pool is enabled.  
    **Default:** Off

***

## 2. Cloud-Specific Settings

These options are tailored to the capabilities and best practices of each cloud provider. Choose the settings that are relevant to your provider.

### AWS

- **CIDR Whitelist**  
  **Label:** Public CIDR Whitelist  
  **What It Does:** Defines the IP ranges allowed to access your cluster on AWS.  
  **When to Use:**  
  - Adjust this to restrict or broaden network access. For production environments, using a more restrictive range is recommended for enhanced security.  
    **Default:** Open to all (0.0.0.0/0).

- **Dedicated Node Pool Instance Type (AWS)**  
  **Label:** Dedicated Node Pool Instance Type (AWS)  
  **What It Does:** Determines the instance type for dedicated node pools on AWS.  
  **When to Use:**  
  - Select an instance type that matches the performance characteristics your workload requires—whether you need compute-optimized, memory-optimized, or balanced performance.  
    **Default:** A balanced instance type is used by default.

### GCP

- **Private Nodes**  
  **Label:** Enable Private Nodes  
  **What It Does:** Controls whether your GKE nodes are assigned private IP addresses (enhancing security) or public IP addresses.  
  **When to Use:**  
  - For production environments where security is paramount, enabling private nodes reduces exposure to the public internet.  
    **Default:** Enabled.

- **Legacy Node Management**  
  **Label:** Enable Legacy Node Management  
  **What It Does:** Provides support for older node management practices.  
  **When to Use:**  
  - Use this setting if transitioning from an older system or if legacy integrations require it.  
    **Default:** Off

- **Dedicated Node Pool Instance Type (GCP)**  
  **Label:** Dedicated Node Pool Instance Type (GCP)  
  **What It Does:** Chooses the instance type for dedicated node pools on GCP.  
  **When to Use:**  
  - Similar to AWS, select an instance type that best meets your performance and cost requirements.  
    **Default:** A standard balanced instance type is used by default.

- **Workload Logging**  
  **Label:** Enable Workload Logging  
  **What It Does:** Enables the collection of application logs to Google Cloud Logging.  
  **When to Use:**  
  - Enable this if you need detailed insights into application performance and troubleshooting information for your GCP applications.  
    **Default:** Off

### Azure

- **Disk Type**  
  **Label:** Azure Disk Type  
  **What It Does:** Lets you choose between disk types for your default node pool on Azure—options vary between high-durability managed disks and faster, transient ephemeral disks.  
  **When to Use:**  
  - **Managed:** Ideal for most production workloads requiring durability.  
  - **Ephemeral:** Suitable for transient workloads that demand higher performance with lower persistence.  
    **Default:** Managed.

- **Dedicated Node Pool Instance Type (Azure)**  
  **Label:** Dedicated Node Pool Instance Type (Azure)  
  **What It Does:** Specifies the instance type for dedicated node pools on Azure.  
  **When to Use:**  
  - Select an instance type that fits your performance needs and budget constraints.  
    **Default:** A recommended standard instance type is used by default.

### Dedicated Node Pool (Applies to All Clouds)

- **Dedicated Node Pool**  
  **Label:** Enable Dedicated Node Pool  
  **What It Does:** Activates the dedicated node pool feature to isolate high-priority or resource-intensive workloads from the general pool of nodes.  
  **When to Use:**  
  - Use this when you need to ensure that certain workloads receive dedicated resources for improved performance or security.  
    **Default:** Enabled.

- **Secure Boot for Dedicated Node Pool**  
  **Label:** Enable Secure Boot for Dedicated Node Pool  
  **What It Does:** Ensures that nodes only run trusted software, offering enhanced security.  
  **When to Use:**  
  - Consider enabling secure boot if your security policies require enhanced protection against low-level threats.  
    **Default:** Off

- **Secure Boot for Default Node Pool**  
  **Label:** Enable Secure Boot for Default Node Pool  
  **What It Does:** Provides the same trusted-boot functionality for the default node pool.  
  **When to Use:**  
  - Enable secure boot if your environment has stringent security requirements, particularly in regulated industries.  
    **Default:** Off

# Tips for Using Advanced Settings

- **Understand Your Workload:** Adjust settings based on whether your applications are production-critical, experimental, or resource-intensive.  
- **Test in a Staging Environment:** Before applying significant changes, validate the impact in a non-production environment.  
- **Monitor Performance and Costs:** Be aware that features such as auto-provisioning and high parallel release counts may increase resource usage or costs.  
- **Leverage Cloud-Specific Features:** Customize settings for your cloud provider to maximize performance and security benefits.