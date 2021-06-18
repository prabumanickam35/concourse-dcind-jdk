# Concourse Docker-in-Docker with JDK
Based on [karlkfi/concourse-dcind](https://github.com/karlkfi/concourse-dcind) with Open JDK 8 added on top.

Perfect for Java/Kotlin projects using [Testcontainers](https://www.testcontainers.org/) for integration tests.

## How to get it
Images published to [Docker Hub](https://hub.docker.com/r/arrivalmobility/concourse-dcind-jdk).

## How to use it
Example task file: 
```yaml
---
platform: linux

image_resource:
  type: docker-image
  source:
    repository: pprabu49/concourse-dcind-jdk
    tag: {VERSION}

inputs:
  - name: my-project

run:
  path: entrypoint.sh
  args:
    - bash
    - -ceux
    - my-project/ci/tasks/build
```
