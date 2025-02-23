# Github Action: DISTRO Core Sync rsync

This repository supplies a GitHub Action used as part of the build
process for distro-core.

## LICENSE Information

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

## Usage

| inputs | Required | Desctiption |
| --- | --- | --- |
| src_dir | X | source directory path |
| dst_dir | X | destination directory path |
| expiry_days | - | expiry days |

| outputs | Required | Desctiption |
| --- | --- | --- |
| src_dir | - | source directory path |
| dst_dir | - | destination directory path |

Action yaml

~~~ yaml
jobs:
  test:
    steps:
    - id: rsync-dl-dir
      if: steps.bitbake-targets.outputs.dl_dir != '' && steps.runner.outputs.mnt_dl_dir != ''
      uses: distro-core/actions/rsync@main
      with:
        src_dir: ${{ steps.bitbake-targets.outputs.dl_dir }}
        dst_dir: ${{ steps.runner.outputs.mnt_dl_dir }}
~~~
