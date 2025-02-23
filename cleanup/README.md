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

| inputs | Required | Desctiption |
| --- | --- | --- |
| paths | X | cleanup paths |

Example:

~~~ yaml
jobs:
  test:
    steps:
    - id: pre-cleanup
      uses: distro-core/actions/cleanup@main
      with:
        paths: |
          build/*.{log,lock,sock}
          build/conf/{.*,*}
          build/tmp
~~~
