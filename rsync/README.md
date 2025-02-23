# Github Action: DISTRO Core Sync rsync

This repository supplies a GitHub Action used as part of the build
process for distro-core.

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
    - if: ${{ steps.runner.outputs.runner-environment == 'self-hosted' && steps.bitbake-targets.outputs.dl_dir != '' && steps.runner.outputs.mnt_dl_dir != '' }}
      uses: distro-core/distro-core-action-rsync@main
      with:
        src_dir: ${{ steps.bitbake-targets.outputs.dl_dir }}
        dst_dir: ${{ steps.runner.outputs.mnt_dl_dir }}
~~~
