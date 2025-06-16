---
title: Self Hosted Gitlab
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
> ❗️ This feature is in Beta and please contact us if you face any issues.

<br />

### Interactive Walkthrough

Here's an Interactive demo showing the step-by-step self-hosted GitLab linking process

<Embed url="https://app.storylane.io/demo/awkrwbjlk24o" title="Projects | Feb 5 11:45 AM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_831186b0-f039-4378-b832-cfc753e69a5c/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/awkrwbjlk24o" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fawkrwbjlk24o%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fawkrwbjlk24o%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_831186b0-f039-4378-b832-cfc753e69a5c%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

### Step 1:

Link your self-hosted GitLab account to enable GitOps workflows for project creation and environment management.

### Prerequisites

* Admin access to your self-hosted GitLab instance.
* A valid GitLab Personal Access Token (PAT) with API, read\_repository, and write\_repository permissions.

### Configuration Steps

#### Display Name\*

Enter a unique identifier for this GitLab account (e.g., gitlab-custom).

#### GitLab Hostname\*

Provide your self-hosted GitLab instance URL (e.g., [https://gitlab.yourcompany.com](https://gitlab.yourcompany.com)).

> 📘 Note: For default setups, this may be http\://gitlab.com or a custom domain.

### Personal Access Token\*

Generate Token in GitLab:

* Navigate to your GitLab profile: Preferences > Access Tokens.
* Select scopes: api, read\_repository, write\_repository.
* Copy the generated token.
* Paste the Token in the 'Personal Access Token' field in the UI.

### Connection Options

* Link Account: Validate and save the configuration.
* Back: Return to previous settings.
* Cancel: Abort the setup process.

<br />

## 🚧 Coming Soon: App-Based Integration

We are actively developing OAuth2 app-based authentication for integration with self-hosted GitLab. 

Need help?\
Contact [support@facets.cloud](mailto:support@facets.cloud) or review GitLab’s PAT documentation.
