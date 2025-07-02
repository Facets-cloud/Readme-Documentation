---
title: Locking a Resource
deprecated: false
hidden: true
metadata:
  robots: index
---
## Overview

Resource Locking in Facets helps safeguard your critical infrastructure by giving you the ability to lock individual resources from accidental changes. When a resource is locked, certain actions—like disabling the resource or modifying sensitive fields—are explicitly restricted. This feature is especially useful for production-grade components like databases, storage, or Kubernetes node pools.

***

## Why Lock Resources?

In complex environments, even a small mistake—like changing a field or disabling a live service—can lead to unexpected downtime or data loss. While tools like prevent\_destroy in Terraform offer some protection, they don’t help in cases where a resource is deleted or disabled from the blueprint entirely.

Resource Locking solves this by:

* Preventing critical resources from being disabled or deleted.
* Blocking edits to sensitive fields that are known to cause service disruption.
* Allowing module authors to define which fields are lock-sensitive.
* Adding a deliberate layer of control for safety-critical environments.

***

## How Locking Works

### Locked Resources:

* Cannot be disabled or deleted.
* **Fields marked as x-ui-lockable:** true in the module schema become read-only.
* Only users with the appropriate permissions can lock/unlock resources.
* All lock/unlock actions are tracked in audit logs.

### Unlocked Resources

* Default state of any resource.
* Can be edited or disabled normally.
* No restrictions apply.

***

## Use Cases

* Protect production databases from accidental shutdown or destructive updates.
* Lock Kubernetes node pools and persistent volumes that must remain stable.
* Allow module developers to mark fields like storage size or replica count as locked once deployed.

***

## How to Use Resource Locking

<Embed typeOfEmbed="jsfiddle" url="" />

## Permissions and Auditability

**RBAC Required:** Only users with lock/unlock\_resource permission can lock or unlock resources.

**Audit Logs:**

* Every lock/unlock event is recorded with the user, timestamp, and resource ID.
* Helps maintain accountability and change traceability.

## Summary

Resource Locking is designed to give teams peace of mind when working with critical infrastructure. By restricting high-risk actions behind an explicit lock mechanism and tying them to permissions and audit logs, Facets ensures that your most important resources are protected from human error.