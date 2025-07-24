---
title: Resource Variables
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
Facets empowers teams with resource-specific variable management right at the blueprint level. Each resource in your blueprint **can define its own unique set of variables**, establishing baseline configurations that serve as defaults.

This granular control means every resource maintains its own configuration set, while still allowing for environment-specific overrides when needed. The clear hierarchical structure makes it immediately apparent which values are inherited from the blueprint and which are customised for specific environments. This approach provides the perfect balance between standardisation and flexibility, ensuring your resources can be configured optimally for different scenarios.

<Image align="center" src="https://files.readme.io/a9b04fe643806c5766b5a152aaf545d4ae473ab1bf6859c1a814cd2b8a64f0db-Screenshot_2025-02-12_at_11.34.56_AM.png" />

### Real-World Application

Consider an application service that needs different configuration across environments.

**In the Blueprint:**

```
user-service:
  variables:
    SLD_INIT_USER_EMAIL: "support@company.com"
    API_RATE_LIMIT: "1000"
    FEATURE_FLAGS_ENABLED: "true"
    DEFAULT_USER_ROLE: "basic"
```

**For Production Environment:**

```
production:
  user-service:
    variables:
      SLD_INIT_USER_EMAIL: "enterprise-support@company.com"
      API_RATE_LIMIT: "5000"
      DEFAULT_USER_ROLE: "enterprise"
```

This approach transforms resource configuration management **from a complex, multi-file system into a clear, hierarchical structure** that's easy to understand and maintain.