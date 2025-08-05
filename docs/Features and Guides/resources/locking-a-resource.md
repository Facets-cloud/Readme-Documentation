---
title: Critical Resources
deprecated: false
hidden: false
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
* Certain fields within the module are marked as critical using **x-ui-critical**

Only users with the *write\_critical\_resources* permission can:

* Delete the resource
* Change its status (enable/disable)
* Edit fields marked as **x-ui-critical**

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
* Fields marked with **x-ui-critical** are read-only unless the user has permission
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

## How to Use Critical Resources

<Embed typeOfEmbed="jsfiddle" url="https://app.storylane.io/demo/idsplwjfzypk" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fidsplwjfzypk%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fidsplwjfzypk%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_b6aade33-8526-47d6-80b1-4968122008aa%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" href="https://app.storylane.io/demo/idsplwjfzypk" providerUrl="https://www.storylane.io" providerName="Storylane" />

## Permissions and Auditability

**Permission Required**: Only users with the *write\_critical\_resources* permission can make restricted changes to critical resources.

**Audit Logs**: Every critical action (delete, disable, modify critical fields) is logged with timestamp, user ID, and resource ID

Ensures traceability and compliance across your infrastructure operations

***

## Summary

Critical Resources in Facets offer a robust safeguard for infrastructure components that require careful handling. By embedding this control directly into the platform, teams gain confidence that production-grade systems are protected from accidental or unauthorised modifications. The result: safer operations, cleaner access controls, and greater peace of mind across your engineering org.