---
title: Versioning Strategy for Facets Modules
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
Facets modules are designed to be reusable, testable, and maintainable components that define infrastructure capabilities. To support evolving requirements while ensuring stability and backward compatibility, we employ a structured versioning strategy.

## Versioning Overview

Facets modules use two-digit version numbers, such as `1.0`, `1.1`, etc. Each increment signifies a major version change, indicating a backward-incompatible update. These changes may include:

- Reorganizations
- Codebase modifications
- Alterations that break existing interfaces or functionalities([Hacker News][1], [GitKraken][2])

The `facets.yaml` configuration captures only the major version. A new major version is introduced when changes cannot be accommodated within the existing version without breaking compatibility.

## Soft Versioning for Backward-Compatible Changes

Backward-compatible enhancements, bug fixes, and incremental improvements are managed through soft versioning. These changes are tracked internally using Git and the Facets platform, without altering the major version number in `facets.yaml`.

This approach allows for:

- Tracking of changes
- Rollback procedures
- Continuous improvement without disrupting existing integrations

## Directory Structure and Source Code Management

To facilitate the separation and maintenance of different major versions, each major version is maintained in its directory:

```

/modules/
  ├── my-module/
      ├── 1.0/
      ├── 1.1/
      └── 2.0/
```

This structure allows for:

- Parallel maintenance of multiple major versions
- Rollback procedures
- Demarcation of version-specific changes([Medium][3])

During the transition phase between versions, this approach ensures that both older and newer versions can be maintained.

_While Git tagging is an alternative method for version management, it can become challenging to maintain, especially when dealing with multiple active versions and ensuring consistency across environments. The directory-based approach offers a more straightforward and maintainable solution in such scenarios._

## Development Workflow for Soft Versioning

For backward-compatible changes within the same major version:

1. **Preview**: Implement changes in a feature branch and create a pull request for review.
2. **Testing**: Conduct tests for the module in a test Project to validate the changes in isolation.
3. **Publishing**: Merge the changes into the main branch and publish the updated module.

The history of these changes is preserved in the Git repository and the Facets platform, enabling reversion to previous states if necessary.

## Impact on Developers

When a new major version of a module is published:

- New instances of the module will default to the latest major version.
- Existing instances will receive a notification indicating the availability of a new version.
- The module's README should include migration steps to assist in upgrading to the new version.

This approach ensures that developers are informed of updates and have guidance on how to transition between versions.

## Best Practices

- Maintain documentation for each major version, including migration guides.
- Utilize semantic versioning principles to communicate the nature of changes.
- Ensure that modules are unit testable to validate patterns of usage in isolation.

By adhering to this versioning strategy, Facets modules remain robust, flexible, and user-friendly, accommodating growth and change without compromising stability.

***

For more information on building and managing Facets modules, refer to the [Building a Facets Module](https://readme.facets.cloud/docs/building-a-facets-module) guide.

***

[1]: https://news.ycombinator.com/item?id=31480306&utm_source=chatgpt.com "Proper use of Git tags - Hacker News"

[2]: https://www.gitkraken.com/gitkon/semantic-versioning-git-tags?utm_source=chatgpt.com "Managing Releases with Semantic Versioning and Git Tags"

[3]: https://techforyou.medium.com/leveraging-the-power-of-git-tags-types-commands-and-best-practices-24ab8c2aae88?utm_source=chatgpt.com "Leveraging the Power of Git Tags: Types, Commands, and Best ..."