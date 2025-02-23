# Github Action: DISTRO Core Bitbake

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

## Usage

| env | Required | Desctiption |
| --- | --- | --- |
| REPO_MANIFEST_URL | X | repo manifest url |
| REPO_MANIFEST_NAME | X | repo manifest name |
| REPO_MANIFEST_REF | X | repo manifest branch/tag/commit-id |
| DISTRO | X | bitbake variable DISTRO https://docs.yoctoproject.org/ref-manual/variables.html#term-DISTRO |
| MACHINE | X | bitbake variable MACHINE https://docs.yoctoproject.org/ref-manual/variables.html#term-MACHINE |
| TARGETS | X | bitbake command line targets_list |
| TARGETS_FLAGS | X | bitbake command line target_flags |
| EXTRA_TARGETS_FLAGS | - | bitbake command line extra target_flags |
| EXTRA_USER_CLASSES | - | bitbake variable USER_CLASSES:append |
| EXTRA_PREMIRRORS | - | bitbake variable PREMIRRORS:prepend https://docs.yoctoproject.org/ref-manual/variables.html#term-PREMIRRORS |
| EXTRA_SSTATE_MIRRORS | - | bitbake variable SSTATE_MIRRORS:prepend https://docs.yoctoproject.org/ref-manual/variables.html#term-SSTATE_MIRRORS |

| outputs | Required | Desctiption |
| --- | --- | --- |
| targets | - | bitbake targets list |
| deploy_dir | - | bitbake variable DEPLOY_DIR https://docs.yoctoproject.org/ref-manual/variables.html#term-DEPLOY_DIR |
| distro_codename | - | bitbake variable DISTRO_CODENAME https://docs.yoctoproject.org/ref-manual/variables.html#term-DISTRO_CODENAME |
| cache | - | bitbake path CACHE https://docs.yoctoproject.org/ref-manual/variables.html#term-CACHE |
| dl_dir | - | bitbake path DL_DIR https://docs.yoctoproject.org/ref-manual/variables.html#term-DL_DIR |
| sstate_dir | - | bitbake path SSTATE_DIR https://docs.yoctoproject.org/ref-manual/variables.html#term-SSTATE_DIR |
| tmpdir | - | bitbake path TMPDIR https://docs.yoctoproject.org/ref-manual/variables.html#term-TMPDIR |
| topdir | - | bitbake path TOPDIR https://docs.yoctoproject.org/ref-manual/variables.html#term-TOPDIR |
| build| - | bitbake bblayers configuration from bitbake.log |
| error | - | bitbake error output from bitbake-error.log, limited size |
| warn | - | bitbake warning output from bitbake-warn.log, limited size |

Action yaml

~~~ yaml
jobs:
  test:
    steps:
    - id: bitbake-targets
      uses: distro-core/actions/bitbake@main
~~~
