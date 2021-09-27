# Memex PowerShell Action Samples

This is a collection of GitHub actions for working with Memexes. The core functionality is built off [cmbrose/github-projects-powershell](https://github.com/cmbrose/github-projects-powershell), see that repo for more details.

## Actions

Note: all actions use the `PROJECTS_VNEXT_GRAPHQL_PAT` secret as the PAT for editing Memexes.

### Add issue to memex by label

Adds an issue to memex when it is given a certain label. Labels are configured by the `labelToMemexIdMap` map at the top of the main script. If the label doesn't match, the action will do nothing.