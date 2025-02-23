# Github Action: DISTRO Core Cleanup

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

Copyright (c) 2025 brainhoard.com

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](./LICENSE).

Editorial discretion is asserted on specific inclusion of layers that
may referenced. All upstream packages and their source code come with
their respective licenses. Individual packages license terms are to be
respected.

## Usage:

~~~ yaml
name: Tests

on:
  workflow_dispatch:

jobs:
  test:
    steps:
    - id: pre-cleanup
      uses: distro-core/distro-core-action-cleanup@main
      with:
        paths: |
          build/${{ vars.DISTRO }}/*.{log,lock,sock}
          build/${{ vars.DISTRO }}/conf/{.*,*}
          build/${{ vars.DISTRO }}
~~~
