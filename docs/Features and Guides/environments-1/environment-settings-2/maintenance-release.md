---
title: Maintenance Release
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
**Maintenance Release** is a type of release designed to execute IaC migration scripts separately from regular (full or selective) releases. These migrations are essential for keeping your infrastructure up-to-date with the latest IaC version. They might involve changes to your cloud resources, configurations, or dependencies.

### Why are Maintenance Releases important?

The Maintenance Release feature addresses the following cases by:

* **Reducing Downtime Risk:** Migration scripts are run in dedicated maintenance windows, ensuring that infrastructure changes don’t disrupt live environments.
* **Enhancing Control:** Users can manually trigger pending migrations, providing more control over when upgrades are applied.
* **Improving Visibility:**  The Maintenance Details page offers transparency into pending migration scripts, including sequence, downtime requirements, and cloud compatibility.
* **Proactive Notifications:** Environment-level notifications keep users informed of maintenance, enabling proactive planning and communication.
* **Streamlined Compliance & Security:** Blocking further releases in case of migration failures prevents inconsistent states, ensuring system integrity and reducing deployment errors.

### How do Maintenance Releases work?

1. **Pending Migration Identification:** When a new IaC version is uploaded or version is changed, Facets identifies pending migrations by comparing the current IaC version of your environment with the latest version available.
2. **Maintenance Window:** You can configure a specific maintenance window for your environment. During this window, pending migrations will be executed automatically as a Maintenance Release.
3. **Manual Trigger:** If you need to execute migrations outside of the maintenance window, you can use the "**Run Maintenance**" button to trigger a Maintenance Release manually.
4. **Notifications and Visibility:** Facets provides notifications about success or failure of Maintenance Releases. The Maintenance Details page shows details about each migration script, including its sequence number, description, downtime requirement, and supported clouds.
5. **Release Blocking:**  If a Maintenance Release fails, subsequent releases (full and selective) are blocked to prevent inconsistencies. A notification prompts you to contact Facets Support for assistance. 

### How to use Maintenance Releases

<Embed url="https://app.storylane.io/demo/n2wrdmajcvau" title="Maintenance releases" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_3e09d3cb-e6f5-477d-829f-0230b0c728b1/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/n2wrdmajcvau" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fn2wrdmajcvau%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fn2wrdmajcvau%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_3e09d3cb-e6f5-477d-829f-0230b0c728b1%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22431%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

### Best Practices for Maintenance Releases

* **Plan and Test Updates:** Schedule maintenance windows during low-traffic periods and validate updates in a staging environment before applying them to production.  

* **Communicate and Notify:** Inform stakeholders in advance about maintenance schedules and use proactive notifications to keep teams updated on pending updates and their impact.  

* **Monitor and Verify Post-Update:** Check environment status after maintenance to ensure updates were successful and maintain records for traceability.  

* **Prepare for Rollbacks:** Always have a rollback plan ready to address issues quickly and avoid prolonged disruptions.

### FAQs for Maintenance Releases

#### 1. **What happens if a Maintenance Release is not executed?**

If pending infrastructure updates are not applied, your environment may remain in an outdated state, increasing the risk of inconsistencies and potential deployment issues in future releases.

***

#### 2. **Can I proceed with regular releases if there are pending updates?**

Yes, if there are pending updates that require a Maintenance Release, releases can still be executed with the stable IAC version.

***

#### 3. **What details are shown in the Maintenance Details page?**

The Maintenance Details page provides a breakdown of pending updates, including sequence, description, and downtime requirements, helping you assess their impact.

***

#### 4. **Can I customize notifications for Maintenance Releases?**

Yes, you can configure environment-level notifications to receive alerts about pending updates, their potential downtime, and the success or failure of Maintenance Releases.
