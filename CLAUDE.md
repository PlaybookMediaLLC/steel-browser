# Fork development rules

This repo is a PlaybookMediaLLC fork of steel-dev/steel-browser. The fork is currently a
pure mirror plus the nightly sync workflow.

1. Keep the fork delta at zero until the fork gets a defined role.
2. When fork work starts, put it in one new directory and record the rules
   here first.
3. `.github/workflows/sync-upstream.yml` merges upstream main into the
   `upstream` branch every night and opens a PR against main.
4. The Actions token cannot push changes to workflow files. When the sync
   job fails on a workflow-file push, run the merge locally and push the
   `upstream` branch with your own credentials. The next workflow run then
   opens the PR.
