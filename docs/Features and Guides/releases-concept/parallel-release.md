---
title: Parallel Releases
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
Parallel Release feature enables simultaneous execution of multiple **Selective Releases** for service resources within the same environment, enhancing deployment flexibility and speed. 

By allowing parallel execution of non-conflicting releases, this feature minimises deployment time while efficiently handling conflicts through queuing or error management.

**Note:** Releases in Parallel cant go through if release are pending for approval. Hence, “Parallel Releases” can be enabled only when “Release Approval Workflow” is disabled and vice versa.

## How to Enable Parallel Releases?

1. Navigate to **Settings > General** to view the Control Plane settings.
2. Set **Enable Parallel Releases** to **true** (this is set to false by default).
3. Specify the **Maximum Parallel Releases** that can be executed across the Control Plane.\
   **Note:** The default value for Maximum Parallel Releases is set to 10.
4. Click **Save Changes.**

You have successfully enabled the parallel release.

## How to Use Parallel Releases?

<Embed url="https://app.storylane.io/demo/pxb4pvzxompv" title="Projects | Nov 28 3:23 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_25738d37-f3f6-462d-9648-f82a03dfca0b/project/project_417c97c3-a06c-4df7-9f41-10ef98f3c0ab/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/pxb4pvzxompv" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fpxb4pvzxompv%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fpxb4pvzxompv%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_25738d37-f3f6-462d-9648-f82a03dfca0b%252Fproject%252Fproject_417c97c3-a06c-4df7-9f41-10ef98f3c0ab%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

### Triggering Releases

* Perform multiple Selective Releases as usual. The Control Plane automatically executes non-conflicting releases in parallel.

### Execution Logic

* Non-conflicting releases run in parallel. 
* Conflicting releases are queued or fail with a state lock error, requiring manual re-triggering.

### Conflict Scenarios & Error Handling

* Parallel execution supports Selective Updates and Selective Create/Delete unless they target the same resource.
* Conflicting releases involving shared resources or Selective Create/Delete result in queuing or state lock errors.
* Re-trigger failed releases after resolving conflicts for smooth deployment.

### Rollback Support

* Rollbacks are supported, but a release with refresh enabled may be necessary to fully restore the system.
