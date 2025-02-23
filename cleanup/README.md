# Github Action: DISTRO Core Cleanup

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

## Usage

| inputs | Required | Desctiption |
| --- | --- | --- |
| paths | X | cleanup paths |

Action yaml

~~~ yaml
jobs:
  test:
    steps:
    - id: pre-cleanup
      uses: distro-core/actions/cleanup@main
      with:
        paths: >-
          build/*.{log,lock,sock}
          build/conf/{.*,*}
          build/tmp
~~~
