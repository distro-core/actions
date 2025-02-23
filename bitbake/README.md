# Github Action: DISTRO Core Bitbake

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

Copyright (c) 2025 brainhoard.com

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

Editorial discretion is asserted on specific inclusion of layers that
may referenced. All upstream packages and their source code come with
their respective licenses. Individual packages license terms are to be
respected.

## Usage:

~~~ yaml
jobs:
  test:
    steps:
    - id: bitbake-targets
      uses: distro-core/distro-core-action-bitbake@main
      with:
        DISTRO: ${{ vars.DISTRO }}
        MACHINE: ${{ vars.MACHINE }}
        TARGETS: ${{ vars.TARGETS }}
        TARGET_FLAGS:
~~~
