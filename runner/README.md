# Github Action: DISTRO Core Runner

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

## Usage

| inputs | Required | Desctiption |
| --- | --- | --- |
| mnt_deploy_dir | - | runner local path DEPLOY_DIR |
| mnt_dl_dir | - | runner local path DL_DIR |
| mnt_sstate_dir | - | runner local path SSTATE_DIR |

| outputs | Required | Desctiption |
| --- | --- | --- |
| runs-on | - | runner name |
| runner-environment | - | runner [ github-hosted, self-hosted ] |
| runner-os | - | runner os [ linux ] |
| runner-arch | - | runner cpu architecture |
| build-number | - | runner build number |
| mnt_deploy_dir | - | runner has detected path at mnt_deploy_dir |
| mnt_dl_dir | - | runner has detected path at mnt_dl_dir |
| mnt_sstate_dir | - | runner has detected path at mnt_sstate_dir |

Action yaml

~~~ yaml
jobs:
  test:
    steps:
    - id: runner
      if: env.DISTRO != '' && env.MACHINE != ''
      uses: distro-core/actions/runner@main
      with:
        mnt_dl_dir: ${{ env.MNT_DL_DIR }}
        mnt_sstate_dir: ${{ env.MNT_SSTATE_DIR }}
~~~
