The goal is to generate the zstream test plan based on the Jira bugs from the different releases.

In order to generate the zstream test plan for releases in the {{releases}}, you should following below steps:

- first, use mcp server to query the  jira issue, you should use the mcp tools to find all issues with the issue_type is Vulnerability or Bug and the status is Review, Testing, Resolved and Closed, and use the release version I provided as the fixVersion, and the fixVersion format will be like 'MCE x.y.z' or 'ACM x.y.z' or 'GLO x.y.z'. and set the fields parameters with the summary, status, components, labels, issuetype, description, and set the limit to 50 and set the project to ACM.
- After you get the issues lists, you should get the value of Components from each of issues and category the bugs based on the value of Components. 
- you should know the owner of each Components follow below table. 

| Component             | Owner                        |
| --------------------- | ---------------------------- |
| Server Foundation     | @serverfoundation@redhat.com |
| Application Lifecycle | @alc@redhat.com              |
| Global Hub            | @glo@redhat.com              |
| Cluster Lifecycle     | @clc@redhat.com              |
| HyperShift            | @hypershift@redhat.com       |
| Console               | @console@redhat.com          |
| Search                | @search@redhat.com           |
| Business Continuity   | @dr4hub@redhat.com           |
| Installer             | @installer@redhat.com        |
| Observability         | @obs@redhat.com              |

- And then create a markdown file named test-plan-{date}.md and the file contains the bug list with the URL and add owner name for each of components, and the output will be a markdown format and should like below:
```
## Test plan for zstream release {{release_list}}

### Bugs to be retested:
#### {{ Value of Component }}: {{ owner }}
- {{ issue ID }}: https://issues.redhat.com/browse/{{ issue ID }}
- {{ issue ID }}: https://issues.redhat.com/browse/{{ issue ID }}
...

#### {{ Value of Component }} {{ owner }}
- {{ issue ID }}: https://issues.redhat.com/browse/{{ issue ID }}
- {{ issue ID }}: https://issues.redhat.com/browse/{{ issue ID }}
...

### Release Notes:
| Issue Type | Issue Key | Priority | Status | Assignee | Summary |
|---|---|---|---|---|---|
| {{ issue type }} | {{ issue id}} | {{ issue priority }} | {{ issue status }} | {{ issue assignee }} | {{ issue summary }} |

```
- and check if the issues have any information related to OCP version and managedcluster information, if yes, please append those information in the markdown file with below format, if no, no need any update.
```
### Issue env info
OCP Version: {{ ocp version }}
Spoke Cluster: {{ managedcluster }}
```