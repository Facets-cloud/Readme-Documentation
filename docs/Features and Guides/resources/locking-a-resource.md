---
title: Critical Resources
deprecated: false
hidden: true
metadata:
  robots: index
---
## Overview

Critical Resources in Facets are designed to **help protect sensitive infrastructure components** by restricting who can make impactful changes. When a resource is marked as critical, specific actions—such as deleting the resource, changing its status, or editing sensitive fields—are limited to users with explicit permissions.

This feature is essential for high-stakes infrastructure components such as production databases, Kubernetes node pools, or persistent storage, where unintended changes can lead to downtime or data loss.

***

## Why Mark Resources as Critical?

In complex environments, even a small mistake—like changing a field or disabling a live service—can lead to unexpected downtime or data loss. While tools like **prevent\_destroy** in Terraform offer some protection, they don’t help in cases where a resource is deleted or disabled from the blueprint entirely.

By marking a resource as critical, Facets provides a deliberate control mechanism that:

* Prevents accidental deletion or disablement
* Restricts changes to sensitive fields
* Establishes clear boundaries based on role-based access control (RBAC)
* Ensures traceability through audit logs

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