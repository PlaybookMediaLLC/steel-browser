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

## Ponytail and code-review-graph

- Load the `ponytail` skill at the start of every coding task and follow it: make the smallest change that fully solves the task. Where it conflicts with the rest of this repository's instructions, those instructions win.
- Use the code-review-graph MCP tools before Grep, Glob or Read to find code, callers, tests and the blast radius of a change. Cloud sessions build the graph in the background at startup, so until `uvx code-review-graph status --json` reports `"build_incomplete": false`, an empty result does not prove the code is absent.
