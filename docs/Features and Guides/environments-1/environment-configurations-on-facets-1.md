---
title: Environment Configurations on Facets
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
Environments in Facets represent distinct deployment destinations for your cloud architecture blueprints. Each environment can have its own specific configurations, allowing you to maintain consistent infrastructure while accommodating different requirements across development, testing, and production deployments.

## Configuration Overrides

Facets allows you to customize configurations for each environment through overrides. This feature enables you to:

- Modify resource configurations without changing the blueprint
- Manage environment-specific variables
- Maintain blueprint integrity while supporting environment-specific customisation needs

## Types of Environment Configurations

### Resource Configurations

Configure infrastructure-specific settings for each environment:

- Compute resources (CPU cores: 2 cores for production, 0.5 cores for testing)
- Memory allocation (8GB RAM for production, 2GB for development)
- Storage capacity (1TB for production databases, 100GB for testing)
- Instance types (production-grade vs development instances)
- Scaling parameters (auto-scaling limits, minimum replicas)

### Environment Variables

Define environment-specific operational parameters:

- API endpoints (<https://api.prod.example.com>, <https://api.dev.example.com>)
- Service URLs (production CDN vs development asset server)
- Feature flags (enable beta features in development only)
- Logging levels (DEBUG for development, INFO for production)
- Cache settings (cache sizes, TTL values)

### Secrets Management

Manage sensitive data separately for each environment:

- Database credentials (production vs development database users)
- API keys (production API keys vs test API keys)
- Authentication tokens (production authentication services)
- Encryption keys (environment-specific encryption)
- Service account credentials (production service accounts vs test accounts)