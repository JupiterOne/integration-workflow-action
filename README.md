# @jupiterone/integration-workflow-action

A public github action used to build & publish open-source JupiterOne integration projects.

Usage:

`.github/workflows/build.yml`:
```yml
name: Build
on: [push, pull_request]
jobs:
  integration-workflow-action:
    runs-on: ubuntu-latest
    steps:
			- id: setup-node
        name: Setup Node
        uses: actions/setup-node@v1
        with:
          node-version: 12.x
      - name: Check out code repository source code
        uses: actions/checkout@v2
      - id: integration-workflow-action
        name: J1 Integration Workflow Action
        uses: jupiterone/integration-workflow-action@v1
        with:
          NPM_AUTH_TOKEN: ${{ secrets.NPM_AUTH_TOKEN }}
```