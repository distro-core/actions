# Github Action: DISTRO Core Sync S3

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
    - uses: distro-core/distro-core-action-s3sync@main
      with:
        src_dir: ${{ steps.bitbake-targets.outputs.dl_dir }}
        dst_dir: s3://distro-core-downloads
        AWS_ENDPOINT_URL: ${{ secrets.AWS_ENDPOINT_URL }}
        AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
        AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
~~~
