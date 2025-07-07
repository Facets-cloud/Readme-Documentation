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

## What Is a Critical Resource?

A resource is considered critical if:

* The module YAML includes critical: true.
* Certain fields within the module are marked as critical using x-ui-critical: true.

Only users with the *modify\_critical\_resources* permission can:

* Delete the resource
* Change its status (enable/disable)
* Edit fields marked as x-ui-critical: true

Users without this permission will see these actions as disabled or read-only.

***

## Why Mark Resources as Critical?

In complex environments, even a small mistake—like changing a field or disabling a live service—can lead to unexpected downtime or data loss. While tools like **prevent\_destroy** in Terraform offer some protection, they don’t help in cases where a resource is deleted or disabled from the blueprint entirely.

By marking a resource as critical, Facets provides a deliberate control mechanism that:

* Prevents accidental deletion or disablement
* Restricts changes to sensitive fields
* Establishes clear boundaries based on role-based access control (RBAC)
* Ensures traceability through audit logs

***

## How It Works

### For Critical Resources

* Cannot be deleted or disabled by users without the required permission
* Fields marked with x-ui-critical: true are read-only unless the user has permission
* All actions are logged with full context (who, what, when)

### For Non-Critical Resources

* Behave as usual with no restrictions on status changes or field edits
* Accessible and editable by any user with general permissions

***

## Use Cases

* Prevent accidental deletion of **production databases**
* **Protect Kubernetes node pools** from scale-down or misconfiguration
* Ensure only authorized personnel can change **resource limits, persistent disk size, or compute allocations**

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