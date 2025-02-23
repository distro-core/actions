# Github Action: DISTRO Core Runner

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
    - id: runner
      if: ${{ vars.DISTRO != '' && vars.MACHINE != '' }}
      uses: distro-core/distro-core-action-runner@main
      # with:
      #   mnt_deploy_dir: /mnt/artifacts
      #   mnt_dl_dir: /mnt/downloads
      #   mnt_sstate_dir: /mnt/sstate-cache
~~~
