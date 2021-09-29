# Memex PowerShell Action Samples

This is a collection of GitHub actions for working with Memexes. The core functionality is built off [cmbrose/github-projects-powershell](https://github.com/cmbrose/github-projects-powershell), see that repo for more details.

## Actions

Note: all actions use the `PROJECTS_VNEXT_GRAPHQL_PAT` secret as the PAT for editing Memexes.

### Add issue to memex by label

[Source](https://github.com/cmbrose/memex-ps-action-samples/blob/main/.github/workflows/add-issue-to-memex-by-label.yml)

Adds an issue to memex when it is given a certain label. Labels are configured by the `labelToMemexIdMap` map at the top of the main script. If the label doesn't match, the action will do nothing.

### Set Triaged Items to In Progress

[Source](https://github.com/cmbrose/memex-ps-action-samples/blob/main/.github/workflows/set-triaged-items-to-in-progress.yml)

Periodically scans all Issues and PRs in a memex and moves items which have been newly triaged from `Triage` status to `In Progress`. This is determined by the current state still being `Triage` and several fields which are filled during triage being populated.

Note that currently this type of action must run on a `cron` schedule as we cannot trigger actions off the fields themselves being set.
