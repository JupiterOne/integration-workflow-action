# @jupiterone/integration-workflow-action

A public github action used to build & publish open-source JupiterOne integration projects.

Usage:

`.github/workflows/build.yml`:
```yml
name: Build
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - id: integration-workflow-action
        name: J1 Integration Workflow Action
        uses: @jupiterone/integration-workflow-action@v0.1
        with:
          NPM_AUTH_TOKEN: ${{ secrets.NPM_AUTH_TOKEN }}
```