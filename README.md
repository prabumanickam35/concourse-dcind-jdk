# Concourse Docker-in-Docker with JDK
Based on [karlkfi/concourse-dcind](https://github.com/karlkfi/concourse-dcind) with Open JDK 11 added on top.

Perfect for Java project using [Testcontainers](https://www.testcontainers.org/) for integration tests.

## Usage
Example task file: 
```yaml
---
platform: linux

image_resource:
  type: docker-image
  source:
    repository: arrivalmobility/concourse-dcind-jdk
    tag: 1.0.0

inputs:
  - name: my-project

run:
  path: entrypoint.sh
  args:
    - bash
    - -ceux
    - my-project/ci/tasks/build
```
