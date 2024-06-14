# workflows

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/docker-alw/workflows/main.svg)](https://results.pre-commit.ci/latest/github/docker-alw/workflows/main)
[![dependabot update](https://github.com/docker-alw/workflows/actions/workflows/dependabot/dependabot-updates/badge.svg)](https://github.com/docker-alw/workflows/actions/workflows/dependabot/dependabot-updates)
[![dependabot validate](https://github.com/docker-alw/workflows/actions/workflows/dependabot_validate.yml/badge.svg)](https://github.com/docker-alw/workflows/actions/workflows/dependabot_validate.yml)
[![release](https://github.com/docker-alw/workflows/actions/workflows/release.yml/badge.svg)](https://github.com/docker-alw/workflows/actions/workflows/release.yml)


This repository contains workflow templates to be imported by other repositories.

Available templates are:

* `docker-alw/workflows/.github/workflows/build_image.yml@v0`: build and push docker images to ghcr.io
* `docker-alw/workflows/.github/workflows/dependabot_validate.yml@v0`: run dependabot

## Usage

To use the provided templates just create a workflow file with following content:

Example for build-image:

```yaml
jobs:
  build-push:
    name: Build-Push
    permissions:
      actions: read
      packages: write
    uses: docker-alw/workflows/.github/workflows/build_image.yml@v0
```

Example for dependabot:

```yaml
jobs:
  validate:
    permissions:
      pull-requests: write
    uses: docker-alw/workflows/.github/workflows/dependabot_validate.yml@v0
```
