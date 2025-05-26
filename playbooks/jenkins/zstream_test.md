The goal is to start the zstream test based on the test plan file {{ test plan }} I provided.

In order to start the zstream test based on the test plan file I provided, you should following below steps:

- first, you should able to read the content of the test plan file and check the ACM version, OCP Version, Spoke cluster information.
- Then, you should know which ACM release version I should test, then we will try to run the test on branch release-x.x based on the ACM version in the test plan, like if the ACM release version is 2.13.2, the branch will be release-2.13.
- Next, you should check if the test plan have the OCP environment information, and you should let me know which OCP version you are planning to test.
- Next, you should able to call the jenkins mcp server to kick off the jenkins jobs ServerFoundation-cronjob-smoke to run the test, and set the jenkins parameters OCP_RELEASE to stable-{{OCP Version}}, set ACM_RELEASE_VERSION to the branch version, set IMPORT_KUBERNETES_CLUSTERS to the spoke clusters from the test plan, and set the GIT_BRANCH to the branch version.