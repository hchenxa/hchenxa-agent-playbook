---
description: Generate the zstream test plan based on the issues
example: "egent_start: generate the zstream test based for MCE 2.9.0 release"
parameters:
  target_go_version:
    description: Target Go version
  releases_list:
    description: Comma-separated list of release
dependencies:
  - knowledge/jira/jira_components.md
---

The goal is to generate the zstream test plan based on the bugs from the different releases.

To generate the zstream test plan for each of releases in the {{releases_list}}, you should following below steps:
- use mcp server, you should query the bugs from jira with status is Review and fixVersion with the release version I provided.
- you should able to get the Component for each of issues and category the bugs based on the Component name
- you should show me the bug list with the URL and also the contractor name for each of the Component
