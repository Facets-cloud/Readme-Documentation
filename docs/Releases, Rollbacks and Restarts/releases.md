---
title: Performing a Release
excerpt: How to perform releases and gather information about a particular release
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
\<\<glossary:Releases>> are mutations that propagates to an environment. In this Section, you will learn how to perform and monitor a release that makes a change to the environment.

Facets is built on a key principle that any changes (release) to an environment has to happen through a single mechanism. These changes could be of

1. New code or updates (new builds)
2. New resources or updates
3. New interactions, schema, policies or updates

# Release Schedule

Releases are of two types

1. Scheduled Release: A Scheduled release [pattern](https://crontab.guru/) is defined in the "edit" environment section in the "Misc" tab. For e.g., a <code>30 5 * * *</code> would mean a scheduled release (full) will happen at <code>5:30 AM, every day</code>.
2. On-demand Release: An on-demand release can be performed in an environment from the "Releases" page. You can make a full or partial release from this page.

   1. Release - Perform a full release i.e. every resource on the Blueprint and their qualified builds will sync to the environment
   2. Selective - Perform a selective release of one or selected resources. This is usually used as a hotfix to the environment

![](https://files.readme.io/ca75549-Screen_Shot_2022-03-29_at_10.18.29_PM.png "Screen Shot 2022-03-29 at 10.18.29 PM.png")

# Release Candidates

Once a release is performed the following details are available for it.

<HTMLBlock>{`
<table style="width: 100%; border-collapse: collapse;">
<thead>
<tr>
  <th style="border: 1px solid #ddd; padding: 8px;"></th>
  <th style="border: 1px solid #ddd; padding: 8px;"></th>
</tr>
</thead>
<tbody>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Started</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>When was the release triggered</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Status</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>&lt;span style={{ color: &quot;green&quot; }}&gt;SUCCESS</span> or &lt;span style={{ color: &quot;red&quot; }}&gt;FAIL</span></p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Last Commit</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>The git commit up to which the IDP has pulled the changes</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Release Type</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>RELEASE (Indicates a full release)<br>LAUNCH (Environment launch)<br>HOTFIX (Indicates a selective release)</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Triggered By</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Either a <strong>user</strong><br>Or<br><strong>Facets Bot</strong> (indicating a scheduled release)</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Action</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><ol>
<li>Release Details  </li>
<li>Terraform Logs</li>
</ol>
</td>
</tr>
</tbody>
</table>
`}</HTMLBlock>

## Release Details

The release details Action shows the resource changes i.e <span style={{ color: "green" }}>Creations</span>, <span style={{ color: "GoldenRod" }}>Modification</span> (i.e. new versions of apps) or <span style={{ color: "red" }}>Destruction</span>.

<Image
  src="https://files.readme.io/7169c77-Screen_Shot_2022-03-29_at_11.22.57_PM.png"
  alt="Release Details"
  align="center"
  caption="Release Details"
/>


## Release Logs

The release logs provide a detail view of the generated terraform logs.

<Image
  src="https://files.readme.io/4c2ff6b-Screen_Shot_2022-03-30_at_12.01.10_AM.png"
  alt="Terraform Logs"
  align="center"
  caption="Terraform Logs"
/>


# Release Summary

The release summary page is aggregated release summary for last 30 days. This provides metrics that can lead to improvement in the SDLC.

|                      |                                                  |
| :------------------- | :----------------------------------------------- |
| Successful Releases  | Number of Successful Releases in last 30 days    |
| Failed Releases      | Number of Failed Releases in last 30 days        |
| Deployment Frequency | Average deployment per day                       |
| Change Failure Rate  | Percentage of changes that resulted in a failure |