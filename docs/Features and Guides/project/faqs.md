---
title: FAQs
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
### **1. Can I change the GitOps account after creating a project?**

**Answer:** Yes, you can change the GitOps account in the **Project Settings > GitOps** section. However, ensure that the new account has access to the correct repository and branch to avoid configuration errors. Verify that permissions are properly configured to prevent deployment failures.

***

### **2. How can I ensure that overrides are properly migrated before enabling GitOps for Overrides?**

**Answer:** Before enabling **GitOps for Overrides**, follow these steps to ensure a smooth migration:  

1. Verify that all environment-specific configuration overrides are stored in the repository at the correct path.  
2. Double-check that the repository permissions allow write access.  
3. Test the environment after migration to confirm that the applied configurations match your expected setup.

**Important:** Once overrides are migrated and GitOps is enabled, changes can no longer be made via the UI.

***

### **3. What are the limitations of the "Restrict UI Changes" option?**

**Answer:** When **Restrict UI Changes** is enabled, all modifications must be performed through Git. This ensures configuration consistency but removes the ability to make quick changes through the Facets UI.  

Consider enabling this option only if your team follows strict version control workflows and is comfortable making all changes through version control systems.

***

### **4. What’s the difference between "Single Branch Promotion" and "Branch Per Environment"?**

**Answer:**  

* **Branch Per Environment:** Each Git branch is mapped to a specific environment (e.g., the `dev` branch for the Development environment).  
* **Single Branch Promotion:** One branch is linked to multiple environments, and changes are automatically promoted from one environment to the next (e.g., from `staging` to `production`).  

**When to use:**  

* Choose **Single Branch Promotion** if you prefer a linear progression of changes through environments.  
* Choose **Branch Per Environment** if you want parallel testing across multiple branches/environments.
