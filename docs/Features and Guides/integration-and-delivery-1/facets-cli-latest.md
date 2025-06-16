---
title: Facets CLI
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
**Note:** If you are using the older version of facetsctl, refer to the [Facets CLI](doc:command-line-tool-for-facets) documentation.

This documentation serves as a quick reference guide for using the facetsctlv3 CLI tool. It offers an easy-to-use alternative to Facets APIs, enabling users to push new Docker artifacts to the Facets Control Plane and refresh Kubernetes credentials for a specified environment.

## NPM Page

You can view and download the latest `facetsctlv3` package from its [NPM page](https://www.npmjs.com/package/@facets-cloud/facetsctlv3).

## Commands

**Note:** Ensure you run the login and artifact init commands before using the push, register, or upload commands.

`facetsctlv3` provides the following commands for users:

### `facetsctl help`

This command displays the help for facetsctlv3. You can use it to get information about a specific command by providing the command name as an argument.

```Text Shell
 **ARGUMENTS**  $ facetsctl help [COMMAND...] [-n]
```

**ARGUMENTS**

COMMAND: Command to display help for.

**FLAGS**

| Flag                    | Required | What does it do?                                                 |
| :---------------------- | :------- | :--------------------------------------------------------------- |
| `-n, --nested-commands` | No       | Defines if all nested commands should be included in the output. |

***

### `facetsctl login`

This command allows the user to log in to the Facets Control Plane.

```shell
$ facetsctl login -u <value> -t <value> -f <value>
```
```Text Example
$ facetsctl login --username my-user --token my-token --facets-url https://facets-control-plane.example.com
```

**FLAGS**

| Flag                       | Required | What does it do?                      |
| :------------------------- | :------- | :------------------------------------ |
| `-f, --facets-url=<value>` | Yes      | Defines the URL of the Control plane. |
| `-t, --token=<value>`      | Yes      | Defines the Personal token.           |
| `-u, --username=<value>`   | Yes      | Defines the Username.                 |

***

### `facetsctl artifact init`

This command allows you to initialize the artifact information.

```shell
$ facetsctl artifact init -p <value> -s <value> -a <value>
```
```Text Example
$ facetsctl artifact init --project my-project --service my-service --artifactory my-artifactory
```

**FLAGS**

| Flag                                | Required | What does it do?              |
| :---------------------------------- | :------- | :---------------------------- |
| `-a, --artifactory=<value>`         | Yes      | Defines the Artifactory name. |
| `-p, --project=<value>`             | Yes      | Defines the Project name.     |
| `-s, --service=<value>` = `<value>` | Yes      | Defines the Service name.     |

***

### `facetsctl artifact push`

This command allows you to push a Docker image to the configured artifact repository.

```shell
$ facetsctl artifact push -d <value>
```
```Text Example
$ facetsctl artifact push --docker-image my-docker-image:latest
```

**FLAGS**

| Flag                          | Required | What does it do?                             |
| :---------------------------- | :------- | :------------------------------------------- |
| ` -d, --docker-image=<value>` | Yes      | Defines the URL of the Docker image to push. |

***

### `facetsctl artifact register`

This command allows you to register a Docker image with the specified type and value.

```shell
$ facetsctl artifact register -t GIT_REF|ENVIRONMENT|RELEASE_STREAM -i <value> -v <value> [-r <value>]
```
```Text Example
$ facetsctl artifact register --type GIT_REF --docker-image my-docker-image:latest --value my-git-ref
```

**FLAGS**

[block:parameters]
{
  "data": {
    "h-0": "Flag",
    "h-1": "Required",
    "h-2": "What does it do?",
    "0-0": "`-i, --docker-image=<value>`",
    "0-1": "Yes",
    "0-2": "Defines the Docker image to register.",
    "1-0": "`-r, --runId=<value>`",
    "1-1": "No",
    "1-2": "Used to corelate to your CI system.",
    "2-0": "`-t, --type=<option>`",
    "2-1": "Yes",
    "2-2": "Defines the Type (GIT_REF, ENVIRONMENT, RELEASE_STREAM).  \n\\<options: GIT_REF|ENVIRONMENT|RELEASE_STREAM>",
    "3-0": "`-v, --value=<value>`",
    "3-1": "Yes",
    "3-2": "Defines the value of the specified type."
  },
  "cols": 3,
  "rows": 4,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


***

### `facetsctl artifact upload`

This command allows you to upload any type of application build file to the Facets Control Plane

```shell
$ facetsctl artifact upload -t GIT_REF|ENVIRONMENT|RELEASE_STREAM -f <value> -v <value> [-r <value>]
```
```Text Example
 $ facetsctl artifact upload --type GIT_REF --file-path file-to-upload --value my-git-ref
```

**FLAGS**

[block:parameters]
{
  "data": {
    "h-0": "Flag",
    "h-1": "Required",
    "h-2": "What does it do?",
    "0-0": "`-f, --file-path=<value>`",
    "0-1": "Yes",
    "0-2": "Defines the path to the application build file (e.g., WAR, JAR, ZIP) on your local system.",
    "1-0": "`-r, --runId=<value>`",
    "1-1": "No",
    "1-2": "Used to corelate to your CI system.",
    "2-0": "`-t, --type=<option>`",
    "2-1": "Yes",
    "2-2": "Defines the Type (GIT_REF, ENVIRONMENT, RELEASE_STREAM).  \n\\<options: GIT_REF|ENVIRONMENT|RELEASE_STREAM>",
    "3-0": "`-v, --value=<value>`",
    "3-1": "Yes",
    "3-2": "Defines the value of the specified type."
  },
  "cols": 3,
  "rows": 4,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


***

### `facetsctl release sync APPS`

This command allows you to sync out-of-sync apps to match their desired state with the deployed state.

```Text Shell
$ facetsctl release sync APPS -p <value> -e <value>
```

**ARGUMENTS**

`APPS`:  List of app names to sync (comma-separated | example: ... sync app1,app2,app3 -p ...)

**FLAGS**

| Flag                        | Required | What does it do?              |
| :-------------------------- | :------- | :---------------------------- |
| `-e, --environment=<value>` | Yes      | Defines the Environment name. |
| `-p, --project=<value>`     | Yes      | Defines the Project name.     |

***

### `facetsctl release wait APPS`

This command allows you to wait for the sync status of the specified apps, and trigger sync if --sync is provided

```Text Shell
  $ facetsctl release wait APPS -p <value> -e <value> [--sync]
```

**ARGUMENTS**

`APPS`: List of app names to wait for (comma-separated | example: ... sync app1,app2,app3 -p ...)

**FLAGS**

| Flag                        | Required | What does it do?                        |
| :-------------------------- | :------- | :-------------------------------------- |
| `-e, --environment=<value>` | Yes      | Defines the Environment name.           |
| `-p, --project=<value>`     | Yes      | Defines the Project name.               |
| `--sync`                    | No       | Triggers a sync if apps are out-of-sync |

***

## Facets CLI version v1.1.2

#### For Mac Os

| Type | Architecture | Download link                                                                                                                                   |
| :--- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------------- |
| Gzip | 64-bit       | [facetsctl-darwin-x64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-x64.tar.gz)     |
| XZ   | 64-bit       | [facetsctl-darwin-x64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-x64.tar.xz)     |
| Gzip | ARM64        | [facetscti-darwin-arm64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-arm64.tar.gz) |
| XZ   | ARM64        | [facetsctI-darwin-arm64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-darwin-arm64.tar.xz) |

#### For Linux

| Type | Architecture | Download link                                                                                                                                 |
| :--- | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
| Gzip | 64-bit       | [facetsctl-linux-x64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-x64.tar.gz)     |
| XZ   | 64-bit       | [facetsctI-linux-×64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-x64.tar.xz)     |
| Gzip | ARM          | [facetsctl-linux-arm.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm.tar.gz)     |
| XZ   | ARM          | [facetsctl-linux-arm.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm.tar.xz)     |
| Gzip | ARM64        | [facetsctl-linux-arm64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm64.tar.gz) |
| XZ   | ARM64        | [facetsctl-linux-arm64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-linux-arm64.tar.xz) |

#### For Windows

| Type | Architecture | Download link                                                                                                                             |
| :--- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| Gzip | 64-bit       | [facetsctl-win32-x64.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x64.tar.gz) |
| XZ   | 64-bit       | [facetsctl-win32-x64.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x64.tar.xz) |
| Gzip | 32-bit       | [facetsctI-win32-x86.tar.gz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x86.tar.gz) |
| XZ   | 32-bit       | [facetsctI-win32-x86.tar.xz](https://facets-cf-templates.s3.amazonaws.com/oclif-tarballs/v3/production/latest/facetsctl-win32-x86.tar.xz) |