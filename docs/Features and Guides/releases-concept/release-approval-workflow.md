---
title: Release Approval Workflow
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
The Release Approval Workflow introduces a mechanism to manage release approvals for critical environments. Depending on custom conditions defined by the user in a script, releases can either proceed automatically or require explicit approval, ensuring greater control and governance during deployments. Only users with certain permissions will be able to approve/reject the pending releases. 

**Note:** Releases in Parallel cant go through if release are pending for approval. Hence, “Parallel Releases” can be enabled only when “Release Approval Workflow” is disabled and vice versa.

## How to Enable Release Approval Workflow in Facets

### Step 1: Prepare the Approval Script

1. Create a script that defines the conditions for approval.\
   **Example:**
   * Require approval only for specific environments.
   * Automate approval for other environments.
2. Ensure the script returns an exit code based on the required conditions:
   * **Exit Code 0:** Automatic approval (default behavior, the release executes immediately)
   * **Exit Code 2:** Release requires manual approval
   * **Other Codes:** The release fails

**Note:** Sample script is mentioned at the end of this document.

### Step 2: Integrate the Approval Workflow

1. Upload the script to the designated Facets Project's Git repository.
2. The path and nomenclature that should be followed for the script is: 

```Text Python
<project_name>/pre_release_hooks/pre_release_hook.py
```

[OR]

```Text Shell
<project_name>/pre_release_hooks/pre_release_hook.sh
```

3. Ensure Terraform plans or relevant operations use this script during release execution. 

**Sample Code:**

Sample of how release changes will be in the json file is as below:

```json json
{  
  "environmentName": "<environmentName>",  
  "releaseStream": "<releaseStream>",  
  "resources": [  
    {  
      "resourceType": "<resourceType>",  
      "resourceName": "<resourceName>",  
      "resourcePath": "<resourcePath>",  
      "changeType": "<changeType>" // CREATE|DELETE|UPDATE_IN_PLACE|REPLACE|RECREATE|NO_OPERATION  
    }  
  ]  
}
```

### Step 3: Configure Permissions

1. Assign approve/reject permissions (“Release Approval/Reject”) to approve or reject the triggered releases to specific users via RBAC settings.
2. Permissions include granting access to approve/reject from Facets UI. Users can also integrate tools like JIRA which can automatically create tickets as a release goes for approval. This needs to be handled outside Facets by the users.

## How to use the Release Approval Workflow?

### 1. Trigger a Release

When a release is triggered in an environment, it enters either:

* A queued state if there are other releases in progress in that environment.
* Or start immediately if there are no conflicts.

### 2. Script Execution

Once the release moves to a ready state, the approval script is executed. Based on the template script (mentioned at the end of this document), the following things are executed:

* **Exit Code 0:** Release proceeds automatically
* **Exit Code 2:** Release enters Pending Approval State
* **Other exit codes:** Release fails

### 3. Pending Approval Actions:

When a release enters Pending Approval Status:

* **Approval Step:** Users with 'Release Approval/Reject' permission can approve or reject the release from the Facets UI or through JIRA tickets (if configured). 
  * **On Approval:**
    * A new “Bot” Release is triggered automatically to apply the changes.
    * The original release status is updated to Approved.
  * **On Rejection:**
    * The release status changes to Rejected. Queued releases can proceed for execution.

<Embed url="https://app.storylane.io/demo/hbxyns2q1gil" title="Releases | Nov 28 3:02 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_ac706bdb-fa93-49a7-8be4-a2d7b56b1ef6/project/project_c6c521cb-9124-4a8a-9e9a-ec7b6382bfce/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/hbxyns2q1gil" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fhbxyns2q1gil%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fhbxyns2q1gil%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_ac706bdb-fa93-49a7-8be4-a2d7b56b1ef6%252Fproject%252Fproject_c6c521cb-9124-4a8a-9e9a-ec7b6382bfce%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Conditions for Release Approval Workflow

### Approval Workflow Execution

* Environments with Approval Requirement:
  * Releases to environments requiring approval follow the workflow defined in the script.
* Environments without Approval Requirement:
  * Releases proceed automatically if conditions are met (Exit Code 0).

### Handling Multiple Releases

* Pending Approval Releases:
  * Only one release can be in the Pending Approval state at a time.
  * New releases are in queued state until the pending release is resolved (approved or rejected).
* Queued releases are triggered once the approval is resolved.

## Sample Script to be added in the Facets Project's Github Repo

This sample script enables release approval workflow for all the environments with Release Stream set to "PROD":

```Text pre_release_hook.py
import sys
import json

def main():
    if len(sys.argv) != 2:
        print("Usage: python pre_release_hook.py <path_to_json_file>")
        sys.exit(1)

    json_file_path = sys.argv[1]

    try:
        with open(json_file_path, 'r') as file:
            data = json.load(file)
        
        environment_name = data.get("environmentName")
        release_stream = data.get("releaseStream")
        resources = data.get("resources", [])

        print(f"Environment Name: {environment_name}")
        print(f"Release Stream: {release_stream}")            
        print("Resources:")
        for resource in resources:
            print(f"  - Resource Type: {resource.get('resourceType')}")
            print(f"    Resource Name: {resource.get('resourceName')}")
            print(f"    Resource Path: {resource.get('resourcePath')}")
            print(f"    Change Type: {resource.get('changeType')}")
        
        if release_stream == "PROD":
            print(f"Exiting with exit code '2' since Release Stream is {release_stream}")
            sys.exit(2)

    except FileNotFoundError:
        print(f"Error: File not found - {json_file_path}")
        sys.exit(1)
    except json.JSONDecodeError:
        print(f"Error: Failed to decode JSON from file - {json_file_path}")
        sys.exit(1)

if __name__ == "__main__":
    main()
```
