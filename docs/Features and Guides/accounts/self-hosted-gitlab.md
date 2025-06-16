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

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fawkrwbjlk24o&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fawkrwbjlk24o&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_831186b0-f039-4378-b832-cfc753e69a5c%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/awkrwbjlk24o",
  "title": "Projects | Feb 5 11:45 AM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_831186b0-f039-4378-b832-cfc753e69a5c/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/awkrwbjlk24o",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

### Step 1:

Link your self-hosted GitLab account to enable GitOps workflows for project creation and environment management.

### Prerequisites

- Admin access to your self-hosted GitLab instance.
- A valid GitLab Personal Access Token (PAT) with API, read_repository, and write_repository permissions.

### Configuration Steps

#### Display Name\*

Enter a unique identifier for this GitLab account (e.g., gitlab-custom).

#### GitLab Hostname\*

Provide your self-hosted GitLab instance URL (e.g., <https://gitlab.yourcompany.com>).

> 📘 Note: For default setups, this may be http\://gitlab.com or a custom domain.

### Personal Access Token\*

Generate Token in GitLab:

- Navigate to your GitLab profile: Preferences > Access Tokens.
- Select scopes: api, read_repository, write_repository.
- Copy the generated token.
- Paste the Token in the 'Personal Access Token' field in the UI.

### Connection Options

- Link Account: Validate and save the configuration.
- Back: Return to previous settings.
- Cancel: Abort the setup process.

<br />

## 🚧 Coming Soon: App-Based Integration

We are actively developing OAuth2 app-based authentication for integration with self-hosted GitLab. 

Need help?  
Contact [support@facets.cloud](mailto:support@facets.cloud) or review GitLab’s PAT documentation.