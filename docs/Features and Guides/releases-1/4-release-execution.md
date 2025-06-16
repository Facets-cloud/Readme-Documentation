---
title: 4. Release Execution
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
This document provides a comprehensive overview of the key features and functionalities associated with release management. It covers Queued Releases, Paused Releases, CLI-based Releases, Parallel Releases, and Scheduled Releases. Additionally, it includes troubleshooting guidelines to help identify and resolve common issues encountered during the release process.

***

## 1. Queued Releases

### Overview

Queued Releases allow users to initiate a new release even when a previous release is still in progress. This functionality ensures that deployments continue seamlessly, as the system automatically manages the release sequence through a queueing mechanism.

### Use Cases

This feature is particularly useful in continuous deployment workflows, where minimizing manual intervention is critical. It helps manage multiple simultaneous release requests from different users, thereby avoiding potential deployment failures that could result from overlapping releases.

### Key Features

Queued Releases are enabled by default and do not require any manual configuration. All releases that are in the queue can be viewed in the **Active Releases** section on the **Releases Page**. Users also have the ability to delete queued releases if necessary.

Each queued release includes detailed metadata, such as:

* Release Type
* Whether the release is a refresh (`true`/`false`)
* Whether the release is forced (`true`/`false`)
* Whether destructive actions are allowed (`true`/`false`)
* Any associated comments
* The user who triggered the release

For Selective Releases, additional information such as the Resource Type, Resource Name, and the specific actions is also displayed.

**Note:** Scheduled releases will not be queued if a release is already in progress for the same environment.

***

## 2. Paused Releases

### Overview

The Paused Release feature allows users to temporarily halt the initiation of any release type, including Launch, Full, Selective, Custom, and Destroy releases. This provides greater control over the release process and helps avoid unintended or poorly-timed deployments.

### Use Cases

Common scenarios for pausing releases include planned maintenance windows or compliance with change freeze periods. It also allows teams to better manage the timing of releases in coordination with business or infrastructure readiness.

### Key Features

When a release is paused, it overrides the availability rules configured for the environment. Users can later resume (unpause) the release process as required.

Releases can be paused at two different levels:

* **Blueprint Level**: Enables release pausing or resumption for an entire environment through the **Environments Tab**.

  <Image align="center" width="600px" src="https://files.readme.io/ddf49b13ab1b9f13d88266547aa1b1b59d2b2374f9274c2ec427bdf9de016986-Screenshot_2025-04-09_at_10.39.28_AM.png" />
* **Environment Level**: Provides control over individual environments via the **Releases Page**.

  <Image align="center" width="600px" src="https://files.readme.io/71305c9908f74860651f7f7fba264680dcd6699e8fc7e4b6ecb2d62033f4c8c0-Screenshot_2025-04-09_at_10.39.49_AM.png" />

***

## 3. CLI-based Releases

### Overview

The CLI-based release management system enables users to trigger and monitor releases directly through the command line using `facetsctl`. This approach is well-suited for automating deployment processes and integrating releases into CI/CD pipelines. [Read More](https://www.npmjs.com/package/@facets-cloud/facetsctlv3)

### Use Cases

CLI-based releases are ideal for DevOps teams that want to automate application synchronization, maintain state consistency, and manage deployments programmatically within scripted workflows.

### CLI Commands

#### `facetsctl release sync APPS`

This command synchronizes the specified applications, bringing them into alignment with their desired state.

##### Usage

```sh
$ facetsctl release sync APPS -p <project> -e <environment>
```

##### Arguments

* `APPS`: A comma-separated list of application names to be synchronized.

##### Flags

| Flag                        | Required | Description                     |
| --------------------------- | -------- | ------------------------------- |
| `-e, --environment=<value>` | Yes      | Specifies the environment name. |
| `-p, --project=<value>`     | Yes      | Specifies the project name.     |

#### `facetsctl release wait APPS`

This command waits for the specified applications to reach a stable sync state. Optionally, it can trigger a sync operation if the `--sync` flag is provided.

##### Usage

```sh
$ facetsctl release wait APPS -p <project> -e <environment> [--sync]
```

##### Arguments

* `APPS`: A comma-separated list of application names.

##### Flags

| Flag                        | Required | Description                                          |
| --------------------------- | -------- | ---------------------------------------------------- |
| `-e, --environment=<value>` | Yes      | Specifies the environment name.                      |
| `-p, --project=<value>`     | Yes      | Specifies the project name.                          |
| `--sync`                    | No       | Triggers a sync if the applications are out of sync. |

***

## 4. Parallel Releases

### Overview

Parallel Releases allow users to execute multiple **Selective Releases** simultaneously within the same environment. This significantly improves deployment efficiency by reducing overall release time when changes do not conflict.

### Use Cases

This feature is beneficial when deploying multiple microservices at the same time, especially when those services are independent. It enables teams to perform concurrent updates and reduces the deployment window for large-scale or distributed systems.

### Key Features

Only non-conflicting releases are eligible to run in parallel. If conflicts are detected, the release is either queued or may fail with a state lock error.

**Note:** The "Release Approval Workflow" must be disabled in order to use Parallel Releases.

### How to Enable Parallel Releases

<Embed url="https://app.storylane.io/demo/pxb4pvzxompv" title="Projects | Nov 28 3:23 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_25738d37-f3f6-462d-9648-f82a03dfca0b/project/project_417c97c3-a06c-4df7-9f41-10ef98f3c0ab/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/pxb4pvzxompv" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fpxb4pvzxompv%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fpxb4pvzxompv%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_25738d37-f3f6-462d-9648-f82a03dfca0b%252Fproject%252Fproject_417c97c3-a06c-4df7-9f41-10ef98f3c0ab%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

1. Navigate to **Settings > General**.
2. Enable the **Parallel Releases** option (disabled by default).
3. Set the **Maximum Parallel Releases** limit (default: 10).
4. Click **Save Changes** to apply the configuration.

### Execution Behavior

Releases that do not modify overlapping resources will execute in parallel. If there are any conflicts, the release may be queued or result in a state lock error. In case of failures, rollbacks are supported, although some may require a refresh to fully restore the desired state.

***

## 5. Scheduled Releases

### Overview

Scheduled Releases allow users to automate their deployment workflows by specifying a predefined schedule. This ensures timely deployments without manual triggers and helps maintain consistency across release cycles.

### Use Cases

Scheduled Releases are especially useful for periodic updates, automating routine deployments, and ensuring that releases align with business hours, compliance requirements, or maintenance windows.

### How to Configure a Scheduled Release

<Embed url="https://app.storylane.io/demo/maciqnme2jja" title="Overview | Feb 17 4:36 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_daf0ad98-ee90-4d76-8392-d94a2403ac00/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/maciqnme2jja" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fmaciqnme2jja%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fmaciqnme2jja%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_daf0ad98-ee90-4d76-8392-d94a2403ac00%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

1. **Open Environment Settings**
   * Navigate to the **Environment Settings** section and go to the **Releases** tab.

2. **Configure the Schedule**
   * Toggle the **Available** option to enable scheduled releases.
   * Choose the desired frequency:
     * **Minutes**: For rapid deployment intervals.
     * **Hours**: For more frequent daily deployments.
     * **Days**: For longer development and testing cycles.
     * **Weeks**: For production-grade, stable deployments.
   * Define the specific interval for the release schedule.
   * Use the **Pause** toggle to temporarily suspend the scheduled release.

3. **Save the Configuration**
   * Click **Save Changes** to activate the schedule.
   * Manual release triggers will still be available in parallel with the schedule.

***

## Troubleshooting

### Release Not Triggering

**Possible Causes:**

* The environment may have an active paused release.
* A scheduled release could be conflicting with an ongoing deployment.
* A state lock error may be preventing the release due to resource conflicts.

**Resolution:**

* Resume the paused release via the **Releases Page**.
* Adjust the release schedule to avoid overlaps with ongoing deployments.
* Resolve any conflicting resource states and retry the release.

***

### Parallel Release Not Executing

**Possible Causes:**

* The **Release Approval Workflow** is currently enabled, which blocks parallel execution.
* The environment has reached the maximum configured limit for parallel releases.

**Resolution:**

* Disable the **Release Approval Workflow** to enable parallel execution.
* Increase the **Maximum Parallel Releases** value in the system settings.

***

### CLI Sync Command Not Working

**Possible Causes:**

* The specified project or environment name may be incorrect.
* The targeted applications are already in sync and require no action.

**Resolution:**

* Confirm and correct the environment and project identifiers.
* Use the `--sync` flag to enforce synchronization even if applications appear in sync.
